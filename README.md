# Introduction

This is an extension to [JTcl](http://jtcl.kenai.com/) that implements all the functionality F5 added to the Tcl language.

# Building

Fetch the [source](https://hg.kenai.com/hg/jtcl~jtcl-main) of [JTcl](http://jtcl.kenai.com/) from its mercurial repo and replace the maven-jar-plugin config with the following in order to generate the test jar 

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

If you're using Mac Os X and don't have mercurial installed, I recommend using the Source Tree app from the app store. It has support for both git and mercurial.
The next step, is to build and install the artifacts into your local maven repository using

    mvn clean install -DskipTests
    
Next, fetch the source code of this project, and build code using 

    mvn clean install
