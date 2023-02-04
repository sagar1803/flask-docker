FROM ubuntu:22.04

RUN apt-get update -y
RUN apt-get install python3-pip -y
RUN apt-get install gunicorn3 -y

WORKDIR /opt/

COPY requirements.txt /opt/requirements.txt
COPY flaskapp /opt/

RUN pip3 install -r requirements.txt

CMD ["gunicorn3", "-b", "0.0.0.0:8000", "app:app", "--workers=5"]