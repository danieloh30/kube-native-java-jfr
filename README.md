# kube-native-java to monitor native excutables using JFR (Java Flight Recorder)

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Creating a native executable

You can create a native executable using: 
```shell script
quarkus build --native
```

## Run PostgreSQL locally

```shell script
docker run --rm=true --name person -e POSTGRES_USER=user -e POSTGRES_PASSWORD=superSecret -e POSTGRES_DB=person -p 5432:5432 postgres:14
```

## Execute your native executable with: 

```
target/kube-native-java-1.0.0-SNAPSHOT-runner -XX:+FlightRecorder -XX:StartFlightRecording=settings=profile.jfc,filename=recording.jfr
```