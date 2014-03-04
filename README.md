xtend-gradle-plugin
===================

[![Build Status](https://oehme.ci.cloudbees.com/buildStatus/icon?job=xtend-gradle-plugin)](https://oehme.ci.cloudbees.com/job/xtend-gradle-plugin/)

A gradle plugin for building Xtend projects

Features
--------

- Compiles Xtend sources to Java
- Enhances Java classes with Xtend debug information
- Automatically downloads the correct Xtend compiler based on which version of xtend.lib you use
- Supports both normal Java projects and the new Android build system
- Hooks into 'gradle eclipse', so the Xtend compiler is configured for your project when you import it into Eclipse

Usage
------

Add the plugins to your build classpath

    buildscript {
      repositories {
        mavenCentral()
      }
      dependencies {
        classpath 'org.xtend:xtend-gradle-plugin:0.0.2'
      }
    }

For normal Java projects add 

    apply plugin: 'xtend'

This will automatically apply the 'java' and 'eclipse' plugins, too.
  
If you are using the new Android build system, add

    apply plugin: 'xtend-android'

This will not apply anything else, because there are different android plugins for apps and libraries. Just choose yourself. Also this will not generate Eclipse metadata, since the new Android build system is currently only supported by Android Studio.
    
Now you just need xtend.lib and start coding.

    repositories {
    	mavenCentral()
    }
    
    dependencies {
      //or testCompile if you only want to use Xtend for some tests
      compile 'org.eclipse.xtend:org.eclipse.xtend.lib:2.5.2'
    }
