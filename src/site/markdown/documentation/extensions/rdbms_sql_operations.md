<head><title>Extensions : RDBMS SQL Operations</title></head>

# Section : [Documentation](../index.html) > [Extensions](index.html)

## Extensions : RDBMS SQL Operations Support
![Plugin](../../images/nucleus_plugin.gif)

DataNucleus is developed as a plugin-driven framework and one of the components that is 
pluggable is the support for JDOQL/JPQL operations in the "new" query mechanism. 
DataNucleus provides support for all major operations typically handling them internally
but occasionally handing off to an SQL function where one is more appropriate. However
the codebase is structured so that you could add on support for your own easily enough

The following sections describe how to create your own SQL Operation plugin for DataNucleus.

### Interface

Any SQL operation plugin will need to implement _org.datanucleus.store.rdbms.sql.operation.SQLOperation_
[![Javadoc](../../images/javadoc.gif)](http://www.datanucleus.org/javadocs/store.rdbms/latest/org/datanucleus/store/rdbms/sql/operation/SQLOperation.html).
So you need to implement the following interface

	import org.datanucleus.store.rdbms.sql.method;
	
	public interface SQLOperation
	{
    	/**
    	 * Return the expression for this SQL function.
    	 * @param expr Left hand expression
    	 * @param expr2 Right hand expression
    	 * @return The SQL expression for the operation
    	 */
    	public SQLExpression getExpression(SQLExpression expr, SQLExpression expr2);
	}

### Implementation

So there is only one method to provide in your implementation. The arguments to this are

* The expression on the left hand side of the operation. So if you have _{expr1} {operation} {expr2}_ then the first argument will be _{expr1}_
* The expression on the right hand side of the operation. So if you have _{expr1} {operation} {expr2}_ then the first argument will be _{expr2}_

So if we wanted to support _modulus (%)_ (so something like __expr1 % expr2__)
and wanted to use the SQL function "MOD" to provide this then we define our class as

	package mydomain;
	
	import java.util.ArrayList;
	
	import org.datanucleus.exceptions.NucleusException;
	import org.datanucleus.store.rdbms.sql.operation.SQLOperation;
	import org.datanucleus.store.rdbms.sql.expression.SQLExpression;
	import org.datanucleus.store.rdbms.sql.expression.NumericExpression;
	
	public class MyModOperation implements SQLOperation
	{
    	public SQLExpression getExpression(SQLExpression expr, SQLExpression expr2)
    	{
        	ArrayList args = new ArrayList();
        	args.add(expr);
        	args.add(expr2);
        	return new NumericExpression("MOD", args);
    	}
	}

So in this implementation when the user includes _{expr1} % {expr2}_ this is translated into the SQL __MOD({expr1}, {expr2})__ which will certainly
work on some RDBMS. Obviously you could use this extension mechanism to support a different underlying SQL function.

### Plugin Specification

So we now have our custom SQL method and we just need to make this into a DataNucleus plugin. To do this you simply add a file 
_plugin.xml_ to your JAR at the root. The file _plugin.xml_ should look like this

	<?xml version="1.0"?>
	<plugin id="mydomain" name="DataNucleus plug-ins" provider-name="My Company">
    	<extension point="org.datanucleus.store.rdbms.sql_operation">
        	<sql-operation name="mod" datastore="hsql"
            	evaluator="mydomain.MyModOperation"/>
    	</extension>
	</plugin>

Note that you also require a MANIFEST.MF file as per the [Extensions Guide](index.html).

So we defined calls to an operation _mod_ for the datastore "hsql" to use our evaluator. Simple! 
Whenever this operation is encountered in a query from then on for the HSQL database it will use our operation evaluator.
