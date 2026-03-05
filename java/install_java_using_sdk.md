# JAVA
<hr>

The installation guide for SDKMan can be found at: [Installation - SDKMAN! the Software Development Kit Manager](https://github.com/navinkumarboddu/tech_docs_tips/blob/main/java/sdk_install.md).

#### # Afterwards you can list Java versions with

```html
sdk list java
```

#### # And you can install the Temurin Java 17 distribution with

```html
sdk install java <version_no> (or a newer Java 17 version taken from the previous command)
```

You can also install other versions and switch between JDKs with the `sdk use` command.

#### # Check Installed Java Versions

```html
sdk list java | grep installed
```

#### # Use / Switch Between Java Versions

To temporarily switch Java versions for the current terminal session:

```html
sdk use java <version_no>
```

Example:
```html
sdk use java 17.0.10-tem
```

This switch applies only to the current shell session.


#### # Set Default Java Version

To permanently set a Java version as the default:
```html
sdk default java <version_no>
```

Example:
```html
sdk default java 17.0.10-tem
```
This version will be used in all new terminal sessions.

#### # Verify Active Java Version

```html
java -version
```

Example output:
```html
openjdk version "17.0.10" 2024-01-16
OpenJDK Runtime Environment Temurin-17.0.10
OpenJDK 64-Bit Server VM
```

#### # Remove a Java Version

If you want to uninstall a version:
```html
sdk uninstall java <version_no>
```

Example:
```html
sdk uninstall java 17.0.10-tem
```

Quick Example Workflow
```html
sdk list java
sdk install java 17.0.10-tem
sdk install java 21-tem
sdk use java 21-tem
sdk default java 17.0.10-tem
```