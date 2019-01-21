FROM 8-jre-alpine3.8

ADD user-0.0.1-SNAPSHOT.jar /app/application.jar

CMD ["java", "-jar", "-Ddetail.hostname=localhost", "/app/application.jar"]
