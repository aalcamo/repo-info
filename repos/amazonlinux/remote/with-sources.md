## `amazonlinux:with-sources`

```console
$ docker pull amazonlinux@sha256:c5bc0bd0721c1c610e5ac3a89afdcecf7ee21cdfe5a4872e94a59bf6d8e5775d
```

-	Platforms:
	-	linux; amd64

### `amazonlinux:with-sources` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **348.1 MB (348081797 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:971525df91672e6417e8562aeddda4bf1ff40d4cb192520e9ac694729ee009d0`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Fri, 07 Apr 2017 16:43:32 GMT
ADD file:f3cf8c8e1ec2c8a1def08d5a104ce873febd881e68bb614a36aa94fc158d0fe7 in / 
# Fri, 07 Apr 2017 16:43:33 GMT
CMD ["/bin/bash"]
# Fri, 07 Apr 2017 16:44:04 GMT
RUN mkdir /usr/src/srpm  && curl -o /usr/src/srpm/srpm-bundle.tar.gz "https://amazon-linux-docker-sources.s3-accelerate.amazonaws.com/srpm-bundle.tar.gz?versionId=eOPaBjB.7TEIToS3vvHMktlsQwnUWX96"  && echo "4ab23a8fffa5b6badfbf738e13bb10dd4d9700fde29a0c83c2b86362943a6974 /usr/src/srpm/srpm-bundle.tar.gz" | sha256sum -c -
```

-	Layers:
	-	`sha256:0793c64286b713d98c810dfb36d7d82246c58f3cf632897aaa197adc12962765`  
		Last Modified: Fri, 07 Apr 2017 16:44:42 GMT  
		Size: 59.5 MB (59530547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2c6833689f81f8dc23402878abf9e9a304a5264d016898ebf9d9a7688b4b4df`  
		Last Modified: Fri, 07 Apr 2017 16:46:08 GMT  
		Size: 288.6 MB (288551250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
