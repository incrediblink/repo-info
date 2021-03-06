## `traefik:latest`

```console
$ docker pull traefik@sha256:2a9da62973c54cf6f68bfb7ddc8f936db5c831451fab6bf158a6202d9e2d5252
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8

### `traefik:latest` - linux; amd64

```console
$ docker pull traefik@sha256:9ca34f270de8c49fe611d9e778bdf5bed68522cdc92448bffcfccb56a71c5180
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.8 MB (14848372 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:deeeb64f56362644344ed2696d20d08ee9ef1a6a31da4309939b453b3b23a058`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Fri, 03 Nov 2017 22:11:40 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Mon, 14 May 2018 23:50:08 GMT
COPY file:51b2288d9cdd0fb718d983ff64560f88b0cb43fbc39cbf0d8c75ad6643985d03 in / 
# Mon, 14 May 2018 23:50:08 GMT
EXPOSE 80/tcp
# Mon, 14 May 2018 23:50:08 GMT
ENTRYPOINT ["/traefik"]
# Mon, 14 May 2018 23:50:08 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.6.1 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:5d3835484afecc78dccfa2f7d4fcf273aacfe0c7600b957314e38488f3942045`  
		Last Modified: Fri, 03 Nov 2017 22:12:12 GMT  
		Size: 155.2 KB (155152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c3defc93798f2d5db853d5537f73597239756060b700e65e59ae321a12b308d`  
		Last Modified: Mon, 14 May 2018 23:50:37 GMT  
		Size: 14.7 MB (14693220 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `traefik:latest` - linux; arm variant v6

```console
$ docker pull traefik@sha256:b37cb00a28980d44b615fcbeebf3433dd423a14a2135ba8dc6f77256b8af6ef3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **14.2 MB (14231672 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dabc6e00614f0d2817f79f2ea425063f623d0d60f65ef9c4c4c7e88b529417ed`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Tue, 24 Oct 2017 23:48:27 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Tue, 15 May 2018 07:59:44 GMT
COPY file:ab12052fad4e554fd3eee4955a5137934b521f1e18cd1e1b33f51b3c5445f2d1 in / 
# Tue, 15 May 2018 07:59:44 GMT
EXPOSE 80/tcp
# Tue, 15 May 2018 07:59:44 GMT
ENTRYPOINT ["/traefik"]
# Tue, 15 May 2018 07:59:44 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.6.1 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:8996ab8c9ae2c6afe7d318a3784c7ba1b1b72d4ae14cf515d4c1490aae91cab0`  
		Last Modified: Tue, 24 Oct 2017 23:48:35 GMT  
		Size: 155.2 KB (155184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccdaa53fbd0d780666bd946bfcea46778eb44299c8ef5beff4f6844ce40a592e`  
		Last Modified: Tue, 15 May 2018 08:00:10 GMT  
		Size: 14.1 MB (14076488 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `traefik:latest` - linux; arm64 variant v8

```console
$ docker pull traefik@sha256:eaa391ea3ad1a601680bc875d39553e1d825e60681e830c9516fde17371cca86
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **13.9 MB (13937610 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:afd5dd7f972f4e4a035765d2b84319106e590b877f809ab2a8eec58d811c7a90`
-	Entrypoint: `["\/traefik"]`

```dockerfile
# Wed, 25 Oct 2017 04:54:39 GMT
COPY file:d8282341d1fb7d2cc3d5d3523d0d4126066cc1ba8abe3f0047a459b3a63a5653 in /etc/ssl/certs/ 
# Tue, 15 May 2018 13:46:05 GMT
COPY file:cf4deff64d8671ac4636e12ddcae74cde4a2efb1d1eab8ffa843c28aa36a8958 in / 
# Tue, 15 May 2018 13:46:06 GMT
EXPOSE 80/tcp
# Tue, 15 May 2018 13:46:13 GMT
ENTRYPOINT ["/traefik"]
# Tue, 15 May 2018 13:46:14 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.6.1 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:78fe135ba97a13abc86dbe373975f0d0712d8aa6e540e09824b715a55d7e2ed3`  
		Last Modified: Wed, 25 Oct 2017 04:55:01 GMT  
		Size: 155.2 KB (155151 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28722174cac1c82a9ca302218c6e0bf04f309677c9490ab3712e72a79f689364`  
		Last Modified: Tue, 15 May 2018 13:47:30 GMT  
		Size: 13.8 MB (13782459 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
