# Step 1: Create Project Structure

```bash
java-docker-app/
 ├── Dockerfile
 ├── pom.xml
 └── src/
     └── main/
         └── java/
             └── com/example/demo/
                 └── DemoApplication.java


```

# Step 2: Build Docker image

```bash

FROM maven:3.9.6-eclipse-temurin-17

WORKDIR /app

COPY . .

RUN mvn clean package

EXPOSE 8080

CMD ["java", "-jar", "target/demo-1.0.jar"]

```

# Step 3: Build Image

```bash

docker build -t java-web-app:v1 .
```
# Step 4: Run Container

```bash
docker run -d -p 8080:8080 --name java-web-container java-web-app:v1


```
# Step 5: Open in Browser
```bash

http://localhost:8080
```
# You’ll see:
Hello Alfia! Your Java Docker App is running 🚀

.
To see container after execution:

```bash
docker ps -a
```

# Optional: Remove container

```bash

docker rm java-container

```

