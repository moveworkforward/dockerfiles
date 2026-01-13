FROM atlassian/jira-software:10.3.8-jdk17

COPY ./server.xml /opt/atlassian/jira/conf
COPY ./server.xml.j2 /opt/atlassian/etc
COPY ./tomcat_store /var/atlassian/