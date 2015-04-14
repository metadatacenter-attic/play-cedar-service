# play-cedar-service

A sample project showing how to integrate a [Play Framework](http://www.playframework.com/) project with a [Maven](http://maven.apache.org/) build process. 
It will work for both Java- and Scala-based projects.

See [Integrating Play Framework And Maven](http://orrsella.com/2014/02/25/integrating-play-framework-and-maven/) for more information.
This project is derived from the example [play-maven-integration](https://github.com/orrsella/play-maven-integration) project.
It has been updated to work with the current (2.3.8) Activator-based version of Play.

In addition to allowing both Maven and the Play Activator to work together, this project privides an approach for separating 
the Play-based functionality of a service from it core application logic. 

The Maven build is expecting two subdirectories containing the core server code and the Play-based code, respectively.
These two subdirectories should be named using the artifact ID in the base POM.
The sub-project <artifactId>-core contains all non Play server code; the <artifactId>-play contains Play-based functionality.

The steps for taking this project and using it as the basis for a new CEDAR project are:

. Clone the project using Git
. Rename the base directory from play-cedar-service to <new-service>;
. Edit the base POM and change the artifact ID from cedar-service to <new-service>;
  also change the module names in the <modules> section from cedar-service-{core,play} to <new-service>-{core,play}
. Rename the core subdirectory from cedar-service-core to <new-service>-core
. Edit the POM in the core subdirectory and change the artifact ID from cedar-service-core to <new-service>-core;
  change the parent artifact ID from cedar-service to <new-service>
. Rename the Play subdirectory from cedar-service play to <new-service>-play
. Edit the POM in the Play subdirectory and change the artifact ID from cedar-service-play to <new-service>-play;
  change the parent artifact ID from cedar-service to <new-service>. Also change the artifact ID of the core
  dependency from cedar-service-core to <new-service>-core.

