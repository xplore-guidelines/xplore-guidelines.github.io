# Checkstyle

We recommend running Checkstyle on every build.

``` xml linenums="1" title="pom.xml"
<plugin>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <configuration>
        <configLocation>checkstyle.xml</configLocation>
        <failOnViolation>true</failOnViolation>
        <logViolationCountToConsole>true</logViolationCountToConsole>
        <logViolationsToConsole>true</logViolationsToConsole>
    </configuration>
    <executions>
        <execution>
            <id>checkstyle</id>
            <phase>validate</phase>
            <goals>
                <goal>check</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

???+ tip

    If necessary, you can disable the Checkstyle plugin for a specific build by adding `-Dcheckstyle.skip` to the command line.

## Checkstyle version

The [Maven Checkstyle Plugin ↗](https://maven.apache.org/plugins/maven-checkstyle-plugin) does not always depend on the latest version of Checkstyle.
For example version 3.1.2 of the plugin depends on version 8.29 of Checkstyle while version 9.1 has already been released.
New versions of Checkstyle often include new checks and bug fixes for existing checks.
You can override the default Checkstyle version used by the Maven plugin.

``` xml linenums="1" title="pom.xml"
<plugin>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <dependencies>
        <dependency>
            <groupId>com.puppycrawl.tools</groupId>
            <artifactId>checkstyle</artifactId>
            <version>9.1</version>
        </dependency>
    </dependencies>
</plugin>
```

## Local configuration



## Global configuration

When working on more than one codebase where you want to keep the coding style consistent, you can consider packaging and releasing the `checkstyle.xml` configuration file as a separate artifact.
Add a dependency to the new artifact and point to the shared configuration file.

``` xml linenums="1" title="pom.xml"
<plugin>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <configuration>
        <configLocation>checkstyle.xml</configLocation>
    </configuration>
    <dependencies>
        <dependency>
            <groupId>be.xplore</groupId>
            <artifactId>code-style</artifactId>
            <version>1.0.0</version>
        </dependency>
    </dependencies>
</plugin>
```

--8<-- "includes/abbreviations.md"
