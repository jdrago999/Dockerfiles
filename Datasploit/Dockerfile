FROM debian:stretch-slim
LABEL MAINTAINER "Chandrapal <bnchandrapal@protonmail.com>"

RUN cd /home \
    && apt-get update \
    && apt-get install -y git python python-pip libxml2-dev libxslt-dev lib32z1-dev \
    && git clone https://github.com/DataSploit/datasploit.git \
    && cd datasploit \
    && git checkout cac54135 \
    && pip install -r requirements.txt

COPY config.py /home/datasploit/config.py

WORKDIR /home/datasploit

ENTRYPOINT ["python", "datasploit.py"]
