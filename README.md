# Gradle Docker Codefresh example

This is an example Java application that uses Spring Boot 2, Gradle and Docker
It is compiled using Codefresh.

If you are looking for Maven, then see this [example](https://github.com/codefresh-contrib/spring-boot-2-sample-app)

## Create a multi-stage docker image

To compile and package using Docker multi-stage builds

```bash
docker build . -t my-app
```

## Create a Docker image packaging an existing jar

```bash
./gradlew build
docker build . -t my-app -f Dockerfile.only-package
```

## To run the docker image

```bash
docker run -p 8080:8080 my-app
```

And then visit http://localhost:8080 in your browser.

## To use this project in Codefresh

There is also a [codefresh.yml](codefresh.yml) for easy usage with the [Codefresh](codefresh.io) CI/CD platform.

For the simple packaging pipeline see [codefresh-package-only.yml](codefresh-package-only.yml)

More details can be found in [Codefresh documentation](https://codefresh.io/docs/docs/learn-by-example/java/gradle/)

