											QUANTIFIED SELF V2



This is a manual for the users on how to use the QuantifiedSelf V2 application.
QuantifiedSelf aims to track your progression via numbers or explicitly by the data that the user provides concurrently.

Instructions on how to run the code:

1) This project requires node_modules of version 14.00.00+ to be installed, in the frontend directory. These can be obtained from the NodeJS website and installer
2) Setup a redis-server on your linux environment and turn the server on using the command 
   "redis-server" on the terminal.
3) Navigate to the project directory and open three more terminals.
4) In one of the terminals, use the command cd frontend/ to go to the frontend folder and use the command "npm run serve" to start the vue application.
5) The vue app cannot function without the flask API. 
6) Hence, go to the other two terminals and enter the command cd backend/ to go to the backend directory.
7) On the backend directory, enter the command "source flask/bin/activate" to activate the virtual environment.
8) In one of the two terminals, enter the command "python application.py" to start the flask API server
9) In the other terminal, enter the command "celery -A application.celery worker --loglevel info" to start the celery application for the asynchronous tasks to run.
10) After this, the app is ready for testing



