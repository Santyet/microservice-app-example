# Usamos una imagen base liviana con JDK 8
FROM openjdk:8-jdk-alpine

# Directorio de trabajo dentro del contenedor
WORKDIR /app

# Copiamos el JAR compilado al contenedor y lo renombramos como app.jar
COPY target/users-api-0.0.1-SNAPSHOT.jar app.jar

# Variables de entorno con valores por defecto (pueden ser sobreescritas al correr el contenedor)
ENV JWT_SECRET=defaultsecret
ENV SERVER_PORT=8080

# Expone el puerto (opcional, útil para documentación)
EXPOSE ${SERVER_PORT}

# Comando de entrada que ejecuta la app
ENTRYPOINT ["sh", "-c", "java -Dserver.port=$SERVER_PORT -DJWT_SECRET=$JWT_SECRET -jar app.jar"]
