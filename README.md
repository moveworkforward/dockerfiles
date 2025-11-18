# dockerfiles
The file contains docker files to build the images used in CI and other cases.

# How to build and push an image
```
cd <into the docker folder>
docker build --platform linux/amd64 .  // for amd64 - required for CircleCI, for Apple use: --platform linux/arm64
docker image tag <IMAGE-ID> moveworkforward/atlas-run-standalone:<TAG>
docker image push moveworkforward/atlas-run-standalone:<TAG>
```
`IMAGE-ID` can be found by running `docker images` after the build command.
For instance `IMAGE-ID=9c3104152ae500b1089fe29f43fb88b367dd62e9041aff1014bc161278885362` for output:
```
 => => exporting layers                                                                                                                                                                                             15.9s
 => => exporting manifest sha256:58dc4192c67ede53ea143ee8c430ea9781a3216d34c61371ad9b69da0a98a0e8                                                                                                                    0.0s
 => => exporting config sha256:2080bcf70acb45d9a80baaef03d1cb982fde81b03682271840482ac64fcc54a2                                                                                                                      0.0s 
 => => exporting attestation manifest sha256:db7bdb95ec6e91eb05df0dd119e99c9feb3d7ee9bca8826e087c45ef1539797b                                                                                                        0.0s 
 => => exporting manifest list sha256:9c3104152ae500b1089fe29f43fb88b367dd62e9041aff1014bc161278885362                                                                                                               0.0s 
 => => naming to moby-dangling@sha256:9c3104152ae500b1089fe29f43fb88b367dd62e9041aff1014bc161278885362 
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
moveworkforward/atlassian-sdk:17-jdk-9.0.4-atlas-20-node
moveworkforward/atlas-run-standalone:bitbucket-9
moveworkforward/atlas-run-standalone:jira-10
moveworkforward/atlas-run-standalone:confluence-9
```