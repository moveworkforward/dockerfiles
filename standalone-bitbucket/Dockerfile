FROM moveworkforward/atlassian-sdk:17-jdk-8.2.28-atlas-20-node

LABEL maintainer=support@moveworkforward.com

LABEL com.circleci.preserve-entrypoint=true

ENTRYPOINT ["/bin/sh", "-c", "atlas-run-standalone --product bitbucket --http-port 7990 --version 9.0.0 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]