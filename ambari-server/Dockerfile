FROM hortonworks/ambari-base:2.7.3
RUN yum install -y httpd php
#RUN wget http://public-repo-1.hortonworks.com/ambari/centos7/2.x/updates/2.7.3.0/ambari-2.7.3.0-centos7.tar.gz
#RUN wget http://public-repo-1.hortonworks.com/HDP-UTILS-1.1.0.22/repos/centos7/HDP-UTILS-1.1.0.22-centos7.tar.gz
#RUN wget http://public-repo-1.hortonworks.com/HDP-GPL/centos7/3.x/updates/3.1.0.0/HDP-GPL-3.1.0.0-centos7-gpl.tar.gz
#RUN tar zxvf ambari-2.7.3.0-centos7.tar.gz -C /var/www/html/
##RUN wget -nv http://public-repo-1.hortonworks.com/ambari/centos7/2.x/updates/2.7.3.0/ambari.repo -O 		/etc/yum.repos.d/ambari.repo

RUN yum install -y ambari-server
#RUN wget http://public-repo-1.hortonworks.com/HDP/centos7/3.x/updates/3.1.0.0/HDP-3.1.0.0-centos7-rpm.tar.gz
#RUN tar xvzf HDP-UTILS-1.1.0.22-centos7.tar.gz -C /var/www/html/
#RUN tar xvzf HDP-UTILS-1.1.0.22-centos7.tar.gz -C /var/www/html/
#RUN tar xvzf HDP-GPL-3.1.0.0-centos7-gpl.tar.gz -C /var/www/html/
#RUN tar xvzf HDP-3.1.0.0-centos7-rpm.tar.gz -C /var/www/html/


# add mysql and psql connectors to ambari-server so it can be downloaded by services (e.g.: Ranger)
ADD https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.49.tar.gz /var/lib/ambari-server/resources/mysql-jdbc-driver.jar
ADD https://jdbc.postgresql.org/download/postgresql-42.2.14.jar /var/lib/ambari-server/resources/postgres-jdbc-driver.jar
RUN yum install -y mysql-connector-java
RUN cp /usr/share/java/mysql-connector-java.jar /var/lib/ambari-server/resources/mysql-connector-java.jar
ADD start-server.sh /root/start-server.sh
RUN yum install -y sshpass

