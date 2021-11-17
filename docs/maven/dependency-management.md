# Dependency management

The best place to configure the version of the dependencies you use is in the dependency management part of your POM file.
In a multi-module project, this is typically configured in a parent POM from which all other POM's inherit.

``` xml linenums="1"
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>1.7.32</version>
        </dependency>
    </dependencies>
</dependencyManagement>
```

## Bill of Materials

The dependency management part of your POM file is also where you can import BOM files.
BOM files define a consistent version for all the artifacts from one "library".

See [Bill of Materials](bill-of-materials.md).

--8<-- "includes/abbreviations.md"
