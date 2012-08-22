# Introduction

This is an extension to JTcl that implements all the operators F5 added to the TCL language.

# Background

# Getting test classes from jtcl

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

# Building

