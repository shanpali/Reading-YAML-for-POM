# Reading-YAML-for-POM
passing any parameter from Yaml file and referencing it in your POM.xml

# Yaml-Properties Maven Plugin
***A Yaml extension of the MojoHaus Properties Maven Plugin v.1.0.1***


**Continuous Integration:**<br />
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/it.ozimov/yaml-properties-maven-plugin/badge.svg)](https://maven-badges.herokuapp.com/maven-central/it.ozimov/yaml-properties-maven-plugin)
<br />
[![Build Status](https://travis-ci.org/ozimov/yaml-properties-maven-plugin.svg?branch=master)](https://travis-ci.org/ozimov/yaml-properties-maven-plugin)


## How to use it?

This extension provides capability to import content from a yaml file into your pom.
To this end, you should read the instructions for the [properties-maven-plugin](http://www.mojohaus.org/properties-maven-plugin/).

Just rememeber that current release is **version 1.1.3**. To use it in Maven, replace the following code

```xml
<groupId>org.codehaus.mojo</groupId>
<artifactId>properties-maven-plugin</artifactId>
<version>1.0.0</version>
```

with:

```xml
<groupId>it.ozimov</groupId>
<artifactId>yaml-properties-maven-plugin</artifactId>
<version>1.1.3</version>
```

## Example of usage:
```xml
<plugin>
    <groupId>it.ozimov</groupId>
    <artifactId>yaml-properties-maven-plugin</artifactId>
    <version>LATES</version>
    <executions>
        <execution>
            <phase>initialize</phase>
            <goals>
                <goal>read-project-properties</goal>
            </goals>
            <configuration>
                <files>
                    <file>config/my_configuration.yaml</file>
                </files>
            </configuration>
        </execution>
    </executions>
</plugin>
```
And then usage in the pom as 
```xml
 <plugin>
    <groupId>some groupId</groupId>
    <artifactId>some artifactId</artifactId>
    <version>X.Y.Z</version>
    <configuration>
        <cfg_1>${my_yaml_key}</cfg_1>
    </configuration>
</plugin>
```
