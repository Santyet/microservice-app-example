# Etapa 1: Compilar el proyecto con Maven
FROM maven:3.8.5-openjdk-8 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa 2: Imagen final con el .jar
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY --from=build /app/users-api/target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
# Etapa 1: Compilar el proyecto con Maven
FROM maven:3.8.5-openjdk-8 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa 2: Imagen final con el .jar
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY --from=build /app/users-api/target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
