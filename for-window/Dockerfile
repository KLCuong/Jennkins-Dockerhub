# Use a Maven image as the base image
FROM maven:3.9.6-eclipse-temurin-17-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the pom.xml file to the container
COPY pom.xml .

# Download the project dependencies specified in the pom.xml
RUN mvn dependency:go-offline -B

# Copy the rest of the application code to the container
COPY src ./src

# Build the application
RUN mvn package

# Define the command to run the application
CMD ["java", "-jar", "target/your-application.jar"]
