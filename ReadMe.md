# POC EAR with multi WAR files

mvn clean package
cp ./example-ear/target/multi-war.ear ./docker/deployments/multi-war.ear

See ./docker/clients/n1/configuration/standalone.xml

```xml
<secure-deployment name="product-portal.war">
    <realm>${env.KEYCLOAK_REALM}</realm>
    <resource>${env.KEYCLOAK_CLIENT}</resource>
    <auth-server-url>https://${env.KEYCLOAK_HOST}/auth</auth-server-url>
    <credential name="secret">${env.KEYCLOAK_SECRET}</credential>
    <ssl-required>none</ssl-required>
    <register-node-at-startup>true</register-node-at-startup>
    <register-node-period>600</register-node-period>
</secure-deployment>
<secure-deployment name="customer-portal.war">
    <realm>${env.KEYCLOAK_REALM}</realm>
    <resource>${env.KEYCLOAK_CLIENT}</resource>
    <auth-server-url>https://${env.KEYCLOAK_HOST}/auth</auth-server-url>
    <credential name="secret">${env.KEYCLOAK_SECRET}</credential>
    <ssl-required>none</ssl-required>
    <register-node-at-startup>true</register-node-at-startup>
    <register-node-period>600</register-node-period>
</secure-deployment>
```

Work fine !!!