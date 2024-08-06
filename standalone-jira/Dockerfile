FROM moveworkforward/atlassian-sdk:17-jdk-8.2.28-atlas-20-node

LABEL maintainer=support@moveworkforward.com

LABEL com.circleci.preserve-entrypoint=true

ENTRYPOINT ["/bin/sh", "-c", "atlas-run-standalone --product jira --http-port 2990 --version 10.0.0-m0008 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]
