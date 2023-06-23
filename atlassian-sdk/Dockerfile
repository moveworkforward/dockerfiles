FROM cimg/openjdk:8.0.362-node
LABEL maintainer=support@moveworkforward.com

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