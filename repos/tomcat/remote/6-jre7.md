## `tomcat:6-jre7`

```console
$ docker pull tomcat@sha256:f74e20bab3ca234e8cedc2cd27fccefb12d5640c11f95811326fd1c5d3a848f4
```

-	Platforms:
	-	linux; amd64

### `tomcat:6-jre7` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **162.1 MB (162067085 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1bca0b8a2c5962475d2a49997065e0fbf2752db421187849764a956565d9bfe`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:54:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:40:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:40:06 GMT
ENV LANG=C.UTF-8
# Tue, 25 Apr 2017 00:40:07 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 25 Apr 2017 00:40:08 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
# Tue, 25 Apr 2017 00:40:09 GMT
ENV JAVA_VERSION=7u121
# Tue, 25 Apr 2017 00:40:09 GMT
ENV JAVA_DEBIAN_VERSION=7u121-2.6.8-2~deb8u1
# Tue, 25 Apr 2017 00:40:49 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 25 Apr 2017 01:24:40 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Tue, 25 Apr 2017 01:24:41 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 01:24:44 GMT
RUN mkdir -p "$CATALINA_HOME"
# Tue, 25 Apr 2017 01:24:44 GMT
WORKDIR /usr/local/tomcat
# Tue, 25 Apr 2017 01:24:45 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Tue, 25 Apr 2017 01:24:46 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Tue, 25 Apr 2017 01:24:46 GMT
ENV OPENSSL_VERSION=1.1.0e-1
# Tue, 25 Apr 2017 01:24:48 GMT
RUN { 		echo 'deb http://deb.debian.org/debian stretch main'; 	} > /etc/apt/sources.list.d/stretch.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release n=stretch'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: openssl libssl*'; 		echo "Pin: version $OPENSSL_VERSION"; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/stretch-openssl
# Tue, 25 Apr 2017 01:25:06 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 		openssl="$OPENSSL_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 01:25:07 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 80FF76D88A969FE46108558A80B953A041E49465 8B39757B1D8A994DF2433ED58B3A601F08C975E5 A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 B3F49CD3B9BD2996DA90F817ED3873F5D3262722 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Tue, 25 Apr 2017 01:25:13 GMT
RUN set -ex; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Tue, 25 Apr 2017 01:25:14 GMT
ENV TOMCAT_MAJOR=6
# Tue, 25 Apr 2017 01:25:14 GMT
ENV TOMCAT_VERSION=6.0.53
# Tue, 25 Apr 2017 01:25:15 GMT
ENV TOMCAT_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-6/v6.0.53/bin/apache-tomcat-6.0.53.tar.gz
# Tue, 25 Apr 2017 01:25:16 GMT
ENV TOMCAT_ASC_URL=https://www.apache.org/dist/tomcat/tomcat-6/v6.0.53/bin/apache-tomcat-6.0.53.tar.gz.asc
# Tue, 25 Apr 2017 01:26:02 GMT
RUN set -x 		&& wget -O tomcat.tar.gz "$TOMCAT_TGZ_URL" 	&& wget -O tomcat.tar.gz.asc "$TOMCAT_ASC_URL" 	&& gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz 	&& tar -xvf tomcat.tar.gz --strip-components=1 	&& rm bin/*.bat 	&& rm tomcat.tar.gz* 		&& nativeBuildDir="$(mktemp -d)" 	&& tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1 	&& nativeBuildDeps=" 		gcc 		libapr1-dev 		libssl-dev 		make 		openjdk-${JAVA_VERSION%%[-~bu]*}-jdk=$JAVA_DEBIAN_VERSION 	" 	&& apt-get update && apt-get install -y --no-install-recommends $nativeBuildDeps && rm -rf /var/lib/apt/lists/* 	&& ( 		export CATALINA_HOME="$PWD" 		&& cd "$nativeBuildDir/native" 		&& ./configure 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes 		&& make -j$(nproc) 		&& make install 	) 	&& apt-get purge -y --auto-remove $nativeBuildDeps 	&& rm -rf "$nativeBuildDir" 	&& rm bin/tomcat-native.tar.gz
# Tue, 25 Apr 2017 01:26:02 GMT
EXPOSE 8080/tcp
# Tue, 25 Apr 2017 01:26:03 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e39c3ffe41332a7a3c7f85f57e547361ec90b6e0091dd6058e06acccde2217d4`  
		Last Modified: Mon, 24 Apr 2017 22:19:28 GMT  
		Size: 19.3 MB (19266225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aac3320edf402163d25e312e38b3611696a39ea8cefb0f58bda4e29bf980ed0a`  
		Last Modified: Tue, 25 Apr 2017 00:50:41 GMT  
		Size: 573.7 KB (573718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16bca657a5b49bc714d81b3e3b0310bcf8d9a48837e8b4acd1fdfd10cfad25e1`  
		Last Modified: Tue, 25 Apr 2017 00:50:40 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab928e9ab29c94e2cc78fea8ce33e2951b4c5c0d04bb058fec55cd0b0fae68cf`  
		Last Modified: Tue, 25 Apr 2017 00:50:49 GMT  
		Size: 78.4 MB (78410868 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1906bfdc43ae7e3d6b71475e928d8991099332298b70835cb17f5e47654c7c45`  
		Last Modified: Tue, 25 Apr 2017 01:39:04 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef4fe90224d3f112ec824cc69df7c42c96152475581e779d37cfe42464744332`  
		Last Modified: Tue, 25 Apr 2017 01:39:04 GMT  
		Size: 329.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55ead578e5f752c362399dfbf18fe203b7a2550c00afe44762f4e37017242b97`  
		Last Modified: Tue, 25 Apr 2017 01:39:06 GMT  
		Size: 3.2 MB (3247931 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aca812690815b24f116953376fd50c2fd76276566623c5682fb481cb829cb4c7`  
		Last Modified: Tue, 25 Apr 2017 01:39:05 GMT  
		Size: 281.2 KB (281217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b2dc6317b04e812953fb70ed4aee93b7902772afaa4a53551303fe201f3187f`  
		Last Modified: Tue, 25 Apr 2017 01:39:06 GMT  
		Size: 7.7 MB (7736138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
