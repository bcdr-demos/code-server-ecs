# start with code-server's Debian image
FROM codercom/code-server:latest

# add requirements for python project (inspired by https://docs.docker.com/compose/gettingstarted)
RUN sudo apt-get update && sudo apt-get install -y python3.7 python3-pip

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
COPY app.py /home/coder/project/app.py

# give the coder user permission to edit
RUN sudo chown -R coder /home/coder/project