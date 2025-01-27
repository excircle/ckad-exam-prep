# Define, Build, and Modify Containers

### **1.) Define, Build, and Modify Container Images**

Create a sample application file (e.g., app.py for Python):

```bash
echo 'print("Hello, CKAD Takers!")' > app.py
```

### **2.) Define, Build, and Modify Container Images**

Create a `requirements.txt` file for dependencies (Python example):

```bash
echo 'flask' > requirements.txt
```

### **3.) Create Dockerfile for the App**

Create the Docker for the for the image build

```bash
cat << EOF > Dockerfile
# Use a base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy application files
COPY . .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Define the command to run the application
CMD ["python", "app.py"]
EOF
```

### **4.) Build Docker image**

Use `docker build` to create the Docker image

```bash
docker build -t my-ckad-app:latest .
```

### **5.) Run Docker Images**

Run our image. You should see `Hello, CKAD Takers!` printed in the terminal.

```bash
> docker run --rm my-ckad-app:latest
Hello, CKAD Takers!
```
