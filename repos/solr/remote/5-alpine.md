## `solr:5-alpine`

```console
$ docker pull solr@sha256:42d357f848f3a4649ccf104181a520e1fb2b64cb4130054a10eba1cc9bf45cc5
```

-	Platforms:
	-	linux; amd64

### `solr:5-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **193.4 MB (193358987 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6e8c572d3282f9cd5ce4d08bd2c918715de89c38e9f87ddf734992ba8edf0657`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Tue, 07 Mar 2017 01:03:58 GMT
ENV LANG=C.UTF-8
# Tue, 07 Mar 2017 01:03:59 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 07 Mar 2017 01:04:09 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk/jre
# Tue, 07 Mar 2017 01:04:09 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 07 Mar 2017 01:04:10 GMT
ENV JAVA_VERSION=8u121
# Tue, 07 Mar 2017 01:04:10 GMT
ENV JAVA_ALPINE_VERSION=8.121.13-r0
# Tue, 07 Mar 2017 01:04:15 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 07 Mar 2017 20:02:13 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Tue, 07 Mar 2017 20:02:13 GMT
ARG SOLR_DOWNLOAD_SERVER
# Tue, 14 Mar 2017 20:27:30 GMT
RUN apk add --no-cache         lsof         gnupg         procps         tar         bash
# Tue, 14 Mar 2017 20:27:32 GMT
RUN apk add --no-cache ca-certificates wget &&         update-ca-certificates
# Tue, 14 Mar 2017 20:27:32 GMT
ENV SOLR_USER=solr
# Tue, 14 Mar 2017 20:27:32 GMT
ENV SOLR_UID=8983
# Tue, 14 Mar 2017 20:27:33 GMT
RUN addgroup -S -g $SOLR_UID $SOLR_USER &&   adduser -S -u $SOLR_UID -g $SOLR_USER $SOLR_USER
# Tue, 14 Mar 2017 20:27:34 GMT
ENV SOLR_VERSION=5.5.4
# Tue, 14 Mar 2017 20:27:34 GMT
ENV SOLR_URL=https://archive.apache.org/dist/lucene/solr/5.5.4/solr-5.5.4.tgz
# Tue, 14 Mar 2017 20:27:34 GMT
ENV SOLR_SHA256=c1528e4afc9a0b8e7e5be0a16f40bb4080f410d502cd63b4447d448c49e9f500
# Tue, 14 Mar 2017 20:27:35 GMT
ENV SOLR_KEYS=E6E21FFCDCEA14C95910EA65051A0FAF76BC6507
# Tue, 14 Mar 2017 20:27:38 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Tue, 14 Mar 2017 20:27:54 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -q $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -q $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores &&   sed -i -e 's/#SOLR_PORT=8983/SOLR_PORT=8983/' /opt/solr/bin/solr.in.sh &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_USER /opt/solr &&   mkdir /docker-entrypoint-initdb.d /opt/docker-solr/
# Tue, 14 Mar 2017 20:27:55 GMT
COPY dir:37fe27423809e9a020959b49d869a79285ab853758a6a8a6bfe8564dcdf7ff56 in /opt/docker-solr/scripts 
# Tue, 14 Mar 2017 20:27:56 GMT
RUN chown -R $SOLR_USER:$SOLR_USER /opt/docker-solr
# Tue, 14 Mar 2017 20:27:56 GMT
ENV PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Tue, 14 Mar 2017 20:27:57 GMT
EXPOSE 8983/tcp
# Tue, 14 Mar 2017 20:27:57 GMT
WORKDIR /opt/solr
# Tue, 14 Mar 2017 20:27:57 GMT
USER [solr]
# Tue, 14 Mar 2017 20:27:58 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 14 Mar 2017 20:27:58 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:627beaf3eaaff1c0bc3311d60fb933c17ad04fe377e1043d9593646d8ae3bfe1`  
		Last Modified: Fri, 03 Mar 2017 20:34:41 GMT  
		Size: 1.9 MB (1905270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1de20f2d8b839756d5fc0ae6871096666a822b6b4205e11e9cf438a2263f3281`  
		Last Modified: Tue, 07 Mar 2017 01:12:49 GMT  
		Size: 232.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74e619d348278f1e8660192734bff496a6c3e05aab6bef025e843e7413a7c9e3`  
		Last Modified: Tue, 07 Mar 2017 01:15:49 GMT  
		Size: 53.8 MB (53811092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5612c7935782ea8818c6c0dc995398897504dc2839b2ffcd8adcaee1e7d97e1`  
		Last Modified: Tue, 14 Mar 2017 20:31:21 GMT  
		Size: 5.2 MB (5165760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79fe63d33c3b93c222319fc62b484f3c1a351afc40549dd51e04ebbad036525e`  
		Last Modified: Tue, 14 Mar 2017 20:31:19 GMT  
		Size: 612.2 KB (612170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c57f9cdaa147f9ea11fb92f86c81fed2d94e1f87222fd26b8a784b40c91398fd`  
		Last Modified: Tue, 14 Mar 2017 20:31:16 GMT  
		Size: 1.2 KB (1236 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b768f07ee275a9aecd14dd06f5db765d2452f21ada3dcb8763520bd73a8734a`  
		Last Modified: Tue, 14 Mar 2017 20:31:16 GMT  
		Size: 7.1 KB (7087 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b9bcbb6753e77edb39e3abb452e886c2aa8e5ffdac1659d2700ffba4ce3d2b9`  
		Last Modified: Tue, 14 Mar 2017 20:31:30 GMT  
		Size: 131.9 MB (131850074 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:769aea95ae2762b693c75218d7c8547300297744399fcb8b9fc2e48c03dd1abe`  
		Last Modified: Tue, 14 Mar 2017 20:31:16 GMT  
		Size: 3.0 KB (3031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae794e18877774dc8cbe02b1ad86e37342dcc864164bca13917e1f3d47eeaa72`  
		Last Modified: Tue, 14 Mar 2017 20:31:16 GMT  
		Size: 3.0 KB (3035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
