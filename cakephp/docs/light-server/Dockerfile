FROM cakephpfr/docs:light

ENV DEBIAN_FRONTEND noninteractive

LABEL Description="This image is used to create an environment to contribute to the cakephp/docs (light-server version without latex)"

COPY requirements.txt /tmp/
RUN pip install -r /tmp/requirements.txt

WORKDIR /data

CMD sphinx-serve --build build
