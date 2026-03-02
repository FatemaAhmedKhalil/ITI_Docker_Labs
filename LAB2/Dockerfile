FROM python:alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/meldafrawi/basic-flask-app.git

#RUN pip install appdirs click Flask itsdangerous Jinja2 MarkupSafe packaging pyparsing six Werkzeug

# Go to App Work Directory
WORKDIR /app/basic-flask-app
#Remove the old versions from requirment,txt file
RUN sed -i 's/==.*//g' requirements.txt
#Install requirment in latest version
RUN pip install -r requirements.txt

CMD [ "python", "routes.py" ]