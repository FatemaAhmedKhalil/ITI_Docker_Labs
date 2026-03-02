FROM python:alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/meldafrawi/basic-flask-app.git

#Install requirment.txt latest
RUN pip install appdirs click Flask itsdangerous Jinja2 MarkupSafe packaging pyparsing six Werkzeug

# Go to App Work Directory
WORKDIR /app/basic-flask-app

CMD [ "python", "routes.py" ]