# itech-maven-utility-project

This repo contains two sample projects Utils & UtilityCenter.

**Utils** project will create non executable JAR file using following command

```sh
> mvn clean install
```
**UtilityCenter** project will create an executable JAR using maven-shade-plugin

```sh
> mvn clean package
> java -jar target/UtilityCenter-1.0.SNAPSHOT
```

## Utils

Creates a non executable **JAR** file. It contains the following dependencies

```xml
<dependencies>
        <dependency>
            <groupId>org.apache.commons</groupId>
            <artifactId>commons-lang3</artifactId>
            <version>3.10</version>
        </dependency>

        <dependency>
            <groupId>org.apache.httpcomponents</groupId>
            <artifactId>httpclient</artifactId>
            <version>4.5.12</version>
        </dependency>
    </dependencies>
```

## UtilityCenter

Creates a executable **JAR** file using **maven-shade-plugin**

```xml
<build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-shade-plugin</artifactId>
                <version>3.2.4</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>shade</goal>
                        </goals>
                        <configuration>
                            <shadedArtifactAttached>false</shadedArtifactAttached>
                            <transformers>
                                <transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
                                    <mainClass>com.iamvickyav.Utility</mainClass>
                                </transformer>
                            </transformers>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
        </plugins>
 </build>
 ``` 
