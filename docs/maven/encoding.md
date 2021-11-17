Always configure the source and output encoding for Maven to avoid the default platform encoding from influencing the build outcome.
UTF-8 is the de-facto standard.

```xml linenums="1" title="pom.xml"
<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
</properties>
```

If you don't specify these properties, a warning usually appears in the build output.

???+ tip

    If your project inherits from the `spring-boot-starter-parent` POM, these properties are already configured.

--8<-- "includes/abbreviations.md"
