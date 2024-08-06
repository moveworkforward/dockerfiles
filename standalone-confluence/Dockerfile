FROM cimg/openjdk:17.0.11-node

LABEL maintainer=support@moveworkforward.com

LABEL com.circleci.preserve-entrypoint=true

ENTRYPOINT ["/bin/sh", "-c", "atlas-run-standalone --product confluence --version 9.0.1 --http-port 1990 --server 0.0.0.0 --jvmargs -Xmx4096M -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]
