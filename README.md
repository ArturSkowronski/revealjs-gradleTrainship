#Gradle
###Build Tool for Java
Created by [Artur Skowronski](http://hibari.eu) /
[@ArturSkowronski](http://twitter.com/ArturSkowronski)

##Heads Up
Gradle is a flexible general purpose build tool like Ant, with build-by-convention Maven style. 

##Pros
* Powerful support for multi-project builds
* Powerful dependency management
* Full support for your existing Maven or Ivy repositories
* Ant tasks and builds as first class citizens

##Prerequisites
* _JDK 1.5_ or higher
* add _GRADLE_HOME/bin_ to your PATH environment 
variable
* ... or use fabolous gradle wrapper :)

##Structure
Domain Specific Language (DSL) based on Groovy.

##Sample 1 - Hello World
* Default name of build script is _build.gradle_
* _-q_ option disable gradle logs
* first run is slow - gradle needs to fork JVM for itself
* everything in body (it will be discussed during lifecycle sample) will be executed before doLast && doFirst
* _<<_ is a shortcut for doLast

##Sample 2 - Hello World with variables
* You can use variables in your tasks
* You can make variables external using _ext_ namespace
* External  variables need to be in 
* You can use groovy standard libraries
* You can use groovy syntax sugar
* _$it_ in loop count iteration

##Sample 3 - Task Dependencies
* You can provide _defaultTask_ which is run if no task is provided by CLI
* When task depends on other task, the other one will be executed before.
* Thanks to groovy syntax, you can create tasks dynamically
* You can depend on dynamically created task
* You can add dependcy dynamicaly to dynamically created task (magic :))

##Sample 4 - Methods
* You can create reusable methods

##Sample 5 - Lifecycle
* Gradle has three lifecycle phases: initialization, configuration && execution
* Initialization phase executes actions from settings file like chaecking project dependencies
* Configuration phase of each task is always run
* Gradle will run only execution phase of provided tasks

##Sample 6 - Multimodule
* You can add another project to your build using _settings.gradle_
* works as next leaf in project tree
* you can change configuration on runtime in initialization phase
* parent can run tasks in child context
* parent can run tasks in all childs context using _allproject_ directive
* parent can run additional tasks in all childs context using _subproject_ directive

##Sample 7 - Java Library
* To add support to Java, you need apply Java plugin to your _build.gradle_ file
* Java plugin has its own lifecycle
* Out-of-the-box, you can create war & jar files
* You can add dependencies which will be automatically esolved with Ivy
* We can generate java project with this all with command 
	gradle setupBuild --type java-library 
it generate valid maven structure..
* ...or even use 
	gradle setupBuild --type pom
to create maven project

<h1>THE END</h1>
<h3>Artur Skowronski</h3>

