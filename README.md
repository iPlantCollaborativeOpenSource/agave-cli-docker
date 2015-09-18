# Agave CLI for iPlant

This repository holds a custom Dockerfile for extending the agaveapi/agave-cli image with:

* [jq](https://stedolan.github.io/jq/)
* wget
* which
* a custom login prompt

Usage:

```bash
docker run -it --rm=true -v $HOME/.agave:/root/.agave -v `pwd`:/home iplantc/agave-cli bash
```

