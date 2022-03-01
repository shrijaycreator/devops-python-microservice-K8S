# devops-python-microservice-K8S
Python microservice deployment using Docker and kubernetes
# Prerequistes and Assumptions
Assuming all tasks are done using an linux based operating system.

1.a Python development environment.

2.a Docker environment running.

3.a Kubernetes cluster running.

4.Have the kubectl command line (kubectl CLI) installed.

# Instructions to Build the application using Dockerfile
Dockerfile file is created according to the python microservice application source code,

To run the dockerfile
cd to the directory containing the Dockerfile
    
    $ docker build -t [Dockerhubname]/job1 .
    
    $ docker build -t [Dockerhubname]/job2 .
    
    $ docker build -t [Dockerhubname]/api-route .
    
    $ docker images

  you will see the images built
  
To run the image

    $docker run -p  job1
    $docker run -p  job2
    $docker run -p  api-route

# Deploying using Kubernetes
Assuming that the kubernetes cluster is running, The docker Images is pushed to Dockerhub.
deployment.yaml and service.yaml is created

To apply the deployment. (cd to the directory containing the files)
Run the following from the directory where the deploymeny file is located.


    $kubectl apply -f deployment.yaml
    $kubectl describe deployment 
    $kubectl get pods

#Loadbalancer service
port 8081 , pointing to port 8080
targetPort

To run the Service

    $kubectl apply -f service.yaml
    $kubectl get service

#To run Job1 and Job2 as Cronjob

    $kubectl apply -f cronjob1.yaml
    
    $kubectl apply -f cronjob2.yaml

To check scheduled cronjobs

    $ kubectl get cronjob.
