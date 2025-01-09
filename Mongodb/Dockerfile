#FROM        docker.io/redhat/ubi9
#COPY        mongo.repo /etc/yum.repos.d/mongo.repo
#RUN         dnf install mongodb-org -y
#RUN         sed -i -e 's/127.0.0.1/0.0.0.0/' /etc/mongod.conf
#RUN         systemctl enable mongod
#RUN        service mongod start
#ENTRYPOINT  service mongod restart && bash
#EXPOSE      27017


# Use the official MongoDB image with the latest version
FROM mongo:latest

# Expose port 27017 for MongoDB connections
EXPOSE 27017

# Create the data directory inside the container
RUN mkdir -p /data/db

# Mount the data directory to a volume to persist data
VOLUME ["/data/db"]

# Run the MongoDB server
CMD ["mongod", "--dbpath", "/data/db"]

# to build from above file
# docker build -t my-mongodb .
# MONGODB_INITDB_ROOT_USERNAME
# MONGODB_INITDB_ROOT_PASSWORD