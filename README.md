# dockerfiles
The file contains docker files to build the images used in CI and other cases.

# How to build and push an image
```
cd <into the docker folder>
docker build .
docker image tag <IMAGE-ID> moveworkforward/atlas-run-standalone:<TAG>
docker image push -a moveworkforward/atlas-run-standalone
```
