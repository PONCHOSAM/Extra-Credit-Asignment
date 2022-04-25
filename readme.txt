//==================================================<This is a project By Samuel Hennon to create a kubernettis cluster of 3 and then deploy a pyton web app on it
* First I started by creating my cluster from the google cloud platform console
* From there I set up a basic cluster with the settings given during lecture
* From that point I opened the terminal to setup my python flask 
* I used the Following Code
//=========================<Requirements.txt
Flask==2.0.2
//=========================<app.py
from flask import Flask
app = Flask(__name__)
@app.route('/')
def index():
 return "Hello World!\n"
if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
//=========================<Dockerfile
) In web directory, create a Dockerfile file
FROM python:3.7-slim
ENV APP_HOME /app
WORKDIR $APP_HOME
COPY . ./
RUN pip install -r requirements.txt
ENTRYPOINT ["python"]
CMD ["app.py"]
//=========================
* After creating my docker image and running it I deployed my cluster with this yaml file it had generated
* This Yaml File is included in the files 
* This completes the assignmnet
