# Introduction

This is an extension to [JTcl](http://jtcl.kenai.com/) that implements all the functionality F5 added to the Tcl language.

# Download binary

Instead of building this project yourself, you can download the binary from [Release v 0.9 ](https://github.com/landro/jtcl-irule/releases/tag/v0.9)

# Building

Fetch the [source](https://hg.kenai.com/hg/jtcl~jtcl-main) of [JTcl](http://jtcl.kenai.com/) using mercurial and replace the maven-jar-plugin config with the following in order to generate the test jar 

     <plugin>
        <artifactId>maven-jar-plugin</artifactId>
        <version>2.2</version>
        <executions>
          <execution>
            <id>default-jar</id>
            <phase>package</phase>
            <goals>
              <goal>jar</goal>
            </goals>
            <configuration>
              <archive>
                <manifest>
                  <mainClass>tcl.lang.Shell</mainClass>
                </manifest>
                <manifestEntries />
              </archive>
            </configuration>
          </execution>
          <execution>
            <goals>
              <goal>test-jar</goal>
            </goals>
          </execution>
        </executions>
      </plugin>

If you're using Mac Os X and don't have mercurial installed, I recommend using the [Source Tree](http://www.sourcetreeapp.com/) app from the app store.
It has excellent support for both git and mercurial.
The next step, is to build and install the artifacts into your local maven repository using

    mvn clean install -DskipTests

WARNING! you have to use JDK version 1.6. You can achieve this by setting JAVA_HOME appropriately.
    
Next, fetch the source code of this project, and align the _jtcl.version_ property in _pom.xml_in with the JTcl version. Then, build the project using:

    mvn clean package

This will generate a jar file named *jtcl-irule.jar* in the _target_ directory.
This jar file has to be added to the classpath of the JTcl shell script in order to override som of the functionality found in JTcl.
Place it in front of the other jar file - it will take precedence. See TesTcl installation instructions for details.

# What has been implemented so far

All the special iRule operators have now been implemented!

Original JTcl source code was modified in order to support the following iRule operators:

__iRule only operators__

- *starts_with* Tests if one string starts with another string
- *ends_with* Tests if one string ends with another string
- *contains* Tests if one string contains another string
- *matches_glob* Implement glob style matching within a comparison
- *matches_regex* Tests if one string matches a regular expression

__iRule aliases to standard Tcl operators__

- *equals* Tests if one string equals another string (*eq* operator)
- *and* Performs a logical "and" comparison between two values (*&&* operator)
- *or* Performs a logical "or" comparison between two values (*||* operator)
- *not* Performs a logical "not" on a value (*!* operator)

The only files that have been modified are:

- Expr.java
- expr.test


# License
Both jtcl-irule and JTcl are released under a BSD-style license. 