To set up Apache Axis2 from scratch (without using the default Axis2 WAR) and deploy only your service on Tomcat 10 or above, follow the steps below. This guide ensures that you avoid Jakarta EE compatibility issues and build a minimal Axis2 service that runs in Tomcat 10+ with Java 17+.

✅ Overview

*  Apache Axis2 no longer actively maintains a Jakarta EE 9+ compatible WAR, so direct deployment of the Axis2 webapp often fails on Tomcat 10+.

* Solution: Instead of using the Axis2 WAR, we will:
  * Build a standalone Axis2 service (AAR file).
  * Embed Axis2 runtime inside a custom web application.
  * Package the service with minimal configuration.
  * Ensure compatibility with Tomcat 10+ and Java 17+.

## Step-by-Step Setup
🔹1. Download Required Libraries

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