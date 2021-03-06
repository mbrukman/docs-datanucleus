<head><title>Download</title></head>

## DataNucleus Releases Download

DataNucleus provides Open Source products, and you can freely download any __release__ of DataNucleus, together with the associated source code.
DataNucleus downloads are subject to the [Apache 2 License](documentation/license.html).
Note that DataNucleus software versioning uses the versioning strategy defined [here](documentation/development/index.html#versioning).
We hope that you are successful in your use of DataNucleus, and if you have any problems or queries, please contact us using the [Forum](http://forum.datanucleus.org). 
Be aware that we don't have much time for this free support so you could make a [donation](documentation/donations.html) to further development and pay for our time providing support.

The first thing to note is that __all DataNucleus releases are "stable"__, in that they all pass all DataNucleus tests and the relevant TCKs, 
so any referral to some "stable branch" is a concept for other projects; the whole point of TDD is to guarantee stability.
The principal DataNucleus releases are :-

<table width="100%" border="0" cellpadding="2" cellspacing="2">
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="https://sourceforge.net/projects/datanucleus/files/datanucleus-accessplatform" target="_blank"><img alt="" src="images/logos/DataNucleus_AccessPlatform_40.jpg"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="https://sourceforge.net/projects/datanucleus/files/datanucleus-accessplatform" target="_blank"><b>DataNucleus AccessPlatform Zip</b></a> : 
            Zip of all DataNucleus plugin jars for a particular datastore and, optionally, jars
            for key dependencies. You can also check the dependencies for 
            <a href="http://www.datanucleus.org/products/accessplatform_4_2/dependencies.html">4.2</a>,
            <a href="http://www.datanucleus.org/products/accessplatform_4_1/dependencies.html">4.1</a>,
            <a href="http://www.datanucleus.org/products/accessplatform_5_0/dependencies.html">5.0</a>
            separately if you wish. Available from our SourceForge project home page.
        </td>
    </tr>
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="http://central.maven.org/maven2/org/datanucleus/" target="_blank"><img alt="" src="images/download_plugins.gif"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="http://central.maven.org/maven2/org/datanucleus/" target="_blank"><b>DataNucleus Plugin JARs</b></a> : 
            DataNucleus products are made up of a selection of plugins, and each plugin is also an OSGi bundle. You can download plugins individually, if you wish, as they are released.
            Available from the <a href="http://central.maven.org/maven2/org/datanucleus/">Maven Central</a> repository.
        </td>
    </tr>
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="http://central.maven.org/maven2/org/datanucleus/datanucleus-maven-plugin" target="_blank"><img alt="" src="images/download_maven.gif"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="http://central.maven.org/maven2/org/datanucleus/datanucleus-maven-plugin" target="_blank"><b>Maven Plugin</b></a> : 
            The DataNucleus Maven plugin provides enhancement of classes and the opportunity to manage the database schema.
            Available from the <a href="http://central.maven.org/maven2/org/datanucleus/datanucleus-maven-plugin/">Maven Central</a> repository.
        </td>
    </tr>
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="http://www.datanucleus.org/downloads/eclipse-update" target="_blank"><img alt="" src="images/download_eclipse.gif"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="http://www.datanucleus.org/downloads/eclipse-update" target="_blank"><b>Eclipse Plugin</b></a> : 
            The DataNucleusEclipse plugin provides enhancement of classes and the opportunity to manage the database schema.
            You can download this plugin by adding the DataNucleus "Eclipse Update" site of <i>http://www.datanucleus.org/downloads/eclipse-update</i> to your Eclipse configuration.
        </td>
    </tr>
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="https://sourceforge.net/projects/datanucleus/files/datanucleus-samples" target="_blank"><img alt="" src="images/download_samples.gif"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="https://sourceforge.net/projects/datanucleus/files/datanucleus-samples" target="_blank"><b>DataNucleus Samples</b></a> :
            There are various samples of code for use with DataNucleus available, including the source files from the tutorial. 
            Available from SourceForge for easy download, with the source code projects housed on GitHub for 
            <a href="https://github.com/datanucleus/samples-jdo">JDO</a> and <a href="https://github.com/datanucleus/samples-jpa">JPA</a>.
        </td>
    </tr>
</table>

## DataNucleus Nightly Builds Download

We also provide a nightly build of the current GitHub codebase (from GitHub around 2AM GMT).
DataNucleus downloads are subject to the [Apache 2 License](documentation/license.html).
Note that DataNucleus software versioning uses the versioning strategy defined [here](documentation/development/index.html#versioning).

<table width="100%" border="0" cellpadding="2" cellspacing="2">
    <tr>
        <td style="vertical-align: middle; width: 174px;" bgcolor="#FFFFFF" align="center">
            <a href="http://www.datanucleus.org/downloads/maven2-nightly/org/datanucleus" target="_blank"><img alt="" src="images/download_nightly-build.gif"/></a>
        </td>
        <td style="vertical-align: middle; width: 100%;" bgcolor="#FFFFFF">
            <a href="http://www.datanucleus.org/downloads/maven2-nightly/org/datanucleus" target="_blank"><b>Nightly build of plugin JARs</b></a> : 
            here you can find all JARs of all plugins that have changed since the most recent release.
        </td>
    </tr>
</table>

If using Maven you simply need to add the following to your _pom.xml_


    <repositories>
        <repository>
            <id>DN_Nightly_M2_Repo</id>
            <url>http://www.datanucleus.org/downloads/maven2-nightly/</url>
            <releases>
                <enabled>false</enabled>
            </releases>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>


Please be aware that all nightly builds are development work-in-progress and no guarantee is provided. These builds are typically stable but things may be 
broke occasionally as new features are added etc. You cannot report issues in GitHub against nightly builds, only against released versions of DataNucleus, 
but should report any problems in the ['General Development' Forum](http://forum.datanucleus.org/) if you have an issue with a nightly build, 
preferably after waiting a few days in case it is a work in progress type situation with a new feature being introduced.
