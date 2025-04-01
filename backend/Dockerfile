FROM gradle:8.5.0-jdk21 AS build
WORKDIR /Java-app/
COPY Java-app .
RUN gradle -p /Java-app/back-end bootJar


FROM openjdk:21-jdk
COPY --from=build /Java-app/back-end/build/libs/ci-back-end-0.0.1-SNAPSHOT.jar .
EXPOSE 8081
CMD ["java","-jar","ci-back-end-0.0.1-SNAPSHOT.jar"]
