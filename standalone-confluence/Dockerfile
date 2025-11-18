FROM  moveworkforward/atlassian-sdk:21-jdk-9.1.1-atlas-22-node

LABEL maintainer=support@moveworkforward.com

LABEL com.circleci.preserve-entrypoint=true


ENTRYPOINT ["/bin/sh", "-c", "atlas-run-standalone --product confluence -u 9.6.0 --version 10.1.1 --http-port 1990 --server localhost --jvmargs '-Datlassian.upm.plugin.upload.enabled=true -Datlassian.upm.signature.check.upload.disabled=true -Datlassian.upm.signature.check.enabled=fals -Datlassian.upm.signature.check.disabled=true -Xmx4096M' -Datlassian.upm.plugin.upload.enabled=true -Datlassian.upm.signature.check.upload.disabled=true -Datlassian.upm.signature.check.enabled=fals -Datlassian.upm.signature.check.disabled=true -DskipAllPrompts=true -Dmoveworkforward.dev.mode=true"]
