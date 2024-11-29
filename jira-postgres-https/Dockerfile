FROM atlassian/jira-software:9.2.0-jdk11

COPY ./server.xml /opt/atlassian/jira/conf
COPY ./server.xml.j2 /opt/atlassian/etc
COPY ./tomcat_store /var/atlassian/