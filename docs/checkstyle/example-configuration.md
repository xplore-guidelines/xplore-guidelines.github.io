# Example configuration

``` xml linenums="1"
<?xml version="1.0" encoding="UTF-8"?>

<!DOCTYPE module PUBLIC
        "-//Checkstyle//DTD Checkstyle Configuration 1.3//EN"
        "https://checkstyle.org/dtds/configuration_1_3.dtd">

<module name="Checker">
    <property name="charset" value="UTF-8"/>

    <module name="FileTabCharacter">
        <property name="eachLine" value="true"/>
    </module>

    <module name="LineLength">
        <property name="max" value="120"/>
    </module>

    <module name="OrderedProperties"/>

    <module name="UniqueProperties"/>
</module>
```
