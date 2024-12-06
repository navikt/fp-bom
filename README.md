# fp-bom

Inneholder en felles Bill of Material (BOM) som brukes av alle biblioteker/applikasjoner laget av #teamforeldrepenger.

## Teknologi oversikt

Platform - [Jakarta EE 10](https://projects.eclipse.org/releases/jakarta-10)

### Jakarta API implementasjoner brukt

* Servlets - [Jetty Embedded Server](https://www.eclipse.org/jetty/documentation.php)
* Authentication - [Jetty JAAS](https://www.eclipse.org/jetty/documentation/jetty-10/operations-guide/index.html#og-jaas), [Jetty JASPI](https://www.eclipse.org/jetty/documentation/jetty-10/operations-guide/index.html#og-jaspi) - fases ut
* Persistence - [Hibernate ORM](https://hibernate.org/orm)
* Bean Validation - [Hibernate Validator](https://hibernate.org/validator/)
* Context and Dependency Injection (CDI) - [JBoss Weld Servlet Core](http://weld.cdi-spec.org/) + [Jandex](https://smallrye.io/jandex/jandex/3.0.0/index.html)
* REST (JAX-RS) - [Eclipse Jersey](https://eclipse-ee4j.github.io/jersey/)
* JSON Binding - [FasterXML Jackson](https://github.com/FasterXML/jackson)
* JSON Processing - [FasterXML Jackson](https://github.com/FasterXML/jackson)
* Messaging (JMS) - [IBM MQ client](https://www.ibm.com/docs/en/ibm-mq/8.0?topic=jms-writing-mq-classes-applications)
* Expression Language (EL) - [Eclipse Expressly](https://mvnrepository.com/artifact/org.glassfish.expressly) - brukes av Hibernate Validator

Fasses ut:
* XML Binding - SUN [jaxb-impl](https://mvnrepository.com/artifact/com.sun.xml.bind/jaxb-impl) og Glassfish [jaxb-runtime](https://mvnrepository.com/artifact/org.glassfish.jaxb/jaxb-runtime)

### Databaser

* [Oracle](https://www.oracle.com/database/technologies/)
* [PostgreSQL](https://www.postgresql.org/)

### Sikkerhet 

* Token validering - [NAV Token Support](https://github.com/navikt/token-support) + [Jetty JASPI](https://www.eclipse.org/jetty/documentation/jetty-10/operations-guide/index.html#og-jaspi) - JASPI fases ut
* Passord lagring - [Vault](https://www.vaultproject.io/) + Kubernetes [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) 
* Tilgangskontroll - [Axiomatisc ABAC](https://axiomatics.com/resources/reference-library/attribute-based-access-control-abac) - fases ut

### Andre

* Applikasjons konfig - [fp-konfig](https://github.com/navikt/fp-felles/tree/master/felles/konfig)
* Kafka - [Apache Kafka](https://kafka.apache.org/)
* Kafka Schema - [Avro](https://docs.confluent.io/platform/current/schema-registry/serdes-develop/serdes-avro.html#avro-schema-serializer-and-deserializer)
* Caching - [Ehcache](https://www.ehcache.org/)
* MQ - [IBM MQ Client](https://www.ibm.com/docs/en/ibm-mq/9.3?topic=umcjm-obtaining-mq-classes-jms-mq-classes-jakarta-messaging-separately) 
* Testing - [JUnit](https://junit.org/junit5/) + [AssertJ](https://assertj.github.io/doc/) + [Mockito](https://site.mockito.org/)
* Logging - [SLF4J API](https://www.slf4j.org/) + [Logback](https://logback.qos.ch/)
* OpenAPI (OAS 3) - [Swagger](https://swagger.io/resources/open-api/)
* DB Change Management - [Flyway DB](https://flywaydb.org/)
* Connection Pool Management - [HikariCP](https://github.com/brettwooldridge/HikariCP)
* Monitoring - [Prometheus](https://prometheus.io/) + [Micrometer](https://micrometer.io/)
* OpenTelemetry - [OpenTelemetry](https://github.com/open-telemetry/opentelemetry-java-instrumentation)
