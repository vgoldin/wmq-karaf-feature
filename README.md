# wmq-karaf-feature
IBM WebSphere Connection Pool Service for Apache Karaf

1. Define default WebSphereMQ connectivity parameters in src/main/resources/wmq.service.cfg
2. Build with "mvn clean install"
3. Deploy wmq-feature-kar-assembly-${project.version}.kar to KARAF_HOME/deploy folder

Reference the service in your OSGi bundle with:

```
<osgi:reference id="wmqConnectionPool" filter="(name=default-wmq-cf)" interface="javax.jms.ConnectionFactory"/>

<bean id="wmq" class="org.apache.camel.component.jms.JmsComponent">
    <property name="connectionFactory" ref="wmqConnectionPool"/>
</bean>
```
