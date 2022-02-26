# trino-udf-archetype

This is an archetype to generate bootstrapped UDF projects.

## Getting Started

### Installing

#### Remote

The archetype has not been uploaded to the Maven archetype catalog yet.

#### Local

Download/clone this project and run the following command to build the archetype locally.

```
mvn clean install archetype:update-local-catalog
```

Also works with just the following command.

```
mvn install
```

### Generating

After you have installed the archetype, you are able to use it from the command line.

Example: Using all defaults

```
mvn archetype:generate -B -DarchetypeGroupId=io.trino -DarchetypeArtifactId=trino-udf-archetype -DarchetypeVersion=1.0 -DartifactId=IsNullUdf -Dversion=360
```

Example: Customizing some of the parameters

```
mvn archetype:generate -B -DarchetypeGroupId=io.trino -DarchetypeArtifactId=trino-udf-archetype -DarchetypeVersion=1.0 -DartifactId=IsNullUdf -Dversion=360 -DgroupId=com.example -DpluginId=udf.spiffy
```

#### Parameters

**-B** runs maven in non-interactive mode.Do not include if interactive mode is desired.

The coordinates for the archetype. The current version is 1.0, but that may change so this parameter may need to be modified.

```
-DarchetypeGroupId=io.trino -DarchetypeArtifactId=trino-udf-archetype -DarchetypeVersion=1.0
```

*artifactId* is one of the coordinates of the generated maven UDF project. This is the name of the project.  It does not have a default value.

```
-DartifactId=IsNullUdf
```

*groupId* is one of the coordinates of the generated maven UDF project. The default value is *io.trino*. Can be overridden in interactive mode.

```
-DgroupId=com.example
```

*version* is one of the coordinates of the generated maven UDF project. This is the target version of Trino/Starburst. It does not have a default value.

```
-Dversion=364
```

*pluginId* is used to compose the package in non-interactive mode. The default value is *plugin.sample*. Can be overridden in interactive mode.

Note: If *package* is overridden, this value is ignored.

```
-DpluginId=mysoftware.myplugin
```

*package* specifies the Java package generated for the project. This value defaults to *{groupId}.{pluginId}*. Can be overridden in interactive mode. Really not intended for external use.

Note: It's recommended to include the *groupId* as part of the package value.

```
-Dpackage=com.example.plugin.yowza
```

The values used to generate the UDF project can be seen in the Maven output

```
[INFO] ----------------------------------------------------------------------------
[INFO] Using following parameters for creating project from Archetype: trino-udf-archetype:1.0
[INFO] ----------------------------------------------------------------------------
[INFO] Parameter: groupId, Value: io.trino
[INFO] Parameter: artifactId, Value: plugin
[INFO] Parameter: version, Value: 360
[INFO] Parameter: package, Value: io.trino.snarf
[INFO] Parameter: packageInPathFormat, Value: io/trino/snarf
[INFO] Parameter: package, Value: io.trino.snarf
[INFO] Parameter: pluginId, Value: snarf
[INFO] Parameter: groupId, Value: io.trino
[INFO] Parameter: artifactId, Value: plugin
[INFO] Parameter: version, Value: 360
[INFO] Project created from Archetype in dir: /Starburst/Projects/UDFTest/plugin
[INFO] ------------------------------------------------------------------------
```

## Built With

* [Maven](https://maven.apache.org/) - Dependency Management
