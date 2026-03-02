# LAB #2

## Question 1

### Steps:

- Build python flask image with the name **ITI-flask-lab2** from repo ```https://github.com/meldafrawi/basic-flask-app.git```
- The Image is preferred to be based on **alpine** or **ubuntu**

Dockerfile recipe:

```Dockerfile
FROM python:alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/meldafrawi/basic-flask-app.git
RUN pip install -r basic-flask-app/requirements.txt
ENTRYPOINT ["python", "basic-flask-app/app.py"]
```

Since the Repo ```requirment.txt``` contains old versions, I tried to install latest versions manually

The Repo shows that the App Name is ```route.py``` in WORKDIR: ```/app/basic-flask-app```

The New Dockerfile recipe:

```Dockerfile
FROM python:alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/meldafrawi/basic-flask-app.git

#Install requirment.txt latest
RUN pip install appdirs click Flask itsdangerous Jinja2 MarkupSafe packaging pyparsing six Werkzeug

#Go to App Work Directory
WORKDIR /app/basic-flask-app

CMD [ "python", "routes.py" ]
```

Build the Image:

```bash
docker build -t ITI-flask-lab2 .
```

![step 2](images/02.png)

- Run the image with memory limit 100MB
- Make sure that the image runs successfully on your machine and publish Port ```127.0.0.1:5000``` to Port ```80``` ON THE HOST

```bash
docker run -d -memory=100m -p 127.0.0.1:80:5000 ITI-flask-lab2 
```

![step 3](images/03.png)


Run ```http://127.0.0.1:80``` or write in shell:

```bash 
curl 127.0.0.1:80
```

![step 4](images/04.png)

![Final](images/01.png)

- Push the image to Docker Hub account ```fatemaahmedkhalil```

```bash
docker login
docker tag iti-flask-lab2 fatemaahmedkhalil/iti-flask-lab2:v0.1
docker push fatemaahmedkhalil/iti-flask-lab2:v0.1
```

![step 5](images/05.png)

---

## Question 2

### Steps: