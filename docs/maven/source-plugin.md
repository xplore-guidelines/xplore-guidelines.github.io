# Source plugin

When building shared components, e.g. a JAR file published to an internal Maven repository, configure the Maven source plugin to attach an additional JAR file containing the projects sources.


``` xml linenums="1" title="pom.xml"
<plugin>
    <artifactId>maven-source-plugin</artifactId>
    <executions>
        <execution>
            <goals>
                <goal>jar</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

--8<-- "includes/abbreviations.md"
