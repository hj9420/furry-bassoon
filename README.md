# Sonar Qube

### Window Pre-Work
> This will have to be executed everytime wsl restarts or your computer reboots.
> WARNING: 
```sh 
wsl -d docker-desktop
/etc/sysctl.conf
vm.max_map_count=262144
```

### How to scan using Gradle
> Add the below to your gradle build file
```groovy
plugins {
  id "org.sonarqube" version "3.3"
}
```
### Starting the Sonar Instance No Daemon
```sh
docker-compose up 
```
### Starting the Sonar Instance Daemon (Background)
```sh
docker-compose up -d 
```

> Windows 
>  -Dsonar.login=e6e909d264c42c28ec1bd8e56d0135eb1c9cd323 (Token has to be genrated by the sonar instance)
```sh
./gradlew.bat sonarqube \
  -Dsonar.projectKey=Lively \
  -Dsonar.host.url=http://localhost:9005 \
  -Dsonar.login=e6e909d264c42c28ec1bd8e56d0135eb1c9cd323
 ```
 or 
 > Linux / Linux Subsystem
 ```sh
./gradlew sonarqube \
  -Dsonar.projectKey=Lively \
  -Dsonar.host.url=http://localhost:9005 \
  -Dsonar.login=e6e909d264c42c28ec1bd8e56d0135eb1c9cd323
 ```
> Default sonar user/password is admin/admin
