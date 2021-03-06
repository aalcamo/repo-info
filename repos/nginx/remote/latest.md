## `nginx:latest`

```console
$ docker pull nginx@sha256:e6693c20186f837fc393390135d8a598a96a833917917789d63766cab6c59582
```

-	Platforms:
	-	linux; amd64

### `nginx:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.8 MB (71762415 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5766334bdaa0bc37f1f0c02cb94c351f9b076bcffa042d6ce811b0fd9bc31f3b`
-	Default Command: `["nginx","-g","daemon off;"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 22:06:58 GMT
MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"
# Thu, 06 Apr 2017 16:28:34 GMT
ENV NGINX_VERSION=1.11.13-1~jessie
# Thu, 06 Apr 2017 16:28:35 GMT
RUN set -e; 	NGINX_GPGKEY=573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62; 	found=''; 	for server in 		ha.pool.sks-keyservers.net 		hkp://keyserver.ubuntu.com:80 		hkp://p80.pool.sks-keyservers.net:80 		pgp.mit.edu 	; do 		echo "Fetching GPG key $NGINX_GPGKEY from $server"; 		apt-key adv --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$NGINX_GPGKEY" && found=yes && break; 	done; 	test -z "$found" && echo >&2 "error: failed to fetch GPG key $NGINX_GPGKEY" && exit 1; 	exit 0
# Thu, 06 Apr 2017 16:28:49 GMT
RUN echo "deb http://nginx.org/packages/mainline/debian/ jessie nginx" >> /etc/apt/sources.list 	&& apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y 						ca-certificates 						nginx=${NGINX_VERSION} 						nginx-module-xslt 						nginx-module-geoip 						nginx-module-image-filter 						nginx-module-perl 						nginx-module-njs 						gettext-base 	&& rm -rf /var/lib/apt/lists/*
# Thu, 06 Apr 2017 16:28:50 GMT
RUN ln -sf /dev/stdout /var/log/nginx/access.log 	&& ln -sf /dev/stderr /var/log/nginx/error.log
# Thu, 06 Apr 2017 16:28:51 GMT
EXPOSE 443/tcp 80/tcp
# Thu, 06 Apr 2017 16:28:51 GMT
CMD ["nginx" "-g" "daemon off;"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8f2e0556751d70841519ecfadb2e5033d358b69ad6361f50386ecafa1bd8ea7`  
		Last Modified: Thu, 06 Apr 2017 16:30:08 GMT  
		Size: 5.0 KB (5036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c9972dca3fdda93b980205cb5319e44a5ecd3493c89501b085694e25842defe`  
		Last Modified: Thu, 06 Apr 2017 16:30:13 GMT  
		Size: 20.3 MB (20318707 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:451b9524cb063772e4429c5cdf98081e4d1fd04d0073ab83a628e4db06bd1737`  
		Last Modified: Thu, 06 Apr 2017 16:30:08 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
