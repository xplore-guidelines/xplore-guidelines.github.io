# Whitespace checks

## File tab character

Code can be indented using tabs or spaces.
Make sure your team picks one indentation style and sticks with it.
Operations like code merges will be much easier if everyone uses the same style.

If the code is indented with spaces, it is a good idea to use this check to reject lines containing a tab character.

``` xml linenums="1" title="checkstyle.xml"
<module name="Checker">
    <module name="FileTabCharacter">
        <property name="eachLine" value="true"/>
    </module>
</module>
```

If necessary, you can limit the scope of this Check to files with specific extensions (e.g. java).

``` xml linenums="1" title="checkstyle.xml"
<module name="Checker">
    <module name="FileTabCharacter">
        <property name="eachLine" value="true"/>
        <property name="fileExtensions" value="java"/>
    </module>
</module>
```
