FROM debian:jessie

ENV DEBIAN_FRONTEND noninteractive

LABEL Description="This image is used to create an environment to contribute to the cakephp/docs (light version without latex)"

RUN apt-get update && apt-get install -y \
  python-pip

ADD ./requirements.txt /tmp/requirements.txt
RUN pip install -qr /tmp/requirements.txt

WORKDIR /data

CMD ["/bin/bash"]
