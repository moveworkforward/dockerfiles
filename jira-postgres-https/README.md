## Create SSL Certificate
```bash
keytool -genkeypair -keysize 2048 -alias tomcat -keyalg RSA -sigalg SHA256withRSA -keystore ./tomcat_store
```
Follow up all prompts and use password to `tomcat` as it is the default password for the Java keystore.
`./tomcat_store` is the keystore file that will be used in the configuration.

**Attention:** if you use another password or store location you should update the `Dockerfile `, `server.xml.j2`, `server.xml` files accordingly.



## Create Docker Image
```bash
docker build --platform linux/amd64 .
```
`--platform linux/amd64` might not work for MacOS, so you can skip it. But it's required for Linux boxes

Get the image id from the output
```bash
=> => writing image sha256:aa6458a1444a5962cf957fb37ff3424233f7c5c07f3b459e82dc1bc6c49957ba
```
`aa6458a1444a5962cf957fb37ff3424233f7c5c07f3b459e82dc1bc6c49957ba` is an image id that will be used to tag the image.

## Tag and Push Docker Image
```bash

docker image tag <IMAGE_ID> moveworkforward/jira-software-https:<TAG> //e.g. 9.2.0-jdk11
docker image push -a moveworkforward/jira-software-https
```
***Attention:*** Ensure that you have access to the `moveworkforward` repository on Docker Hub.
Also you have to change the tag in the `docker-compose.yml` file: `image: moveworkforward/jira-software-https:9.2.0-jdk11`.

## Run a Docker compose file
**Attention:**
Ensure that you have `docker-compose.yml` file, `jira_home`, `postgress` folders is in the same directory.
`jira_home`, `postgress` folders should be writable for any user.
```bash
mkdir jira_home
chmod 777 jira_home
mkdir postgress
chmod 777 postgress
```
Run the following command to start the containers
```bash
docker-compose up -d
```
It's required up to 20-30 minutes to initialize Jira Software for the first time.

## Access Jira Software
Open a browser and navigate to `https://host:8443` or `http://host:8080` to access Jira Software.