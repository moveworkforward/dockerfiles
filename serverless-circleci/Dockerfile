FROM cimg/node:20.3.0

USER root

RUN apt-get update && \
    apt-get install -y python3-pip python3-dev && \
    pip3 install --upgrade awscli

RUN npm i npm@latest -g

RUN node -v
RUN npm -v
RUN python3 --version
RUN aws --version

USER circleci