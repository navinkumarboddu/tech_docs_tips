# Code formatting with Spotless Plugin

#java #codequality #spotless

To install maven follow instructions here : [Install Maven Using SDK](https://github.com/navinkumarboddu/tech_docs_tips/blob/main/java/install_maven_using_sdk.md)

To add the Spotless plugin to your Maven project, you need to modify your pom.xml file to include the Spotless plugin configuration. Here's a basic example of how you can do this:

```xml
<project>
    ...
    <build>
        <plugins>
            <!-- Other plugins here -->
            <plugin>
                <groupId>com.diffplug.spotless</groupId>
                <artifactId>spotless-maven-plugin</artifactId>
                <version>2.43.0</version>
                <executions>
                    <execution>
                        <id>format</id>
                        <goals>
                            <goal>apply</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
    ...
</project>
```

In this configuration:

* **com.diffplug.spotless:spotless-maven-plugin** is the Spotless Maven plugin. Here `2.43.0` is the latest version, follow this link for [latest version](https://mvnrepository.com/artifact/com.diffplug.spotless/spotless-maven-plugin)
* The **<_executions_>** section specifies when the plugin should run. In this case, it's set up to run during the **apply** phase. 
* The **<_configuration_>** section allows you to define formatting rules. You can specify different formatting rules for different file types for our case we have not included configuration here.

Once you've added this configuration to your `pom.xml`, you can run :
* To format all files correctly: `mvn clean spotless:apply`
* To check for errors: `mvn clean spotless:check`