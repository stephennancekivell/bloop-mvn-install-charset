# how to get unknown charset from mvn bloopInstall


```
[ERROR] Failed to execute goal ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall (default-cli) on project art: Unable to parse configuration of mojo ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall for parameter charset: Cannot find 'charset' in class bloop.integrations.maven.BloopMojo -> [Help 1]
```

# steps to build project
* create new scala project from mvn archetype
* delete src/test, upgrade scala-maven-plugin to 3.2.2
* add configuration.charset to pom.
* bloopInstall will crash
* remove configuration.charset
* bloopInstall will pass

# run bloopInstall
```
mvn ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall 
```