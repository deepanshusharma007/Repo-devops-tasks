Task 1: Docker, Docker Hub
• Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)
• Build the image using the Dockerfile and run the container
• Verify that the application is working as expected by accessing it in a web browser
• Push the image to a public or private repository (e.g. Docker Hub)



So, we will start with creating a python app in Ubuntu. I had taken reference from this link "https://tecadmin.net/how-to-create-and-run-a-flask-application-using-docker/#:~:text=Create%20a%20Basic%20Flask%20Application,locally%20or%20on%20a%20server.&text=Next%2C%20create%20the%20Python%20virtual%20environment%20and%20then%20activate%20the%20environment.&text=Now%20install%20the%20Flask%20python%20module%20under%20the%20virtual%20environment"

1. sudo mkdir flaskapp
2. cd flaskapp/
3. sudo apt install python3.10-venv
4. python3 -m venv task1
5. sudo python3 -m venv task1
6. source task1/bin/activate
   ![Capture](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/97d1bb04-560b-44c5-864e-d42b278e91c3)

7. apt install python3-pip
8. pip install Flask
9. pip freeze > requirements.txt
10. cd flaskapp/
11. vim app.py
 
