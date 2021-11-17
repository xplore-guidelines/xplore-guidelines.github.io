# PMD

We recommend running Checkstyle on every build.
Add the [Maven PMD Plugin ↗](https://maven.apache.org/plugins/maven-pmd-plugin/) to your parent POM.

``` xml linenums="1"
<plugin>
    <artifactId>maven-pmd-plugin</artifactId>
    <configuration>
        <includeTests>true</includeTests>
        <linkXRef>false</linkXRef>
        <printFailingErrors>true</printFailingErrors>
        <rulesets>pmd.xml</rulesets>
    </configuration>
    <executions>
        <execution>
            <id>pmd</id>
            <phase>process-test-classes</phase>
            <goals>
                <goal>check</goal>
                <goal>cpd-check</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

???+ tip

    If necessary, you can disable the PMD plugin for a specific build by adding `-Dpmd.skip` to the command line.

## Exclude folders

It is often usesful to exclude certain folders from the PMD analysis.
For example folders that contain generated code.

``` xml linenums="1"
<configuration>
    <excludeRoots>
        <excludeRoot>${project.build.directory}/generated-sources</excludeRoot>
        <excludeRoot>${project.build.directory}/generated-test-sources</excludeRoot>
    </excludeRoots>
</configuration>
```

## Local configuration

## Global configuration

When working on more than one codebase where you want to keep the PMD configuration consistent, you can consider packaging and releasing the `pmd.xml` configuration file as a separate artifact.
Add a dependency to the new artifact and point to the shared configuration file.

``` xml linenums="1"
<plugin>
    <artifactId>maven-pmd-plugin</artifactId>
    <configuration>
        <configLocation>pmd.xml</configLocation>
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