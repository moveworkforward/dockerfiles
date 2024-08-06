FROM cimg/openjdk:17.0.11-node
LABEL maintainer=support@moveworkforward.com

ENV JDK_JAVA_OPTIONS="--add-opens=java.base/java.math=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --add-opens=java.base/java.lang.reflect=ALL-UNNAMED --add-opens=java.base/java.time=ALL-UNNAMED --add-opens=java.base/java.time.format=ALL-UNNAMED --add-opens=java.base/java.util=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED --add-opens=java.base/java.util.regex=ALL-UNNAMED --add-opens=java.base/sun.net.spi=ALL-UNNAMED --add-opens=java.base/java.io=ALL-UNNAMED"

RUN sudo apt-get update \
              &&  sudo apt-get install apt-transport-https \
              &&  sudo sh -c 'echo "deb https://packages.atlassian.com/debian/atlassian-sdk-deb/ stable contrib" >>/etc/apt/sources.list' \
              &&  wget https://packages.atlassian.com/api/gpg/key/public \
              &&  sudo apt-key add public \
              &&  sudo apt-get update \
              &&  sudo apt-get install atlassian-plugin-sdk \
              &&  atlas-version \
              &&  git --version

RUN git --version
RUN atlas-version
RUN node -v
RUN npm -v

# Validation
CMD ["/bin/sh" "-c" "atlas-run-standalone --product jira --http-port 2990 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]