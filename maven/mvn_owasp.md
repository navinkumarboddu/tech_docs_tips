# Integrate OWASP Dependency Check with Maven

Why is it Important
As Java developers, we all know how much we rely on dependencies on our daily job. With the ease of Maven (or Gradle), we can easily add so many dependencies whenever we need it. This though, might bring bad impact in our code security if not managed well. Some libraries, albeit published, might have security issues that we as developers need to be aware of.

Keeping up-to-date with all the security fixes or vulnerabilities from plethora of libraries most likely is quite hard for us as a developer. Hence, the importance of the OWASP dependency check tool. Furthermore, we can integrate this with our CI/CD pipeline that can stop the build process when it found any security issue reported in one of our dependencies.



<plugin>
	<groupId>org.owasp</groupId>
	<artifactId>dependency-check-maven</artifactId>
	<version>9.0.9</version>
	<executions>
		<execution>
			<goals>
				<goal>check</goal>
			</goals>
		</execution>
	</executions>
</plugin>
