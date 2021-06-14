# Better UX for pruning images

## Listing existing images

Here I build an enhanced registry image that contains an user friendly tool
for listing all the operators.

```
[msivak@t540p opm-prune]$ podman build .
STEP 1: FROM registry-proxy.engineering.redhat.com/rh-osbs/iib-pub:v4.8
STEP 2: ADD list-packages /bin/
--> Using cache 6703243aa168da8db0de12769e63a9ecbe04b06ced0429ece30b5f0caea806e0
--> 6703243aa16
STEP 3: RUN opm registry prune -p performance-addon-operator
--> Using cache 31893c27307019dbae95ee206798be93bd2ca3da4969cd65041ab44f73e87f5d
--> 31893c27307
31893c27307019dbae95ee206798be93bd2ca3da4969cd65041ab44f73e87f5d
```

And this is the user friendly process for listing them:

```
[msivak@t540p opm-prune]$ podman run -it --entrypoint=/bin/list-packages 31893c27307
```

