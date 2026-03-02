FROM python:alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/meldafrawi/basic-flask-app.git
RUN pip install appdirs click Flask itsdangerous Jinja2 MarkupSafe packaging pyparsing six Werkzeug
WORKDIR /app/basic-flask-app
CMD [ "python", "routes.py" ]