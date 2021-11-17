# Miscellaneous checks

## Unique properties

Detects duplicated keys in properties files.
Duplicate keys are usually an error and it is best to avoid them by rejecting them completely.

``` xml linenums="1" title="checkstyle.xml"
<module name="Checker">
    <module name="UniqueProperties"/>
</module>
```

## Ordered properties

Sorted properties make it easy for people to find required properties by name in file. It makes merges more easy. While there are no problems at runtime.

``` xml linenums="1" title="checkstyle.xml"
<module name="Checker">
    <module name="OrderedProperties"/>
</module>
```
