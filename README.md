# dockerfiles
The file contains docker files to build the images used in CI and other cases.

# How to build and push an image
```
cd <into the docker folder>
docker build .
docker image tag <IMAGE-ID> moveworkforward/atlas-run-standalone:<TAG>
docker image push -a moveworkforward/atlas-run-standalone
```

## Examples
```
docker image tag 9c54de227edc96dd3a68c41eae8b41066504ded8f58b676eea756762fd9aab23 moveworkforward/atlas-run-standalone:confluence-alpine
docker image tag a7f3975ed23a4c2a232e2b3c43bd9336c55699acada9d35eac80524b5fc47efd moveworkforward/atlas-run-standalone:bitbucket-alpine
```

# Run a container locally
```
docker run -d -p 1990:1990 moveworkforward/atlas-run-standalone:confluence-alpine
```
