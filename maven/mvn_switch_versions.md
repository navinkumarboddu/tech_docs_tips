# Switch Between Maven Versions

#java #codequality #spotless

To install maven follow instructions here : [Install Maven Using SDK](https://github.com/navinkumarboddu/tech_docs_tips/blob/main/java/install_maven_using_sdk.md)

#### Switch Between Maven Versions:
Once you have multiple versions of Maven installed, you can easily switch between them using SDKMAN!. Use the following command to set a specific version of Maven as the default:

```bash
sdk use maven <version>
```

For example:

```bash
sdk use maven 3.8.4
```

#### Verify Maven Version: 
To verify that the correct version of Maven is being used, you can use the following command:

```bash
mvn -version
```

This command will display the version of Maven currently in use.

#### List Installed Maven Versions: 
To list all installed versions of Maven, you can use the following command:

```bash
sdk list maven
```

This command will display a list of all installed Maven versions, including the default version.

By following these steps, you can easily manage multiple versions of Maven using SDKMAN!. This can be particularly useful when working on different projects that require different versions of Maven or when testing compatibility with different Maven versions.

