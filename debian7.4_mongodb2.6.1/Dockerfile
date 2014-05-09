FROM        debian:7.4
RUN         apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
RUN         echo 'deb http://downloads-distro.mongodb.org/repo/debian-sysvinit dist 10gen' | tee /etc/apt/sources.list.d/mongodb.list
RUN         apt-get update
RUN         apt-get -y install wget tar mongodb-org=2.6.1 mongodb-org-server=2.6.1 mongodb-org-shell=2.6.1 mongodb-org-tools=2.6.1
RUN         echo "mongodb-org hold" | sudo dpkg --set-selections
RUN         echo "mongodb-org-server hold" | sudo dpkg --set-selections
RUN         echo "mongodb-org-shell hold" | sudo dpkg --set-selections
RUN         echo "mongodb-org-tools hold" | sudo dpkg --set-selections
RUN         mkdir -p /data/db
EXPOSE 27017
ENTRYPOINT ["usr/bin/mongod"]
