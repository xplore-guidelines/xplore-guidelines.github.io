# Ban Duplicate Dependencies

Duplicate dependencies are dependencies that have the same `groupId`, `artifactId`, `type` and `classifier`.
Configure the `maven-enforcer-plugin` to fail the build if duplicate dependencies are found.

``` xml linenums="1" title="pom.xml"
<plugin>
    <artifactId>maven-enforcer-plugin</artifactId>
    <configuration>
        <rules>
            <banDuplicatePomDependencyVersions/>
        </rules>
    </configuration>
</plugin>
```

--8<-- "includes/abbreviations.md"
