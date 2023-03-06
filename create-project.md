# Maven project creation

## Maven in 5 Minutes
Maven can be used to efficiently generate a java maven project ready for use.
https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html 


## Creation of Integration-test project
Generate project
<pre>
mvn archetype:generate -DgroupId=com.example -DartifactId=integration-tests -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
</pre>

Extend the pom.xml file with configurations for the maven failsafe plugin

```
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-failsafe-plugin</artifactId>
            <version>3.0.0-M5</version>
            <executions>
                <execution>
                    <goals>
                        <goal>integration-test</goal>
                        <goal>verify</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```
