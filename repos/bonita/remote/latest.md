## `bonita:latest`

```console
$ docker pull bonita@sha256:849cc3304bf64d0e11190417e4f9b45d60694262a341582a8fb1eff5c6aecc47
```

-	Platforms:
	-	linux; amd64

### `bonita:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **217.0 MB (216979592 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aac1c8079aba6f5822484731bbef48719f355e11d544620b88de1be55d2a5774`
-	Default Command: `["\/opt\/files\/startup.sh"]`

```dockerfile
# Mon, 27 Feb 2017 19:40:39 GMT
ADD file:a642bdc2d8d6e4484e4419fc938e24b03454e36f389233f2ce77fc04722da900 in / 
# Mon, 27 Feb 2017 19:40:48 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 27 Feb 2017 19:40:49 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 27 Feb 2017 19:41:05 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 27 Feb 2017 19:41:06 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 27 Feb 2017 19:41:06 GMT
CMD ["/bin/bash"]
# Mon, 27 Feb 2017 22:43:09 GMT
MAINTAINER Jérémy Jacquier-Roux <jeremy.jacquier-roux@bonitasoft.org>
# Mon, 27 Feb 2017 22:44:00 GMT
RUN apt-get update && apt-get install -y   mysql-client-core-5.5   openjdk-7-jre-headless   postgresql-client   unzip   wget   zip   && rm -rf /var/lib/apt/lists/*
# Mon, 27 Feb 2017 22:44:00 GMT
RUN mkdir /opt/custom-init.d/
# Mon, 27 Feb 2017 22:44:01 GMT
RUN groupadd -r bonita -g 1000   && useradd -u 1000 -r -g bonita -d /opt/bonita/ -s /sbin/nologin -c "Bonita User" bonita
# Mon, 27 Feb 2017 22:44:03 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4
# Mon, 27 Feb 2017 22:44:07 GMT
RUN wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture)" -O /usr/local/bin/gosu   && wget -q "https://github.com/tianon/gosu/releases/download/1.6/gosu-$(dpkg --print-architecture).asc" -O /usr/local/bin/gosu.asc   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu
# Tue, 28 Mar 2017 17:05:47 GMT
ARG BONITA_VERSION
# Tue, 28 Mar 2017 17:05:47 GMT
ARG TOMCAT_VERSION
# Tue, 28 Mar 2017 17:05:48 GMT
ARG BONITA_SHA256
# Tue, 28 Mar 2017 17:05:48 GMT
ARG BONITA_URL
# Tue, 28 Mar 2017 17:05:49 GMT
ENV BONITA_VERSION=7.4.3
# Tue, 28 Mar 2017 17:05:50 GMT
ENV TOMCAT_VERSION=7.0.67
# Tue, 28 Mar 2017 17:05:50 GMT
ENV BONITA_SHA256=5129f43d1aad7e10441e4c0a73e0ab638a64e06fcd2859947b782e08fe9b6bab
# Tue, 28 Mar 2017 17:05:51 GMT
ENV BONITA_URL=http://download.forge.ow2.org/bonita/BonitaBPMCommunity-7.4.3-Tomcat-7.0.67.zip
# Tue, 28 Mar 2017 17:06:03 GMT
RUN mkdir /opt/files   && wget -q ${BONITA_URL} -O /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Tue, 28 Mar 2017 17:06:04 GMT
RUN sha256sum /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip
# Tue, 28 Mar 2017 17:06:06 GMT
RUN echo "$BONITA_SHA256" /opt/files/BonitaBPMCommunity-${BONITA_VERSION}-Tomcat-${TOMCAT_VERSION}.zip | sha256sum -c -
# Tue, 28 Mar 2017 17:06:07 GMT
VOLUME [/opt/bonita]
# Tue, 28 Mar 2017 17:06:08 GMT
COPY dir:9a4e5e16ecaf38cc54b83e4c92a5f49851cda4f8d38d0cfe3c6a1849e3765b28 in /opt/files 
# Tue, 28 Mar 2017 17:06:08 GMT
COPY dir:0f5b28efb7aa0114806152fbcfef64599a58d3bd42d494d262f29d8f3408ea15 in /opt/templates 
# Tue, 28 Mar 2017 17:06:09 GMT
EXPOSE 8080/tcp
# Tue, 28 Mar 2017 17:06:10 GMT
CMD ["/opt/files/startup.sh"]
```

-	Layers:
	-	`sha256:30d541b48fc05d2a1b2b0ac6a74f3df70e928c3edc253d5bce5dc6ae1fad55d2`  
		Last Modified: Mon, 27 Feb 2017 19:46:55 GMT  
		Size: 65.7 MB (65693630 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ecd7f80d390b9e9a009363abea9fb2bb53e8104b4fc2f7abe00ee254005af1c`  
		Last Modified: Mon, 27 Feb 2017 19:46:34 GMT  
		Size: 71.6 KB (71555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46ec9927bb81d07ac2602292888b2c61213d51d1a4eeef6354fb9734246e52da`  
		Last Modified: Mon, 27 Feb 2017 19:46:34 GMT  
		Size: 357.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2e67a4d67b44968a2e2b40b1a22c6ad3192a9a490f1a47824f1309f8b97d30e5`  
		Last Modified: Mon, 27 Feb 2017 19:46:34 GMT  
		Size: 680.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d9dd91554882183cb5d1cd512479487e10f495c22d035a62fbb3ee38d89cf48`  
		Last Modified: Mon, 27 Feb 2017 19:46:35 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f8a9ece2ab54505896ac4c64bf6c03753f9e35b2cb87ce04d05f0b6afef8c2d`  
		Last Modified: Wed, 01 Mar 2017 22:45:56 GMT  
		Size: 65.1 MB (65055354 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3926b08578e0ea40880f0730ee8030603c3132c3a479d9a62923c128c4098971`  
		Last Modified: Wed, 01 Mar 2017 22:45:41 GMT  
		Size: 117.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a414a1469bcedd9a189d75a862a699d20ec990b49fdd27f08c4c26afbb25923`  
		Last Modified: Wed, 01 Mar 2017 22:45:41 GMT  
		Size: 1.8 KB (1784 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:faa5d9e5aeeebe131b96abd1eebb921abc7d9890e900cb7268df1e08e22c6f81`  
		Last Modified: Wed, 01 Mar 2017 22:45:41 GMT  
		Size: 123.2 KB (123203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db233e7f9c3dedc80952e1f673828c699593168c07dbb737254f53bff9a4f5f5`  
		Last Modified: Wed, 01 Mar 2017 22:45:39 GMT  
		Size: 807.6 KB (807588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:814c690ea185d3b0f52fdada6387603d3d62337c2b2cf0a2706c1160bb2a3c4e`  
		Last Modified: Tue, 28 Mar 2017 17:07:00 GMT  
		Size: 85.2 MB (85217545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:407ac9477cb1b5aafdf4d8ce49882bbd0de74bfb6c0aa07a36601e8d3bdc373f`  
		Last Modified: Tue, 28 Mar 2017 17:06:54 GMT  
		Size: 6.0 KB (6013 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5ade7728d07c9caaec4b85644f44a4720b1f1f0059aca955817f297b135edf`  
		Last Modified: Tue, 28 Mar 2017 17:06:54 GMT  
		Size: 1.6 KB (1604 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
