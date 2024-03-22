# Integrate OWASP Dependency Check with Maven for Developer

Why is it Important
As Java developers, we all know how much we rely on dependencies on our daily job. With the ease of Maven (or Gradle), we can easily add so many dependencies whenever we need it. This though, might bring bad impact in our code security if not managed well. Some libraries, albeit published, might have security issues that we as developers need to be aware of.

Keeping up-to-date with all the security fixes or vulnerabilities from plethora of libraries most likely is quite hard for us as a developer. Hence, the importance of the OWASP dependency check tool. Furthermore, we can integrate this with our CI/CD pipeline that can stop the build process when it found any security issue reported in one of our dependencies.

The tool has been built using the [OWASP dependency check project](https://owasp.org/www-project-dependency-check/), which help us in addressing security vulnerabilities in third-party components used in our products.

###### Step 1 : 
To start, the dependency check plugin for Maven itself can be easily configured inside the plugin section inside our pom.xml file under build section. Below is the simplest element to add the dependency check into our pom.xml. Also, this plugin can be added to main pom.xml file or under each module's pom.xml file.

```xml
<plugin>
	<groupId>org.owasp</groupId>
	<artifactId>dependency-check-maven</artifactId>
	<version>9.0.10</version>
	<executions>
		<execution>
			<goals>
				<goal>check</goal>
			</goals>
		</execution>
	</executions>
</plugin>
```

As of this writing, the latest available version of the dependency check plugin is 9.0.10, hence the version inside the pom.xml.

###### Step 2: 
Run the mvn clean install on the repo.

###### Step 3: 
Run the mvn dependency-check:check on the repo, this will generate the reports in the target folder with filename "dependency-check-report.html" in each module.

###### Step 4: 
To view the OWASP reports you can use any simple server or run the command - `python -m http.server 8000` or `python3 -m http.server 8000` and browse http://localhost:8000 in the browser

###### Step 5: 
View the report for example `http://localhost:8000/<project-name>/target/` and Click on the "dependency-check-report.html" to view the report.
