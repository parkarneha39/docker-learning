#Base OS
FROM ubuntu                                                                         

#Creating a base folder where your code will be stored
WORKDIR /app

#this is base file for application so copying it
COPY requirements.txt /app/

#Copying the actual code folder
COPY devops /app/

#this app needs Python, so installing it
RUN apt-get update && apt-get install -y python3 python3-pip && pip install -r requirements.txt && cd devops

#Entrypoint is not changebale
ENTRYPOINT ["python3"]

#CMD section is changeable
CMD ["manage.py", "runserver", "0.0.0.0:8000"]


#The main code file is here: https://github.com/iam-veeramalla/Docker-Zero-to-Hero/tree/main/examples/python-web-app. Clone this repo.