FROM eclipse-temurin:11-jdk-alpine

# Copy local code to the container image.
WORKDIR /app
COPY mvnw .
COPY .mvn ./.mvn
COPY pom.xml .
COPY src ./src

# Build a release artifact.
RUN ./mvnw package -DskipTests

ENV PORT 8080

EXPOSE 8080

# Run the web service on container startup.
CMD ["java","-jar","/app/target/helloworld-0.0.1-SNAPSHOT-jar-with-dependencies.jar"]
