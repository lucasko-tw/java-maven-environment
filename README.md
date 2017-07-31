JAVA Maven Environment
=========================

### Maintain Dependencies 
```sh
mvn dependency:get -DgroupId=org.springframework -DartifactId=spring-core -Dversion=4.3.8.RELEASE
```


### Create Volume for Maven Repository
```
docker volume create --name maven-repo
```

### Build Docker Image
```
docker build -t java-maven .

```

### Run for pre-installing Dependencies
```
 docker run  -v maven-repo:/root/.m2 -v $PWD/maven.sh:/tmp/maven.sh -it java-maven bash /tmp/maven.sh
```



