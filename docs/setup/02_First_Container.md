# 02_First_Container.md

## Objective
Create and run the first Dockerized web app using Flask to understand the basics of containerization.

## Steps
1. Created `app.py` (simple Flask app).
2. Wrote `Dockerfile` to build a Python container image.
3. Built and ran the container.
4. Exposed port 5000 and tested via `curl` and browser.



## app.py

from flask import Flask
app = Flash(__name__)
@app.route('/')
def home():
    return "welcome to tron"

if __name__=='__main__':
    app.run(host='0.0.0.0' , port=5000)

## Commands
```bash
docker build -t mini-netflix-app .
docker run -d -p 5000:5000 mini-netflix-app
docker ps
docker logs mini-netflix
docker stop mini-netflix
docker rm mini-netflix
