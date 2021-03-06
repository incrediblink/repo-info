## `nats-streaming:linux`

```console
$ docker pull nats-streaming@sha256:31ba90f7f23d52d018d0bf5b8fbe0c2f9459b7e977541b6cac36048dd03cf42a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm variant v7
	-	linux; arm64 variant v8

### `nats-streaming:linux` - linux; amd64

```console
$ docker pull nats-streaming@sha256:60463540bddbdfd42cbaf95defde86ca0d699edaf4bc300533abacffd9fa89ff
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.8 MB (3825772 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bf688abfd477120541b1f642059990f57809a8966a19f8640bf9df5744f46ff4`
-	Entrypoint: `["\/nats-streaming-server"]`
-	Default Command: `["-m","8222"]`

```dockerfile
# Tue, 03 Apr 2018 19:41:38 GMT
COPY file:e34751fb7cc16d518615e7b40cf76fc5d101c16162620a5b326c15f95d0f1073 in /nats-streaming-server 
# Tue, 03 Apr 2018 19:41:38 GMT
EXPOSE 4222/tcp 8222/tcp
# Tue, 03 Apr 2018 19:41:39 GMT
ENTRYPOINT ["/nats-streaming-server"]
# Tue, 03 Apr 2018 19:41:39 GMT
CMD ["-m" "8222"]
```

-	Layers:
	-	`sha256:3f0a5941c35d962fad7ac1a47bd612ae4cbf3597fd1547c0073b824ab2f763d5`  
		Last Modified: Tue, 03 Apr 2018 19:42:45 GMT  
		Size: 3.8 MB (3825772 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nats-streaming:linux` - linux; arm variant v6

```console
$ docker pull nats-streaming@sha256:76ce0730111f88101c0181ea1554a794c560a3e403248c29f7da9d7e6cc22c9b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.6 MB (3582300 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ac46c51a5e7aad95a2759c3d3064dc1cee74b7cc251a625caddcce8eea36b117`
-	Entrypoint: `["\/nats-streaming-server"]`
-	Default Command: `["-m","8222"]`

```dockerfile
# Tue, 03 Apr 2018 19:44:03 GMT
COPY file:4abe0279802570dcf5cb2b7b53d76523c36c25d6044621e2a27c552a95fa268a in /nats-streaming-server 
# Tue, 03 Apr 2018 19:44:03 GMT
EXPOSE 4222/tcp 5222/tcp 8222/tcp
# Tue, 03 Apr 2018 19:44:03 GMT
ENTRYPOINT ["/nats-streaming-server"]
# Tue, 03 Apr 2018 19:44:03 GMT
CMD ["-m" "8222"]
```

-	Layers:
	-	`sha256:b0ae9005c3becedf1b6ba48b265ffc0b2aec5153cfeb65bdb2c760a0b8afcb33`  
		Last Modified: Tue, 03 Apr 2018 19:44:14 GMT  
		Size: 3.6 MB (3582300 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nats-streaming:linux` - linux; arm variant v7

```console
$ docker pull nats-streaming@sha256:901476a2eadcb004d7953224b646a64f5b8515b0022569988d75f04f4015e17e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.6 MB (3579365 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:69ce8da611d6f3f5846d3b2db92133df77285928c29e9d78659de6143a13d32e`
-	Entrypoint: `["\/nats-streaming-server"]`
-	Default Command: `["-m","8222"]`

```dockerfile
# Tue, 03 Apr 2018 19:44:14 GMT
COPY file:e55ae8049ade53807670d4ece30083916225488051a6035b772f0ae933e14075 in /nats-streaming-server 
# Tue, 03 Apr 2018 19:44:15 GMT
EXPOSE 4222/tcp 5222/tcp 8222/tcp
# Tue, 03 Apr 2018 19:44:15 GMT
ENTRYPOINT ["/nats-streaming-server"]
# Tue, 03 Apr 2018 19:44:15 GMT
CMD ["-m" "8222"]
```

-	Layers:
	-	`sha256:5a3925afef1f98a6b267272941477e9acc69b70a06c99939bb634b9f6987a273`  
		Last Modified: Tue, 03 Apr 2018 19:44:31 GMT  
		Size: 3.6 MB (3579365 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nats-streaming:linux` - linux; arm64 variant v8

```console
$ docker pull nats-streaming@sha256:824be1736a9e94ae1d373fd4600377e0db07fad66ba7ff6dc0ba6e17789f3b88
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.5 MB (3488208 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c27b8a19870b072c74b578ae24b89744b50996bf9a92a23046df2b2dd638dc8a`
-	Entrypoint: `["\/nats-streaming-server"]`
-	Default Command: `["-m","8222"]`

```dockerfile
# Tue, 03 Apr 2018 19:54:43 GMT
COPY file:2778cdcb40902e151e5d3ac6e2de2a488342e59af5d64908762f35eb7d07a507 in /nats-streaming-server 
# Tue, 03 Apr 2018 19:55:02 GMT
EXPOSE 4222/tcp 5222/tcp 8222/tcp
# Tue, 03 Apr 2018 19:55:02 GMT
ENTRYPOINT ["/nats-streaming-server"]
# Tue, 03 Apr 2018 19:55:03 GMT
CMD ["-m" "8222"]
```

-	Layers:
	-	`sha256:75377ce2c0fc1bd6e92799f923da4a79eed68038afd94fc0598a1374e47f14b8`  
		Last Modified: Tue, 03 Apr 2018 19:55:45 GMT  
		Size: 3.5 MB (3488208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
