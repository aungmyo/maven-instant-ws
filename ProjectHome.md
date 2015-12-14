Tools for rapid development of web services using Maven and JAX-WS

## Creating a Web Service project using instantws-archetype ##

```
mvn archetype:generate
    -DarchetypeCatalog=http://maven-instant-ws.googlecode.com/svn/repo/archetype-catalog.xml
```

## pom.xml Example: Building WSDL from XSD ##

```
<build>

	<plugin>
		<groupId>regm</groupId>
		<artifactId>maven-wsdl-builder-plugin</artifactId>
		<version>0.1</version>
		<executions>
			<execution>
				<goals>
					<goal>generate-wsdl</goal>
				</goals>
				<configuration>
					<xsdDirectory>
						${basedir}/src/main/resources/xsd
					</xsdDirectory>

					<wsdlDestDirectory>
						${project.build.directory}/generated-sources/WEB-INF/wsdl
					</wsdlDestDirectory>
				</configuration>
			</execution>
		</executions>
	</plugin>

</build>

<pluginRepositories>

	<pluginRepository>
		<id>maven-instant-ws-repo</id>
		<name>maven-instant-ws repository</name>
		<url>http://maven-instant-ws.googlecode.com/svn/repo/</url>
	</pluginRepository>

</pluginRepositories>
```