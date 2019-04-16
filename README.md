# camel-dbcp

## Shell command

### PostgreSQL

```
CREATE DATABASE sample;
CREATE TABLE test (name text);
```

### Maven

```
mvn clean package
```

### Karaf 4.1.1

#### Install bundle

```
feature:repo-add camel 2.9.12
feature:install camel-core camel-blueprint camel-sql
feature:repo-add pax-jdbc 1.3.0
feature:install transaction jndi pax-jdbc-postgresql pax-jdbc-pool-dbcp2 pax-jdbc-config
```

#### Operation check

```
service:list DataSourceFactory
log:tail
```

#### Bundle list

```
START LEVEL 100 , List Threshold: 50
 ID │ State  │ Lvl │ Version            │ Name
────┼────────┼─────┼────────────────────┼───────────────────────────────────────
 28 │ Active │  80 │ 4.1.1              │ Apache Karaf :: OSGi Services :: Event
 53 │ Active │  50 │ 2.19.2             │ camel-blueprint
 54 │ Active │  80 │ 2.19.2             │ camel-commands-core
 55 │ Active │  50 │ 2.19.2             │ camel-core
 56 │ Active │  80 │ 2.19.2             │ camel-karaf-commands
 61 │ Active │  50 │ 2.19.2             │ camel-sql
 74 │ Active │  80 │ 3.0.0              │ Expression Language 3.0 API
 75 │ Active │  80 │ 1.2.0              │ CDI APIs
 76 │ Active │  80 │ 1.2                │ javax.interceptor API
 77 │ Active │  80 │ 1.2                │ javax.transaction API
 83 │ Active │  80 │ 1.1.1              │ Apache Aries Transaction Blueprint
 84 │ Active │  80 │ 2.1.0              │ Apache Aries Transaction Blueprint
 85 │ Active │  80 │ 1.3.2              │ Apache Aries Transaction Manager
 86 │ Active │  80 │ 2.1.1              │ Apache Commons DBCP
 87 │ Active │  80 │ 2.5.0              │ Apache Commons Pool
 88 │ Active │  80 │ 1.0.2              │ Apache Felix Coordinator Service
 90 │ Active │  80 │ 3.2.4.1            │ Apache ServiceMix :: Bundles :: cglib
 91 │ Active │  80 │ 1.9.2.1            │ Apache ServiceMix :: Bundles :: jasypt
 92 │ Active │  80 │ 1.0.0.2            │ Apache ServiceMix :: Bundles :: javax
 94 │ Active │  80 │ 1.3.0              │ OPS4J Pax JDBC Config
 95 │ Active │  80 │ 1.3.0              │ OPS4J Pax JDBC Pooling Support Base
 96 │ Active │  80 │ 1.3.0              │ OPS4J Pax JDBC Pooling DBCP2
 97 │ Active │  80 │ 1.0.0.201505202023 │ org.osgi:org.osgi.service.jdbc
 98 │ Active │  80 │ 9.4.1212.jre7      │ PostgreSQL JDBC Driver JDBC41
101 │ Active │  80 │ 1.0.0.SNAPSHOT     │ A Camel Blueprint Route
```

## References

- [Apache Karaf Tutorial Part 6 - Database Access | Karaf-Tutorial](http://liquid-reality.de/Karaf-Tutorial/06/)
