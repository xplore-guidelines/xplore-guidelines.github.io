# Require Plugin Versions

Relying on the default plugin versions from a particular Maven version is a bad practice.
Always define the version of every plugin used by the build to guarantee build reproducibility.
Configure the `maven-enforcer-plugin` to fail the build if a plugin is used without specifying the version to use.

``` xml linenums="1"
<plugin>
    <artifactId>maven-enforcer-plugin</artifactId>
    <configuration>
        <rules>
            <requirePluginVersions/>
        </rules>
    </configuration>
</plugin>
```

???+ tip

    A good  practice is to specify plugin version in the `<pluginManagement/>` element of a parent POM.

--8<-- "includes/abbreviations.md"
