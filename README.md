# wmq-karaf-feature
IBM WebSphere Connection Pool Service for Apache Karaf

1. Build with "mvn clean install"
2. Deploy wmq-feature-kar-assembly-${project.version}.kar to KARAF_HOME/deploy folder
3. Copy src/main/resources/wmq.service.cfg to KARAF_HOME/etc and adjust WebSphereMQ connectivity parameters

Reference the service in your OSGi bundle with:

```
<osgi:reference id="wmqConnectionPool" filter="(name=default-wmq-cf)" interface="javax.jms.ConnectionFactory"/>

<bean id="wmq" class="org.apache.camel.component.jms.JmsComponent">
    <property name="connectionFactory" ref="wmqConnectionPool"/>
</bean>
```
