# Step 2: Create Dockerfile
# Step 3: Build Docker image

```bash

FROM eclipse-temurin:17-jdk-jammy

WORKDIR /app

COPY App.java .

RUN javac App.java

CMD ["java", "App"]

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

