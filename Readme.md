# Dockerizing a Simple Flask Application

In this tutorial, we'll guide you through the process of Dockerizing a simple Flask application and pushing the Docker image to Docker Hub.

## Task 1: Docker, Docker Hub

- Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)
- Build the image using the Dockerfile and run the container
- Verify that the application is working as expected by accessing it in a web browser
- Push the image to a public or private repository (e.g. Docker Hub)

## Step-by-Step Guide

First, let's set up our Python environment and create a basic Flask application.

1. sudo mkdir flaskapp
2. cd flaskapp/
3. sudo apt install python3.10-venv
4. python3 -m venv task1
5. source task1/bin/activate
6. apt install python3-pip
7. pip install Flask
8. pip freeze > requirements.txt

   ![Capture](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/97d1bb04-560b-44c5-864e-d42b278e91c3)

9. apt install python3-pip
10. pip install Flask
11. pip freeze > requirements.txt
12. cd flaskapp/
13. vim app.py  (Now you have to write this code and save it)

    ![app_code](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/62e6e6db-97b0-475f-baa8-3b7221f4d312)


14. sudo vi Dockerfile ----> (Now you have to write this code and save it)

      ![Docker_code](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/d6e61dec-67fc-46cb-bc1d-7543629bb1ba)


15. cd flaskapp/

    your hierarchy should look like this

    ![hierarchy](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/55690783-fb7b-405b-9c6f-fd1c6175eda5)

16. flask run --host 0.0.0.0 --port 5000
17. Now you should have to install docker and then use this command ----> 
    docker build -t flaskapp .
18. sudo docker images
19. sudo docker push deepli123/flaskapp:latest  ---->  (here deepli123 is my docker hub profile name)

    ![dockerhub](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/aeb7ce58-1ac9-4de5-8ab9-5f719c7bb673)



