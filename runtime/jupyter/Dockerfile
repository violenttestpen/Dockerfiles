FROM alpine:latest AS staging

RUN apk update
RUN apk add python3 py3-pip python3-dev build-base
RUN pip3 install wheel
RUN pip3 install jupyter

FROM alpine:latest

# docker run -p8888:8888 jupyter --NotebookApp.token=''

COPY --from=staging /root/.cache /root/.cache
RUN apk add --no-cache python3 py3-pip py3-zmq bash
RUN pip3 install jupyter

RUN adduser -D jupyter -s /bin/bash

USER jupyter
#RUN jupyter notebook --generate-config \
#    && echo "c.NotebookApp.token=''" >> ~/.jupyter/jupyter_notebook_config.py

WORKDIR /home/jupyter

ENTRYPOINT ["jupyter", "notebook", "--no-browser", "--ip=0.0.0.0"]
