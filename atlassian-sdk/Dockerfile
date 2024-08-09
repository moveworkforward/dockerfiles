FROM cimg/openjdk:17.0.11-node
LABEL maintainer=support@moveworkforward.com

ENV JDK_JAVA_OPTIONS="--add-opens=java.base/java.math=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --add-opens=java.base/java.lang.reflect=ALL-UNNAMED --add-opens=java.base/java.time=ALL-UNNAMED --add-opens=java.base/java.time.format=ALL-UNNAMED --add-opens=java.base/java.util=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED --add-opens=java.base/java.util.regex=ALL-UNNAMED --add-opens=java.base/sun.net.spi=ALL-UNNAMED --add-opens=java.base/java.io=ALL-UNNAMED"

RUN sudo apt-get update \
              &&  sudo apt-get install apt-transport-https \
              &&  wget https://marketplace.atlassian.com/download/plugins/atlassian-plugin-sdk-tgz  -O /tmp/atlassian-plugin-sdk-9.0.2.tar.gz \
              &&  ls -lart /tmp \
              &&  sudo tar -xvzf /tmp/atlassian-plugin-sdk-9.0.2.tar.gz -C /opt \
              &&  sudo mv /opt/atlassian-plugin-sdk-9.0.2 /opt/atlassian-plugin-sdk \
              &&  sudo chmod 755 /opt/atlassian-plugin-sdk/bin/* \
              &&  sudo chmod 755 /opt/atlassian-plugin-sdk/apache-maven-3.9.8/bin/* \
              &&  sudo ls -lart /opt/atlassian-plugin-sdk/apache-maven-3.9.8/bin

ENV PATH="/opt/atlassian-plugin-sdk/bin:${PATH}"

RUN git --version
RUN atlas-version
RUN node -v
RUN npm -v

# Validation
CMD ["/bin/sh" "-c" "atlas-run-standalone --product jira --http-port 2990 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]