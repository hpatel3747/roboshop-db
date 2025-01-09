FROM        docker.io/redhat/ubi9
COPY        mongo.repo /etc/yum.repos.d/mongo.repo
RUN         dnf install mongodb-org -y
RUN         sed -i -e 's/127.0.0.1/0.0.0.0/' /etc/mongod.conf
RUN         systemctl enable mongod
RUN         systemctl start mongod
ENTRYPOINT  ["systemctl", "start", "mongod;"]
EXPOSE      27017