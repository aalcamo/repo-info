## `openjdk:6b38-jdk`

```console
$ docker pull openjdk@sha256:79582f6106c6f2aa33968065af8b5ac934a9e8307cad4462facdfafc232976d7
```

-	Platforms:
	-	linux; amd64

### `openjdk:6b38-jdk` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **189.5 MB (189541332 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:75512cd15ab91d3851823ef1c1cf0c624f136760ef5adf2d9ba2622751deba28`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 24 Apr 2017 19:30:04 GMT
ADD file:cda477892272e4acea1f147bb76a3de26ec0d0abfd0c8c4171bfb10053c98985 in / 
# Mon, 24 Apr 2017 19:30:04 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:59:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 20:00:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 23:38:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 23:38:24 GMT
ENV LANG=C.UTF-8
# Mon, 24 Apr 2017 23:38:26 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Mon, 24 Apr 2017 23:38:27 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-6-openjdk-amd64
# Mon, 24 Apr 2017 23:38:27 GMT
ENV JAVA_VERSION=6b38
# Mon, 24 Apr 2017 23:38:28 GMT
ENV JAVA_DEBIAN_VERSION=6b38-1.13.10-1~deb7u1
# Mon, 24 Apr 2017 23:39:11 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-6-jdk="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
```

-	Layers:
	-	`sha256:1d46ed2a74b7da1620376a8b57cf77856ed64160d01186fc015979796e664085`  
		Last Modified: Mon, 24 Apr 2017 19:41:46 GMT  
		Size: 38.1 MB (38117052 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d9304274c9ac261b14cf3ee7685f9120bed42c9a833a7337975a9975750eed1`  
		Last Modified: Mon, 24 Apr 2017 22:28:57 GMT  
		Size: 7.0 MB (6953934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d844091a3ba3d7bd7708b0f781a9fcae97c8d5ebfa2b8d04a2296ea91ff73eed`  
		Last Modified: Mon, 24 Apr 2017 22:29:33 GMT  
		Size: 37.9 MB (37942506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:817d06185f498fa093500909bedb6d26cb8f90a948c9787bf71646ee47954eec`  
		Last Modified: Tue, 25 Apr 2017 00:45:35 GMT  
		Size: 419.3 KB (419314 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a964321e3a6810560b12d34369ab900dec5f3155c8c1e70ab02c303545205dc`  
		Last Modified: Tue, 25 Apr 2017 00:45:34 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a0e98ea1dff88cd09fd9fb058f47ee53a75b522c9e7caa8f483ab094357b6e4`  
		Last Modified: Tue, 25 Apr 2017 00:45:49 GMT  
		Size: 106.1 MB (106108286 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
