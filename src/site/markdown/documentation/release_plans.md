<head><title>Release Plans</title></head>

# Section : [Documentation](index.html) 

## DataNucleus AccessPlatform 4.1

This is current scope for DataNucleus 4.1. If you think other things ought to be included then the answer is simple : get involved.

### Feature Scope

* Rewrite SCO "update" initialisation to cater for cascade delete and optimisation.
* Extend 'operation queue' to include persist, update, remove operations, and migrate to not use the dirtyOPs/indirectDirtyOPs?
* JDO 4.0?
* Make ClassLoaderResolver clearer and allow update of class definitions (put ClassLoader before all other loaders)?
* Support Java 1.8 "Optional" ?

### Release Plans

* __4.1M2 Mar 2015?__



## DataNucleus AccessPlatform 4.0

All plugins were branched for this release cycle.

### Feature Scope

* Runtime will still be supported as runnable for JDK1.7\+
* Extend SchemaAwareStoreManager/SchemaTool to add createSchema/dropSchema
* Upgrade ODF, Excel, HBase, MongoDB plugins to start using "persistable-identity"
* Clean up NucleusContext "type" and maybe make NucleusContext an interface, and have PersistenceNucleusContext for persistence runtime. Means that we could also add a SchemaNucleusContext later on for schema tool(s)
* Transaction savepoints - *Basic API present in core, and supported in RDBMS* (needs testing)
* Clean up MetaDataManager and maybe make it an interface.
* Move majority of schema operations from StoreManager to StoreSchemaHandler
* Upgrade ASM to v5.0
* Generalise TypeConverters so they can support conversion to multiple datastore column values and usable by all store plugins
* Support JDK1.8 (including javax.time - so build requirement for java8 plugin at least will be 1.8)
* Official support for [Cassandra|http://www.datanucleus.org/servlet/wiki/display/ENG/Cassandra] v1.2\+
* Upgrade relevant store plugins to use Table/Column structure and benefit from common features, for ODF, Excel, JSON, MongoDB, Neo4j, HBase
* Upgrade enhancement process to enhance to org.datanucleus.enhancer.Persistable so that users need to have "datanucleus-core.jar" in the CLASSPATH and not "jdo-api.jar".
* Drop EclipsePluginRegistry so all OSGi users should use OSGiPluginRegistry
* Schema Evolution : restructure schema properties to allow for all we will need when adding/removing fields etc

### Release Plans

* __4.0.6 Mar/Apr 2015?__



## DataNucleus AccessPlatform 3.3

### Feature Scope

* JPA2.1 full feature list

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 3.2

### Feature Scope

* Branch on release 3.1.2 (03/Oct/2012)
* Merge "enhancer" into "core" and "api.jdo"
* Repackage ASM into "core" to avoid extra dependency
* Move documentation to use Maven3 "site"/"pdf" plugins
* JPA2.1 features
* Some streamlining of persistence process (default persistent if supported type, pooled ExecutionContext/ObjectProvider, disable L2 cache per PM/EM, etc)

### Release Plans

* _No further releases planned; commercial enquiries required._



## DataNucleus AccessPlatform 3.1

### Feature Scope

* Branch on release 3.0.6
* Move javax.time into core
* Move javax.cache into core
* JPA2.1 Stored Procedures
* JPA2.1 Type Converters
* Naming Factory for all non-RDBMS datastores
* Statistics API, integrated with JMX (remove need for management plugin)
* Support JDK1.7 (Use ASM v4.0)
* JDK1.6+ at runtime
* Neo4j plugin

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 3.0

### Feature Scope

* Branch on release 2.2.1
* Increased modularity of persistence features
* Definitive comparison of persistence features across supported datastores
* [Data Federation]
* [ENG:API Framework] modularity; each API has its own jar
* Good support for MongoDB, HBase, ODF, Excel
* Support for SQLite
* Upgrade to ODFDOM 0.8.7+

Note : API backward compatibility broken.

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 2.2

### Feature Scope

* Branch on release 2.1.1
* Drop legacy JDOQL mechanism for RDBMS
* Type-safe refactorable JDO queries
* Complete JPA2 functionality

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 2.1

### Feature Scope for 2.1

* Branch on release 2.0.2
* JDOQL2 for RDBMS becomes default
* JPA2 Complete (Certification depends on the JCP and getting a TCK, so forget that)
* Support for persistence to OOXML
* Support for persistence to GoogleStorage
* Support for persistence of javax.time types (JSR0310)
* Support for persistence of some Google Collections types
* StorePersistenceHandler

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 2.0

### Feature Scope for 2.0

* Datastores : Add support for HBase, Amazon S3, Oracle Timesten
* In-memory evaluation of contains(), containsKey(), containsValue()
* Drop support for Oracle <= 8, DB2 < 8, Informix style joins, so we maintain ANSI style joins only from this point - use AccessPlatform 1 otherwise
* Drop support for building using Ant ("build.xml", "build.properties") - undocumented and inconsistent.
* Caching of query compilations and results
* JPA2 implementation - build from Geronimo EA JPA2 jar
* Rewrite of JPQL for RDBMS, using generic query mechanism
* Rewrite of JDOQL for RDBMS, using generic query mechanism

### Release Plans

* _No further releases planned; commercial  enquiries required._



## DataNucleus AccessPlatform 1.1

### Feature Scope for 1.1

* Datastores : Add support for ODF, BigTable
* JDK1.5\+ from this release onwards. Move enum to store.rdbms, move JDO+annotations to core, move rest to JPA. Merge JDK1.3/1.4 SCO wrappers
* Remove NucleusSQL - not strategic direction, and hardly used but have a maintenance cost
* Provide generic compilation to SQL converter so that we can start to think about replacing RDBMS JDOQL/JPQL and fixing all of those bugs that exist in it.

### Release Plans

* _No further releases planned; commercial enquiries required._



## DataNucleus AccessPlatform 1.0

### Feature Scope for 1.0

* Datastores : Add support for LDAP, XML, Excel, NeoDatis, JSON
* APIs : JDO2.1, JPA1, some of JPA2 (most of JPA2 can go in Access Platform 1.2/2.0)
* Query Languages : JDOQL for all datastores, SQL for RDBMS, db4o, JPQL for RDBMS.

### Release Plans

* _No further releases planned; commercial enquiries required._

