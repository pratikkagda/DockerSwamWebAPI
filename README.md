# Running ASP.Net Core application inside Docker!

This is a sample To Do ASP.Net Core Web API project which we've hosted within docker.

Here are the guide though how to create docker enabled ASP.Net Core Web API solution.
  1) How to create ASP.Net Core Web API application
  2) How to create docker image
  3) How to upload docker image to docker hub
  4) How to pull docker image from docker hub
  5) How to run Web API application from docker
  
 
 # How to create ASP.Net Core Web API application:
    Please refer attached code its simply creating ASP.Net REST services project which can run on Windows as well Linux environment.
   
 # How to create docker image:
    Once you fetch application, kindly navigate though Dockerfile from solution and observer command "COPY bin/Release/PublishOutput ."
    which says that first of all we need to publish application and need to make sure that publish should be pointing to this path.
    
    After publishing code now we will generate docker image. Navigate though project directory and execute below command within 
    docker console:
    
    docker build -t pratikkagda/dockerswarmtest .
    
    Which will generate docker image file locally. Here pratikkagda is my docker username under which this image will be created.
    
#  How to upload docker image to docker hub:

    In order to publish docker image within docker hub first of all you need to have docker hub account, if you don't have one you can
    create it from: https://hub.docker.com/
    
    Now next step is to login from docker console, simply execute "docker login" command and provide your account details. Once you login
    now its time to upload image that you have created.
    
    First of all execute "docker images" command to chceck if image has successfully created or not and once you see your image name execute
    "docker push pratikkagda/dockerswarmtest" command. Which will push your image to docker hub.
    
 #  How to pull docker image from docker hub:
    
    Now image has published to docker hub, in order to pull image into any docker installed machine we need to execute this command within
    docker console:
    
    docker pull pratikkagda/dockerswarmtest
   
    You can check all available images by executing "docker images" command.
    
 # How to run Web API application from docker:
    
    Within docker image file we've mentioned port# 80 (EXPOSE 80) which means that application will be run on port# 80 after published.
    Now we've pull the images in order to run docker image execute below command within docker console:
    
    docker run --name dockerswarmdemo -d -p 8181:80 pratikkagda/dockerswarmtest
   
   Now we've mapeed port# 8181 with 80 which means that WebAPI project can be accessible through port# 8181. After executing this command
   you can browse though Web Api application by appending /api/todo.
   
 # Important Links:
    
   Simply run application within docker container: 
   
   docker run --name dockerswarmdemo -d -p 8181:80 pratikkagda/dockerswarmtest/
    
   Docker hub UR: https://hub.docker.com/r/pratikkagda/dockerswarmtest/
   
   Postman collection for all availalbe Web API operations: https://www.getpostman.com/collections/0618bf61fdb13727d4ea
 
   
   
