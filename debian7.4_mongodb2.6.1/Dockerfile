FROM        debian:7.4
RUN         apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
RUN         echo 'deb http://downloads-distro.mongodb.org/repo/debian-sysvinit dist 10gen' | tee /etc/apt/sources.list.d/mongodb.list
RUN         apt-get update
RUN         apt-get -y install adduser mongodb-org=2.6.1
RUN         echo "mongodb-org hold" | dpkg --set-selections
RUN         echo "mongodb-org-server hold" | dpkg --set-selections
RUN         echo "mongodb-org-shell hold" | dpkg --set-selections
RUN         echo "mongodb-org-tools hold" | dpkg --set-selections
RUN         mkdir -p /data/db
EXPOSE 27017
ENTRYPOINT ["usr/bin/mongod"]
