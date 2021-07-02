# Maximo Connector

The Anypoint Connector for Maximo enables you to connect Mule flows to the Maximo system using the Maximo Web API.

For information about compatibility and fixed issues, see [Maximo Connector Release Notes](http://example.com/).

All required request headers, error handling, and HTTPS connection configurations are built into the connector.

You can use the Maximo Connector in Mule applications as an outbound connector with CRUD (create, retrieve, update, delete) operations on all non-system Maximo Objects on a given Maximo Server.

## Prerequisites

To use this connector, you must be familiar with:

- Maximo Server
- Mule runtime engine (Mule), including concepts, elements in a Mule flow, and global elements.
- Anypoint Connectors
- Anypoint Studio

Before creating an app, you must:

- Have an Anypoint Platform account.
- Have a Maximo Server to access the target resources.
- Understand how to create a Mule app using Design Center or Anypoint Studio.

## Setup

Add this dependency to your application pom.xml

```
<groupId>works.integration</groupId>
<artifactId>maximo-mule-connector</artifactId>
<version>1.0.0</version>
<classifier>mule-plugin</classifier>
```

## Configuration

| Parameter       | Sample                |
| --------------- | --------------------- |
| Server host     | maximo-demo75.mro.com |
| Server port     | 443                   |
| Server basepath | /maximo/oslc          |
| Username        | maximo                |
| Password        | maximo1               |
| Protocol        | HTTPS                 |

## Deploying to Exchange

The Mule Pi Historian Connector can be deployed to an Exchange with following steps.

1. Update the connector pom.xml file

   * Change the `groupId` value to the Organization Id 


     ```
     <modelVersion>4.0.0</modelVersion>
     <groupId>xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx</groupId>
     <artifactId>maximo-mule-connector</artifactId>
     <version>1.0.0</version>
     <packaging>mule-extension</packaging>
     <name>Maximo Connector</name>
     <description>A Mule extension that provides functionality to interact with the IBM Maximo system.</description>
     
     ```

   * Update `distributionManagement` to point to the Exchange Repository (Uncomment these lines)

     ```
     <distributionManagement>
       <snapshotRepository>
         <id>exchange-repository</id>
         <name>Exchange Repository</name>
         <url>https://maven.anypoint.mulesoft.com/api/v1/organizations/${pom.groupId}/maven</url>
         <layout>default</layout>
       </snapshotRepository>
       <repository>
         <id>exchange-repository</id>
         <name>Exchange Repository</name>
         <url>https://maven.anypoint.mulesoft.com/api/v1/organizations/${pom.groupId}/maven</url>
         <layout>default</layout>
       </repository>
     </distributionManagement>
     ```

2. Configure your `~/.m2/settings.xml` file with your Exchange credentials

   ```
   <servers>
    <server>
      <id>exchange-repository</id>
      <username>USERNAME</username>
      <password>PASSWORD</password>
    </server>
   </servers>
   
   ```

3. Execute `mvn deploy` to publish to Exchange

## References

To use the connecter see reference: [Maximo Connector Reference](http://example.com/)

For more information see: [Maximo Web API Reference](https://www.ibm.com/support/pages/system/files/inline-files/Maximo_NextGen_REST_API_-_nextgen.pdf)