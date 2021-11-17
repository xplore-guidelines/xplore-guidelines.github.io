# Compiler warnings

Nobody likes to work on a codebase littered with thousands of compiler warnings.
Compiler warnings call out mistakes and should not be ignored.
Take compiler warnings seriously, and strive to compile warning-free.

## Maven plugin

Configure the [Maven compiler plugin ↗](https://maven.apache.org/plugins/maven-compiler-plugin) to show warnings and deprecations and to fail the build when any warnings or deprecations are found.

Using `-Xlint:all`, you enable all compiler warnings that come with the Java compiler.
Specific compiler warnings can be excluded using `-`.
For example excluding warnings related to annotation processing can be excluded by using `-Xlint:all,-processing`.

``` xml linenums="1"
<plugin>
    <artifactId>maven-compiler-plugin</artifactId>
    <configuration>
        <compilerArgument>-Xlint:all,-processing</compilerArgument>
        <failOnWarning>true</failOnWarning>
        <showDeprecation>true</showDeprecation>
        <showWarnings>true</showWarnings>
    </configuration>
</plugin>
```

## New codebase

When starting from scratch, or when adding a new module to an existing codebase, configure your build tool to immediately fail the build on any warning.
In other words, treat warnings as compilation errors.

## Existing codebase

Applying the technique described above can be difficult in an existing codebase that already contains lots of warnings.
Instead, try to apply the technique module per module, gradually working towards a warning free codebase.
Whenever a new module is added, treat warnings as errors from the start.

Apply the boyscout rule, always leave the code better than you found it.
Never introduce more warnings and never ignore existing warnings. 
Whenever you stumble upon a warning in a piece of code you're working on, clean it up - no excuses.
