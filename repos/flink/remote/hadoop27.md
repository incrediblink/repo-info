## `flink:hadoop27`

```console
$ docker pull flink@sha256:5a4eb5544c812c74a7e025ff1e2026b2f48a6ae8b3d69bb6cff65c3d0a6910c2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `flink:hadoop27` - linux; amd64

```console
$ docker pull flink@sha256:7012af5cc0cb6824ad1d699810d32cdfedf5eefd5955f539b45f662833deb8a0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **409.5 MB (409541846 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d2c574d0c2152fad5d0c8d6876486e3a450267b93d9f63fe3f069803aff8ab1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["help"]`

```dockerfile
# Sat, 28 Apr 2018 07:08:53 GMT
ADD file:9572fdb59dfbb9b032f3331bbc2a08b31e0aef5fbde44c8f2008d22bf5290cf2 in / 
# Sat, 28 Apr 2018 07:08:53 GMT
CMD ["bash"]
# Fri, 04 May 2018 17:41:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 04 May 2018 17:41:17 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Fri, 04 May 2018 23:51:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 04 May 2018 23:51:32 GMT
ENV LANG=C.UTF-8
# Fri, 04 May 2018 23:51:33 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 04 May 2018 23:51:34 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Fri, 04 May 2018 23:51:34 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Fri, 04 May 2018 23:51:34 GMT
ENV JAVA_VERSION=8u171
# Fri, 04 May 2018 23:51:34 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Fri, 04 May 2018 23:51:35 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Mon, 14 May 2018 22:44:43 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Mon, 14 May 2018 22:44:45 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 15 May 2018 00:47:02 GMT
RUN set -ex;   apt-get update;   apt-get -y install libsnappy1v5;   rm -rf /var/lib/apt/lists/*
# Tue, 15 May 2018 00:47:03 GMT
ENV GOSU_VERSION=1.7
# Tue, 15 May 2018 00:47:09 GMT
RUN set -ex;   wget -nv -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)";   wget -nv -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc";   export GNUPGHOME="$(mktemp -d)";   gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4;   gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu;   rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc;   chmod +x /usr/local/bin/gosu;   gosu nobody true
# Tue, 15 May 2018 00:54:20 GMT
ENV FLINK_VERSION=1.4.2 HADOOP_VERSION=27 SCALA_VERSION=2.11
# Tue, 15 May 2018 00:54:21 GMT
ENV FLINK_HOME=/opt/flink
# Tue, 15 May 2018 00:54:21 GMT
ENV PATH=/opt/flink/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 15 May 2018 00:54:22 GMT
RUN groupadd --system --gid=9999 flink &&     useradd --system --home-dir $FLINK_HOME --uid=9999 --gid=flink flink
# Tue, 15 May 2018 00:54:22 GMT
WORKDIR /opt/flink
# Tue, 15 May 2018 00:54:22 GMT
ENV FLINK_URL_FILE_PATH=flink/flink-1.4.2/flink-1.4.2-bin-hadoop27-scala_2.11.tgz
# Tue, 15 May 2018 00:54:22 GMT
ENV FLINK_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=flink/flink-1.4.2/flink-1.4.2-bin-hadoop27-scala_2.11.tgz FLINK_ASC_URL=https://www.apache.org/dist/flink/flink-1.4.2/flink-1.4.2-bin-hadoop27-scala_2.11.tgz.asc
# Tue, 15 May 2018 00:54:23 GMT
COPY file:d9b980b40ddcfab2700a72e4088616452368e14c4f8fbee56f3258ac7f5dd913 in /KEYS 
# Tue, 15 May 2018 00:55:11 GMT
RUN set -ex;   wget -nv -O flink.tgz "$FLINK_TGZ_URL";   wget -nv -O flink.tgz.asc "$FLINK_ASC_URL";     export GNUPGHOME="$(mktemp -d)";   gpg --import /KEYS;   gpg --batch --verify flink.tgz.asc flink.tgz;   rm -rf "$GNUPGHOME" flink.tgz.asc;     tar -xf flink.tgz --strip-components=1;   rm flink.tgz;     chown -R flink:flink .;
# Tue, 15 May 2018 00:55:11 GMT
COPY file:dd3a2212d5f0bbe552ac5e863e5fb1df12bcbb32cff887e6f4f3c81e2372b6c1 in / 
# Tue, 15 May 2018 00:55:11 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 15 May 2018 00:55:11 GMT
EXPOSE 6123/tcp 8081/tcp
# Tue, 15 May 2018 00:55:12 GMT
CMD ["help"]
```

-	Layers:
	-	`sha256:cc1a78bfd46becbfc3abb8a74d9a70a0e0dc7a5809bbd12e814f9382db003707`  
		Last Modified: Sat, 28 Apr 2018 09:27:54 GMT  
		Size: 45.3 MB (45318159 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6861473222a6f5fb6abe08f0cdebf56b5f42758b0a7430bbbf47a3d365198e5e`  
		Last Modified: Fri, 04 May 2018 18:20:41 GMT  
		Size: 10.8 MB (10773612 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e0b9c3b5ae080d11df6df788ce96a45b684d7b050fd017c06b4ea5a40f58545`  
		Last Modified: Fri, 04 May 2018 18:20:39 GMT  
		Size: 4.3 MB (4335883 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae14ee39877acb45fb6c2157e51ddcd4690ac64ed50b0bbd417eb101518ef81d`  
		Last Modified: Sat, 05 May 2018 00:08:21 GMT  
		Size: 853.1 KB (853090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8085c1b536f02629bdd8a7a1ba474b47b4c842019776b964d5d34e9100a1c07a`  
		Last Modified: Sat, 05 May 2018 00:08:20 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e1431e84c0ce069ca47afe14c3caab9012a2c46f70788f1bdf4b2ec5e4a7e63`  
		Last Modified: Sat, 05 May 2018 00:08:20 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca0e3df5a1fd8d55deb4e05d5d22c6ebea2ecf9aab66b5d074a020339cf4fc28`  
		Last Modified: Mon, 14 May 2018 23:18:26 GMT  
		Size: 122.1 MB (122140587 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cb611ced6ca04659961659e0c74ec16433c5ae37a268283d342196ee6cf5fe`  
		Last Modified: Mon, 14 May 2018 23:17:54 GMT  
		Size: 272.1 KB (272121 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0541c7c550663ae1d58604c0eca3dbd70318beb20cdda5f0f17a6336900ebe10`  
		Last Modified: Tue, 15 May 2018 00:57:05 GMT  
		Size: 466.7 KB (466680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeadb4c5b7e381ca73ea519f21be474f91408e5e7def3e5aa426f8b1ceb87b4f`  
		Last Modified: Tue, 15 May 2018 00:57:05 GMT  
		Size: 819.2 KB (819184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:651011f03201f09a4fe19a18c2d04f206d7ff2d878b671ebcb041e46ed97d44a`  
		Last Modified: Tue, 15 May 2018 01:04:39 GMT  
		Size: 4.6 KB (4613 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eacb10145957c7be1344036e6386f7752a65abac1061c1b515e2b3f1324d52ce`  
		Last Modified: Tue, 15 May 2018 01:04:39 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8828db590e96d5d353fa5a2b37947d40261970787b98753d75ffacc95e10bb4e`  
		Last Modified: Tue, 15 May 2018 01:04:40 GMT  
		Size: 59.3 KB (59336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8e477cd7b0facaec029762d1c1cf6ae35ee79387abcc14c7e3ccf1611e0dcff`  
		Last Modified: Tue, 15 May 2018 01:04:56 GMT  
		Size: 224.5 MB (224496972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:135a6dc4add6bc67e5ecb8bdf69acf36f3d0274cad106fb52f13ffac347098ce`  
		Last Modified: Tue, 15 May 2018 01:04:39 GMT  
		Size: 1.1 KB (1118 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
