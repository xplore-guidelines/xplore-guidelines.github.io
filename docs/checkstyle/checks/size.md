# Size checks

## Executable statement count

The executable statement count check limits the amount of executable statements per method.

!!! quote "Clean Code"
    Functions should do one thing.
    They should do it well.
    They should do it only.

``` xml linenums="1"
<module name="Checker">
    <module name="TreeWalker">
        <module name="ExecutableStatementCount">
            <property name="max" value="5"/>
        </module>
    </module>
</module>
```

## Method length

The method length check counts the number of lines in a method and asserts that it does not exceed a configured maximum.
Method length check counts every line, even when they belong to one single executable statements like a builder or stream operation spread over multiple lines.
Therefor we prefer to limit the amount of code in one method using the [executable statement count](#executable-statement-count) check.


However the method length check can still provide useful.
We've had customers were an external code audit that heavily relied on static code analysis flagged some methods exceeding 30 lines of code.
Although those methods were very readable and only contained a limited amount of executable statements, they still impacted our overall score.
Setting an upper limit of 30 lines per method can avoid such scenario's.

``` xml linenums="1"
<module name="Checker">
    <module name="TreeWalker">
        <module name="MethodLength">
            <property name="max" value="30"/>
        </module>
    </module>
</module>
```

## Line length

``` xml linenums="1"
<module name="Checker">
    <module name="LineLength">
        <property name="max" value="120"/>
    </module>
</module>
```

If necessary, you can limit the scope of this Check to files with specific extensions (e.g. java).

``` xml linenums="1"
<module name="Checker">
    <module name="LineLength">
        <property name="fileExtensions" value="java"/>
        <property name="max" value="120"/>
    </module>
</module>
```

## Parameter number

!!! quote "Clean Code"
    Functions should have a small number of arguments. 
    No argument is best, followed by one, two, and three. 
    More than three is very questionable and should be avoided with prejudice.

By default the parameter number check allows up to 7 parameters per method.

``` xml linenums="1"
<module name="Checker">
    <module name="TreeWalker">
        <module name="ParameterNumber">
            <property name="ignoreOverriddenMethods" value="true"/>
            <property name="max" value="3"/>
            <property name="tokens" value="METHOD_DEF"/>
        </module>
    </module>
</module>
```

--8<-- "includes/abbreviations.md"
