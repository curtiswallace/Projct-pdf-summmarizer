Please follow this Readme to set up and run this project. Start with the backend section, you will require the following in the set up of the backend:
An OpenAI API key, 
A JWT secret token, 
A MongoDB URI

BACKEND:

# Main.py

It serves as the entry point of the application, there are 4 endpoints in this project.
1) /login
2) /signup
3) /credits
4) /summarize

User data has been saved in Mongodb

# Login 
For login purpose

# Signup
To signup a user, on signup each user is awarded 3 credits so he is able to summarize 3 pdf documents for free

# Summarzie pdf

For pdf summarization we have used chatgpt-3.5-turbo model. It reads document thoroughly and then outputs a brief but concise summary.

For summarization user should first sign up and then login using the endpoint for login, then using the frontend user can easily summarize upto three pdf documents.

This endpoint is protected through JWT-Auth, so its only accessible to registered users


# How does credits work

This endpoint is used to fetch the remaining credits of every user. Through the jwt it identifies a user and then fetch user credits. Each user is awarded 3 credits so they are able to summarize 3 pdf documents for free


## Environment Variables

Create a .env file in the root and  follow .env.example to add all the environmental variables in it.
Use the included .env.example file and add in the variables to the placeholders, then remove the .example from the file name so it reads as ".env"
API_KEY='OPENAIKEYHERE'
secret='JWTSECRETHERE'
algorithm=HS256
URI="MONGODBURIHERE"


## Deployment
-> You should have Mongodb Server installed in the system
-> You then only need to set up the MongoDB software and copy the URI string provided into the .env file as previously specified
-> The backend will automatically create the database and the collection when you enter your first user into the application

To deploy this project run

```bash
  pip install -r requirements.txt
  uvicorn main:app --reload

```

FRONTEND:

# Description

    Simple react frontend containing login, signup and landing page, which we have used for the pdf summarization project.

## Deployment

To deploy this frontend run

```bash
  npm install
  npm start

```
