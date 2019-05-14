# Gradle Docker Codefresh example

This is an example Java application that uses Spring Boot 2, Gradle and Docker
It is compiled using Codefresh

## Create a multi-stage docker image

To compile and package using Docker multi-stage builds

```
docker build . -t my-app
```

## Create a Docker image packaging an existing jar

```
./gradlew build
docker build . -t my-app -f Dockerfile.only-package
```

## To run the docker image

```
docker run -p 8080:8080 my-app
```

And then visit http://localhost:8080 in your project

The Dockerfile also has a healthcheck

## To use this project in Codefresh 

There is also a [codefresh.yml](codefresh.yml) for easy usage with the [Codefresh](codefresh.io) CI/CD platform.

For the simple packaging pipeline see [codefresh-package-only.yml](codefresh-package-only.yml)

More details can be found in [Codefresh documentation](https://codefresh.io/docs/docs/learn-by-example/java/gradle/)

