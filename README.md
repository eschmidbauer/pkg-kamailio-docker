# Description

Docker Debian based Images with dependencies installed ready to be used
to build Kamailio from sources

# Upgrade

You need the kamailio sources at _src_ so get them:

```
git clone https://github.com/kamailio/kamailio.git src
```

or refresh them:

```
make pull
```

and just
```
make
```

# build locally the image
for instance:
```
export DIST=bullseye VERSION=master
```
```
cd ${DIST}; docker build --tag=pkg-kamailio-docker:${VERSION}-${DIST} .
```

or pull the image from docker hub

```
docker pull kamailio/pkg-kamailio-docker:${VERSION}-${DIST}
```
# run container
```
docker run -i -t --rm -v `pwd`/src:/code:rw kamailio/pkg-kamailio-docker:${VERSION}-${DIST} /bin/bash
```
