# dockerfiles
The file contains docker files to build the images used in CI and other cases.

# How to build and push an image
```
cd <into the docker folder>
docker build --platform linux/amd64 .  // for amd64
docker image tag <IMAGE-ID> moveworkforward/atlas-run-standalone:<TAG>
docker image push -a moveworkforward/atlas-run-standalone
```

## Examples
```
docker image tag 9c54de227edc96dd3a68c41eae8b41066504ded8f58b676eea756762fd9aab23 moveworkforward/atlas-run-standalone:confluence-alpine
docker image tag a7f3975ed23a4c2a232e2b3c43bd9336c55699acada9d35eac80524b5fc47efd moveworkforward/atlas-run-standalone:bitbucket-alpine
docker image tag b1155466b6d9564587388c8d6e6703341915d04cf95b8ec20649bc83294306e7 moveworkforward/atlas-run-standalone:jira-alpine
```

# Run a container locally
```
docker run -d -p 1990:1990 moveworkforward/atlas-run-standalone:confluence-alpine
```

Platform 7 images:
```
moveworkforward/atlassian-sdk:17-jdk-8.2.28-atlas-20-node
moveworkforward/atlas-run-standalone:bitbucket-9
moveworkforward/atlas-run-standalone:jira-10
moveworkforward/atlas-run-standalone:confluence-9
```