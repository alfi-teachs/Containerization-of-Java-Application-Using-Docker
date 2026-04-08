# Step 2: Create Dockerfile
# Step 3: Build Docker image

```bash

FROM maven:3.9.6-eclipse-temurin-17

WORKDIR /app

COPY . .

RUN mvn clean package

EXPOSE 8080

CMD ["java", "-jar", "target/demo-1.0.jar"]

```

# Step 4: Run the container

```bash

docker build -t javaapp .

```


# Step 5: Output

```bash

docker run --name java-container javaapp

```

You will see:

```bash

HELLO FROM JAVA DOCKER APPLICATION

```


Since this is a simple Java program (not a web app), it will:

Run once
Print output
Exit automatically

That’s why it won’t stay in docker ps (running containers).
To see it after execution:


```bash
docker ps -a
```


# Optional: Remove container

```bash

docker rm java-container

```

