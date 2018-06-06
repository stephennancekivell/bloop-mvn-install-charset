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


# log mvn ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall -e
```
[INFO] Error stacktraces are turned on.
[INFO] Scanning for projects...
[INFO] 
[INFO] -----------------------------< group:art >------------------------------
[INFO] Building art 1.0-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall (default-cli) @ art ---
[WARNING] The POM for org.scala-lang:scala-library:jar:2.12.5 is missing, no dependency information available
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.098 s
[INFO] Finished at: 2018-06-07T09:16:03+10:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall (default-cli) on project art: Unable to parse configuration of mojo ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall for parameter charset: Cannot find 'charset' in class bloop.integrations.maven.BloopMojo -> [Help 1]
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to execute goal ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall (default-cli) on project art: Unable to parse configuration of mojo ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall for parameter charset: Cannot find 'charset' in class bloop.integrations.maven.BloopMojo
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:213)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:154)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:146)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:117)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:81)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:56)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:128)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:305)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:192)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:105)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:956)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:290)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:194)
    at sun.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:498)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:289)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:229)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:415)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:356)
Caused by: org.apache.maven.plugin.PluginConfigurationException: Unable to parse configuration of mojo ch.epfl.scala:maven-bloop_2.12:1.0.0-M10+75-405896f4:bloopInstall for parameter charset: Cannot find 'charset' in class bloop.integrations.maven.BloopMojo
    at org.apache.maven.plugin.internal.DefaultMavenPluginManager.populatePluginFields (DefaultMavenPluginManager.java:664)
    at org.apache.maven.plugin.internal.DefaultMavenPluginManager.getConfiguredMojo (DefaultMavenPluginManager.java:596)
    at bloop.integrations.maven.MojoImplementation$.initializeMojo (MojoImplementation.scala:33)
    at bloop.integrations.maven.MojoImplementation.initializeMojo (MojoImplementation.scala)
    at bloop.integrations.maven.BloopMojo.execute (BloopMojo.java:62)
    at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo (DefaultBuildPluginManager.java:137)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:208)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:154)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:146)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:117)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:81)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:56)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:128)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:305)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:192)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:105)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:956)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:290)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:194)
    at sun.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:498)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:289)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:229)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:415)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:356)
Caused by: org.codehaus.plexus.component.configurator.ComponentConfigurationException: Cannot find 'charset' in class bloop.integrations.maven.BloopMojo
    at org.eclipse.sisu.plexus.CompositeBeanHelper.setProperty (CompositeBeanHelper.java:252)
    at org.codehaus.plexus.component.configurator.converters.composite.ObjectWithFieldsConverter.processConfiguration (ObjectWithFieldsConverter.java:101)
    at org.codehaus.plexus.component.configurator.BasicComponentConfigurator.configureComponent (BasicComponentConfigurator.java:34)
    at org.apache.maven.plugin.internal.DefaultMavenPluginManager.populatePluginFields (DefaultMavenPluginManager.java:634)
    at org.apache.maven.plugin.internal.DefaultMavenPluginManager.getConfiguredMojo (DefaultMavenPluginManager.java:596)
    at bloop.integrations.maven.MojoImplementation$.initializeMojo (MojoImplementation.scala:33)
    at bloop.integrations.maven.MojoImplementation.initializeMojo (MojoImplementation.scala)
    at bloop.integrations.maven.BloopMojo.execute (BloopMojo.java:62)
    at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo (DefaultBuildPluginManager.java:137)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:208)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:154)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:146)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:117)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:81)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:56)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:128)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:305)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:192)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:105)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:956)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:290)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:194)
    at sun.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:498)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:289)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:229)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:415)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:356)
[ERROR] 
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginConfigurationException

```