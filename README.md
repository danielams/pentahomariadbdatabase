# pentahomariadbdatabase
Pentaho Data Integration MariaDB database plugin

Pentaho Data Integration MariaDB database connection OSGI bundle plugin. The plugin allows the user select in the database connection panel the MariaDB connection type.

To build the project you need to clone the repository and execute the command
```sh
mvn package
```

To deploy the pentaho-mariadb-database-1.0-SNAPSHOT.jar in the Pentaho Data Integration is needed to:

* edit the file system/karaf/etc/org.apache.karaf.features.cfg and add ssh at the end of the following line
```ini
featuresBoot=config,pentaho-base,pentaho-client-ee,pdi-dataservice,pentaho-metaverse,pentaho-big-data-ee-plugin-osgi-obf,pdi-data-refinery,ssh
```

Connect to the karaf with the username and password karaf
```sh
ssh karaf@127.0.0.1 -p 8802
```  
and install the bundle using the command:
```sh
bundle:install -s file:/${your_path}/pentahomariadbdatabase/target/pentaho-mariadb-database-1.0-SNAPSHOT.jar
```

Download the proper jdbc connector from the MariaDB https://mariadb.com/kb/en/mariadb/about-mariadb-connector-j/ and put it in the folder lib/ of the data integration

The new connector is available in the connections type of the database connections
