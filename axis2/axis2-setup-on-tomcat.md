To set up Apache Axis2 from scratch (without using the default Axis2 WAR) and deploy only your service on Tomcat 10 or above, follow the steps below. This guide ensures that you avoid Jakarta EE compatibility issues and build a minimal Axis2 service that runs in Tomcat 10+ with Java 17+.

✅ Overview

*  Apache Axis2 no longer actively maintains a Jakarta EE 9+ compatible WAR, so direct deployment of the Axis2 webapp often fails on Tomcat 10+.

* Solution: Instead of using the Axis2 WAR, we will:
  * Build a standalone Axis2 service (AAR file).
  * Embed Axis2 runtime inside a custom web application.
  * Package the service with minimal configuration.
  * Ensure compatibility with Tomcat 10+ and Java 17+.

## Step-by-Step Setup
### 1. Download Required Libraries

#### 1. Axis2 Binary Distribution (not the WAR):
   * Download from: https://axis.apache.org/axis2/java/core/download.html
     * Unzip, e.g., to: C:\axis2-1.8.2

#### 2. Create your project structure:
```pgsql
    Axis2TomcatApp/
    ├── build/
    ├── lib/              ← Axis2 libraries
    ├── services/
    │   └── MyService/
    │       ├── META-INF/
    │       │   └── services.xml
    │       └── com/example/MyService.class
    ├── src/
    ├── webapp/
    │   ├── WEB-INF/
    │   │   ├── web.xml
    │   │   └── lib/
    │   └── index.jsp
    └── build.xml / pom.xml
 ```

#### 3. Copy Axis2 core JARs to webapp/WEB-INF/lib/:
    
From your Axis2 download:

* Copy all JARs from axis2-1.8.2/lib into webapp/WEB-INF/lib/

### 2. Write Your Service Class

Create a simple service in Java:

```java
    // src/com/example/MyService.java
    package com.example;
    
    public class MyService {
        public String sayHello(String name) {
        return "Hello, " + name + "!";
        }
    }
```

Compile it and place the .class file into services/MyService/com/example/.

### 3. Create the services.xml

This file declares your service:

```xml
    <!-- services/MyService/META-INF/services.xml -->
    <service name="MyService" scope="application">
        <description>My Hello Service</description>
        <messageReceivers>
            <messageReceiver
                mep="http://www.w3.org/2004/08/wsdl/in-only"
                class="org.apache.axis2.rpc.receivers.RPCInOnlyMessageReceiver" />
            <messageReceiver
                mep="http://www.w3.org/2004/08/wsdl/in-out"
                class="org.apache.axis2.rpc.receivers.RPCMessageReceiver" />
        </messageReceivers>
        <parameter name="ServiceClass">com.example.MyService</parameter>
    </service>
```

### 4. Package the Service as `.aar`

An `.aar` file is simply a ZIP archive with a `.aar` extension.

Create `MyService.aar`:

```
    cd services/MyService
    jar cvf MyService.aar *
 ```

Place `MyService.aar` in:
```declarative
webapp/WEB-INF/services/
```

5. Create `web.xml` for the Custom Web App

Here, we embed AxisServlet and set up the Axis2 environment:

```declarative
<!-- webapp/WEB-INF/web.xml -->
<web-app xmlns="https://jakarta.ee/xml/ns/jakartaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="https://jakarta.ee/xml/ns/jakartaee
                             https://jakarta.ee/xml/ns/jakartaee/web-app_5_0.xsd"
         version="5.0">

    <display-name>Axis2 Service App</display-name>

    <servlet>
        <servlet-name>AxisServlet</servlet-name>
        <servlet-class>org.apache.axis2.transport.http.AxisServlet</servlet-class>
        <load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
        <servlet-name>AxisServlet</servlet-name>
        <url-pattern>/services/*</url-pattern>
    </servlet-mapping>
</web-app>
```

📝 Note: We are directly registering the Axis2 servlet rather than deploying the default Axis2 WAR.

### 6. Build WAR and Deploy to Tomcat

Create WAR:
```
cd webapp
jar cvf Axis2App.war *
```

Deploy:

* Place Axis2App.war into TOMCAT_HOME/webapps/
* Start Tomcat:
```declarative
CATALINA_HOME/bin/startup.sh
```

Access your service:
```declarative
http://localhost:8080/Axis2App/services/MyService?wsdl
```

### 7. Call the Service (Optional Test)

Use `curl`, SoapUI, or a browser to test the WSDL.

Example response:

```declarative
<definitions ... >
  <service name="MyService">
    <port name="MyServiceSOAP11port_http" ... >
      ...
    </port>
  </service>
</definitions>
```