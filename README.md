# **Docker Basics: Running a Simple Python App**  

This project introduces the basics of Docker by running a simple Python script inside a container. We will start by printing "Hello, World!" using Docker.  

## **Prerequisites**  

Before starting, ensure you have the following installed on your system:  

- **Docker Desktop** ([Download Here](https://www.docker.com/products/docker-desktop))  
- **Python** ([Download Here](https://www.python.org/downloads/))  

## **Step 1: Setting Up the Project**  

Create a new project directory and navigate into it:  
```sh
mkdir docker-hello-world  
cd docker-hello-world  
```

Create a Python script named `app.py`:  

```python
# app.py
print("Hello, World!")
```

## **Step 2: Verify Docker and Python Installation**  

To check if Docker and Python are installed, run the following commands:  

### **Check Docker Version:**  
```sh
docker --version
```  
### **Check Python Version:**  
```sh
python --version
```

If both commands return their respective versions, you are ready to proceed.  

## **Step 3: Creating a Dockerfile**  

Inside the project directory, create a file named `Dockerfile` (without any extension) and add the following content:  

```dockerfile
# Use the official Python image
FROM python:3.9  

# Set the working directory inside the container
WORKDIR /app  

# Copy the Python script to the container
COPY app.py .  

# Command to run the script
CMD ["python", "app.py"]
```

## **Step 4: Building the Docker Image**  

Run the following command to build the Docker image:  
```sh
docker build -t hello-world-app .
```

After the build is complete, you can verify the created image by running:  

```sh
docker images
```

## **Step 5: Running the Docker Container**  

Now, run the Docker container using the following command:  

```sh
docker run hello-world-app
```

If everything is set up correctly, the output should be:  
```
Hello, World!
```

## **Conclusion**  

Congratulations! 🎉 You have successfully created a basic Docker container running a Python script. This is your first step into containerization! 🚀  

For further learning, you can:  
- Modify `app.py` to take user input.  
- Explore multi-stage builds for optimized Docker images.  
- Integrate Docker Compose for managing multiple containers.  

Happy coding! 🚀

