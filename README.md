# Multi-Stage-Docker-Builds
Docker Image Optimization of the Golang-based Calculator Application using Multi Stage Docker Builds

### Docker file without Multi-Stage :

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/08d8203e-5d35-4b30-b9a5-e7a00b8cde92)

### Building of the Docker Image without Multi-Stage :

```
docker build -t simplecalculator .
```

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/ebe1058f-888c-460b-9122-8134301815af)


### Successfull Build of Docker Image (Without MultiStage) :
![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/f4222fa6-2ee4-4049-9844-67ec10b06af3)


### Size of the Docker Image without Multi-Stage (Around 660 MB) :

```
docker images
```

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/3f937b26-177b-4bd1-841b-a2ade8de52cd)


The size of the Docker Image without Multi-Stage is much larger. 

Golang is a statically typed language. So for executing a Golang application, we do not need a Golang Runtime.

During Multi-Stage Build of Docker images, there are two stages namely :

1) Build Stage
   
2) Run Stage (Final Image)

The Final Image will have Runtime Environment, Binary (which has been built in the Build Stage) and Executable. 


To, reduce the size of the Docker Image significantly, the contents of the Build Stage should not be present in the Final Image.



So, we are using DISTROLESS IMAGES. 

### DISTROLESS IMAGES :

Very Minimalistic Image that will hardly have any packages.

The Minimalistic Image (or) Light weight Docker Image will have only the Runtime Environment.

Another important thing to be noted about Distroless Images is that they provide the HIGHEST SECURITY.


### Multi-Stage Docker File :

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/34f0138b-680a-444e-8653-e65e05914127)


### Building of the Mult-Stage Docker Image :

```
docker build -t simplecalculator-multistage .
```

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/0d66dea9-cb81-4ba2-b392-e70b31e910bf)


Size of the Docker Image built using Multi-Stage Docker Builds (Around 1.96 MB) :

```
docker images
```

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/5094d373-f5bd-42d1-8567-7fe1589cd8d1)


### Docker Image Size Comparison (Before Multi-Stage and After Multi-Stage) :

![image](https://github.com/vighas-ks-16/Multi-Stage-Docker-Builds/assets/107311113/f31ce85e-9670-4e48-bb08-735826d990e6)



During this Journey, I have used scratch - One of the official Distroless images from the Docker Hub as the base image.





