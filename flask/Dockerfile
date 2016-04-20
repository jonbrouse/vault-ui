FROM python:alpine

ADD assets/sample_app /opt/sample_app

WORKDIR /opt

#RUN pip install flask-bootstrap
RUN pip install --no-cache-dir -r sample_app/requirements.txt

ENTRYPOINT ["flask"]
