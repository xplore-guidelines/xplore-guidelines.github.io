# Bill of Materials

BOM stands for Bill of Materials.
A BOM is a special kind of POM that is used to control the versions of a set of related artifacts.
The file provides a central place to define and update those versions.

Whenever a framework or library you depend on provides a BOM file, it is the preferred way to introduce that dependency into your project.

``` xml linenums="1"
<dependencyMangement>
    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</group>
            <artifactId>spring-cloud-dependencies</artifactId>
            <version>2020.0.4</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>
    </dependencies>
</dependencyMangement>
```

## Examples

The following frameworks and libraries that we often use provide a BOM file.
When adding a new framework or library, check if a BOM file is provided.

- Apache CXF
- Quarkus
- Spring Boot
- Spring Cloud
- Spring Framework
- Testcontainers

--8<-- "includes/abbreviations.md"
