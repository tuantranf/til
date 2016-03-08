# Remote debug with gradle & jetty

## Gradle Options Setting
```bash
$ echo 'export GRADLE_OPTS="-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=9999"' >> ~/.bashrc 
$ source ~/.bashrc
$ ./gradlew jettyRun
Listening for transport dt_socket at address: 9999
:compileJava UP-TO-DATE
:processResources UP-TO-DATE
:classes UP-TO-DATE
:jettyRun
```

## Eclipse Debug Setting
Run > Debug Configurations > Remote Java Application
```
 Name: your-app-name
 Host: locahost // local PC or remote server host
 Port: 9999
```

## Run Debug
Run > Debug

Done :beer:
