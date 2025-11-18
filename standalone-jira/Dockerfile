FROM  moveworkforward/atlassian-sdk:21-jdk-9.1.1-atlas-22-node

LABEL maintainer=support@moveworkforward.com

LABEL com.circleci.preserve-entrypoint=true

ENTRYPOINT ["/bin/sh", "-c", "atlas-run-standalone -u 9.6.0 --product jira --http-port 2990 --version 11.0.1 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]
