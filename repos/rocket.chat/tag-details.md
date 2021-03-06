<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `rocket.chat`

-	[`rocket.chat:0.55.1`](#rocketchat0551)
-	[`rocket.chat:0.55`](#rocketchat055)
-	[`rocket.chat:0`](#rocketchat0)
-	[`rocket.chat:latest`](#rocketchatlatest)

## `rocket.chat:0.55.1`

```console
$ docker pull rocket.chat@sha256:22a67f20b9c8c65cb1325eb2dfcf526d12cb3d6383fd8d638bfb75980094544a
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0.55.1` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **197.8 MB (197835836 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:df49285f721351998a612c28f814254dee2cb259bf2ea99d0d62a0a4724b7509`
-	Default Command: `["node","main.js"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:13:42 GMT
MAINTAINER buildmaster@rocket.chat
# Thu, 20 Apr 2017 20:13:43 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Thu, 20 Apr 2017 20:13:44 GMT
VOLUME [/app/uploads]
# Thu, 20 Apr 2017 21:00:03 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 25 Apr 2017 01:21:17 GMT
ENV RC_VERSION=0.55.1
# Tue, 25 Apr 2017 01:21:18 GMT
WORKDIR /app
# Tue, 25 Apr 2017 01:22:06 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 25 Apr 2017 01:22:06 GMT
USER [rocketchat]
# Tue, 25 Apr 2017 01:22:07 GMT
WORKDIR /app/bundle
# Tue, 25 Apr 2017 01:22:10 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 25 Apr 2017 01:22:10 GMT
EXPOSE 3000/tcp
# Tue, 25 Apr 2017 01:22:11 GMT
CMD ["node" "main.js"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cab282ab6aac198869b7c551426bbf35ef840cc0d2d3027cda54cab19fc3be9a`  
		Last Modified: Thu, 20 Apr 2017 21:01:09 GMT  
		Size: 2.1 KB (2148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c96c45c7198058e775a3bdeac9d8e385b1713d17bcb68cbf551b2ebd3cb9ea5`  
		Last Modified: Thu, 20 Apr 2017 21:01:10 GMT  
		Size: 127.2 KB (127204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b19d7c99181e00e0fe5b7fc3c1486042ef7de18c0b18b4f1753c5a0adc4cc0f4`  
		Last Modified: Tue, 25 Apr 2017 01:22:53 GMT  
		Size: 114.4 MB (114399779 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:0.55`

```console
$ docker pull rocket.chat@sha256:22a67f20b9c8c65cb1325eb2dfcf526d12cb3d6383fd8d638bfb75980094544a
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0.55` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **197.8 MB (197835836 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:df49285f721351998a612c28f814254dee2cb259bf2ea99d0d62a0a4724b7509`
-	Default Command: `["node","main.js"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:13:42 GMT
MAINTAINER buildmaster@rocket.chat
# Thu, 20 Apr 2017 20:13:43 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Thu, 20 Apr 2017 20:13:44 GMT
VOLUME [/app/uploads]
# Thu, 20 Apr 2017 21:00:03 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 25 Apr 2017 01:21:17 GMT
ENV RC_VERSION=0.55.1
# Tue, 25 Apr 2017 01:21:18 GMT
WORKDIR /app
# Tue, 25 Apr 2017 01:22:06 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 25 Apr 2017 01:22:06 GMT
USER [rocketchat]
# Tue, 25 Apr 2017 01:22:07 GMT
WORKDIR /app/bundle
# Tue, 25 Apr 2017 01:22:10 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 25 Apr 2017 01:22:10 GMT
EXPOSE 3000/tcp
# Tue, 25 Apr 2017 01:22:11 GMT
CMD ["node" "main.js"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cab282ab6aac198869b7c551426bbf35ef840cc0d2d3027cda54cab19fc3be9a`  
		Last Modified: Thu, 20 Apr 2017 21:01:09 GMT  
		Size: 2.1 KB (2148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c96c45c7198058e775a3bdeac9d8e385b1713d17bcb68cbf551b2ebd3cb9ea5`  
		Last Modified: Thu, 20 Apr 2017 21:01:10 GMT  
		Size: 127.2 KB (127204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b19d7c99181e00e0fe5b7fc3c1486042ef7de18c0b18b4f1753c5a0adc4cc0f4`  
		Last Modified: Tue, 25 Apr 2017 01:22:53 GMT  
		Size: 114.4 MB (114399779 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:0`

```console
$ docker pull rocket.chat@sha256:22a67f20b9c8c65cb1325eb2dfcf526d12cb3d6383fd8d638bfb75980094544a
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **197.8 MB (197835836 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:df49285f721351998a612c28f814254dee2cb259bf2ea99d0d62a0a4724b7509`
-	Default Command: `["node","main.js"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:13:42 GMT
MAINTAINER buildmaster@rocket.chat
# Thu, 20 Apr 2017 20:13:43 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Thu, 20 Apr 2017 20:13:44 GMT
VOLUME [/app/uploads]
# Thu, 20 Apr 2017 21:00:03 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 25 Apr 2017 01:21:17 GMT
ENV RC_VERSION=0.55.1
# Tue, 25 Apr 2017 01:21:18 GMT
WORKDIR /app
# Tue, 25 Apr 2017 01:22:06 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 25 Apr 2017 01:22:06 GMT
USER [rocketchat]
# Tue, 25 Apr 2017 01:22:07 GMT
WORKDIR /app/bundle
# Tue, 25 Apr 2017 01:22:10 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 25 Apr 2017 01:22:10 GMT
EXPOSE 3000/tcp
# Tue, 25 Apr 2017 01:22:11 GMT
CMD ["node" "main.js"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cab282ab6aac198869b7c551426bbf35ef840cc0d2d3027cda54cab19fc3be9a`  
		Last Modified: Thu, 20 Apr 2017 21:01:09 GMT  
		Size: 2.1 KB (2148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c96c45c7198058e775a3bdeac9d8e385b1713d17bcb68cbf551b2ebd3cb9ea5`  
		Last Modified: Thu, 20 Apr 2017 21:01:10 GMT  
		Size: 127.2 KB (127204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b19d7c99181e00e0fe5b7fc3c1486042ef7de18c0b18b4f1753c5a0adc4cc0f4`  
		Last Modified: Tue, 25 Apr 2017 01:22:53 GMT  
		Size: 114.4 MB (114399779 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:latest`

```console
$ docker pull rocket.chat@sha256:22a67f20b9c8c65cb1325eb2dfcf526d12cb3d6383fd8d638bfb75980094544a
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **197.8 MB (197835836 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:df49285f721351998a612c28f814254dee2cb259bf2ea99d0d62a0a4724b7509`
-	Default Command: `["node","main.js"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:07:44 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 07 Apr 2017 17:22:07 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Fri, 07 Apr 2017 17:22:08 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 07 Apr 2017 17:42:47 GMT
ENV NODE_VERSION=4.8.2
# Fri, 07 Apr 2017 17:42:57 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Thu, 20 Apr 2017 14:42:14 GMT
ENV YARN_VERSION=0.23.2
# Thu, 20 Apr 2017 14:42:19 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Thu, 20 Apr 2017 14:42:19 GMT
CMD ["node"]
# Thu, 20 Apr 2017 20:13:42 GMT
MAINTAINER buildmaster@rocket.chat
# Thu, 20 Apr 2017 20:13:43 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Thu, 20 Apr 2017 20:13:44 GMT
VOLUME [/app/uploads]
# Thu, 20 Apr 2017 21:00:03 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 25 Apr 2017 01:21:17 GMT
ENV RC_VERSION=0.55.1
# Tue, 25 Apr 2017 01:21:18 GMT
WORKDIR /app
# Tue, 25 Apr 2017 01:22:06 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 25 Apr 2017 01:22:06 GMT
USER [rocketchat]
# Tue, 25 Apr 2017 01:22:07 GMT
WORKDIR /app/bundle
# Tue, 25 Apr 2017 01:22:10 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 25 Apr 2017 01:22:10 GMT
EXPOSE 3000/tcp
# Tue, 25 Apr 2017 01:22:11 GMT
CMD ["node" "main.js"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1c75255d33f781986e7e2731d7b17bf4675d02f4e956371310df4658cf1b1b2`  
		Last Modified: Thu, 23 Mar 2017 00:09:59 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c48deb3bd78b506d15abe7050a46deee302eb4f22d5adf606585294a27db959c`  
		Last Modified: Fri, 07 Apr 2017 17:48:00 GMT  
		Size: 119.1 KB (119061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed263e062728d3aa71f25aadd88fb7378277d7475e1a0a59a0a159bb45931a0f`  
		Last Modified: Fri, 07 Apr 2017 18:02:40 GMT  
		Size: 12.3 MB (12252077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e621205ed034f9c20194946bb307773b3c9edccc3df4aba32dc8f4641c3a466`  
		Last Modified: Thu, 20 Apr 2017 14:59:14 GMT  
		Size: 886.3 KB (886267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cab282ab6aac198869b7c551426bbf35ef840cc0d2d3027cda54cab19fc3be9a`  
		Last Modified: Thu, 20 Apr 2017 21:01:09 GMT  
		Size: 2.1 KB (2148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c96c45c7198058e775a3bdeac9d8e385b1713d17bcb68cbf551b2ebd3cb9ea5`  
		Last Modified: Thu, 20 Apr 2017 21:01:10 GMT  
		Size: 127.2 KB (127204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b19d7c99181e00e0fe5b7fc3c1486042ef7de18c0b18b4f1753c5a0adc4cc0f4`  
		Last Modified: Tue, 25 Apr 2017 01:22:53 GMT  
		Size: 114.4 MB (114399779 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
