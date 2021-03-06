## `maven:3-jdk-9`

```console
$ docker pull maven@sha256:3a2be9f81f74c88e8e4b93a31de4faa571d0d34bca3ce720e6c74727906fac4a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `maven:3-jdk-9` - linux; amd64

```console
$ docker pull maven@sha256:8d5408a71872f71d1de07653e897f990dd69e444912100d34472bfb7988641da
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **391.3 MB (391252607 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:31dc1d7b06b61d3fb221e50878992061aecef5bd05e151606ab8099e00614f02`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 06:49:58 GMT
ADD file:229ad62fdc5e079bf925fb084264841ce27bf7125beb1fd821cbd6ed5132b37c in / 
# Sat, 28 Apr 2018 06:49:59 GMT
CMD ["bash"]
# Sat, 05 May 2018 04:59:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 04:59:18 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 04:59:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:02:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:02:05 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 08:02:06 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 08:06:41 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 08:06:41 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 08:06:41 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 08:06:42 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Mon, 14 May 2018 22:40:56 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Mon, 14 May 2018 22:40:57 GMT
CMD ["jshell"]
# Tue, 15 May 2018 02:12:05 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 02:12:05 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 02:12:05 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 02:12:06 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 02:12:06 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 02:12:09 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 02:12:09 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 02:12:09 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 02:12:10 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 02:12:10 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 02:12:10 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 02:12:10 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:e7cb83f94a464daabb5fa4e63ae521d65d7956bfcb3619bc75857f7d598ff12c`  
		Last Modified: Sat, 28 Apr 2018 08:58:22 GMT  
		Size: 48.3 MB (48303234 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2af7c2bd543ba42600867217cd2f676eae7c4c38a8ba8a3cf8edce489534cfe`  
		Last Modified: Sat, 05 May 2018 05:02:11 GMT  
		Size: 8.6 MB (8642335 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b5286ee17a380311ffd9b7f82c5c957c59358a2103c0a1cc96c0be7eb91528f`  
		Last Modified: Sat, 05 May 2018 05:02:10 GMT  
		Size: 9.5 MB (9459894 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7cd74685af848607530bf0bc1fe535821eb561e9a1d236afd06334c83ef5ba4d`  
		Last Modified: Sat, 05 May 2018 05:02:34 GMT  
		Size: 52.7 MB (52677473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f971e46f30b94b08d5a7313db7baa5633f2332093f2bda04cd223ba062300a6`  
		Last Modified: Sat, 05 May 2018 08:09:46 GMT  
		Size: 895.7 KB (895658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ef6c2ba70cafaa6461da912c989a1ea157a75f99c02e2cc5ca1da580b63c016`  
		Last Modified: Sat, 05 May 2018 08:09:46 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21d6caaade028cc319cf2bca215d2c998c4578b48e3d0b434182929e66ab6ff9`  
		Last Modified: Sat, 05 May 2018 08:16:46 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82654790da96cbdcd442fc0c5548e6419926657c2647105be57f81309482d27f`  
		Last Modified: Mon, 14 May 2018 23:13:56 GMT  
		Size: 262.3 MB (262326345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6250c9a51986bf8b574622a013dad580fb1e9aeec4b2393019898ca53ae1eb2`  
		Last Modified: Tue, 15 May 2018 02:17:26 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43204dd833c84ce9b4212c73ca579b744b453f1fe82a7e12e141e78c3ae12448`  
		Last Modified: Tue, 15 May 2018 02:17:27 GMT  
		Size: 8.9 MB (8945972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7c5ea0549f8db24fd0f0e515c13a862348a4f626d7f0379904df738c4f27e2d`  
		Last Modified: Tue, 15 May 2018 02:17:27 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0690c0da68eac8600931f0481dab8350ca3e1125b808db678e6cce94c4706270`  
		Last Modified: Tue, 15 May 2018 02:17:25 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; arm variant v5

```console
$ docker pull maven@sha256:9ba82c615749d393d6cd790718211f3a80f0a69682fcbbb1fa7a2e62c83b1bb3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **357.4 MB (357428789 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:425e5da2b4ac16c144c00eebc98870ba77ece3fe920c1c80588af3792bf57392`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 08:51:39 GMT
ADD file:289dd78ee91d70cba0d1bc2f296c3c14565c2fc5a7545ded07d727de72e2c7af in / 
# Sat, 28 Apr 2018 08:51:39 GMT
CMD ["bash"]
# Sat, 05 May 2018 08:57:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:57:59 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 08:58:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:21:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:21:49 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 09:21:50 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 09:29:05 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 09:29:05 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 09:29:05 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 09:29:06 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 09:44:01 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:44:02 GMT
CMD ["jshell"]
# Tue, 15 May 2018 11:30:49 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 11:30:49 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 11:30:50 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 11:30:50 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 11:30:51 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 11:30:53 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 11:30:53 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 11:30:53 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 11:30:54 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 11:30:54 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 11:30:54 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 11:30:55 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:e55988127988d265ae9a533cadc5ee50c9a724a2602f8677daa3d5ca1354a4c8`  
		Last Modified: Sat, 28 Apr 2018 08:59:59 GMT  
		Size: 46.3 MB (46298645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aafc48823c28e5748b4391dec0c3ace05a68f5a65301bb16529fbf5cfdcf4ba2`  
		Last Modified: Sat, 05 May 2018 09:11:24 GMT  
		Size: 7.8 MB (7807554 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fab5f6db056b1ea7d4547374cc334a044271698f505521bb613b98b4e9d62fff`  
		Last Modified: Sat, 05 May 2018 09:11:25 GMT  
		Size: 9.2 MB (9194241 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec4a548afcc00660ef6218b8d28d348b5de3b94fefc87bef82631c42056e8ee6`  
		Last Modified: Sat, 05 May 2018 09:11:57 GMT  
		Size: 50.2 MB (50176924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae6ec5ea4e73a466f57a6b546a9cad55615bd6493881162d69fcfbb397d6b75a`  
		Last Modified: Sat, 05 May 2018 09:43:09 GMT  
		Size: 888.9 KB (888926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c28e493916dad869bef88266b645a09302349c9f0452455f2ef5ed2a9d423a4`  
		Last Modified: Sat, 05 May 2018 09:43:08 GMT  
		Size: 235.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:083b8ad045c1ccc105171eb6e96ef13252cdebb816bbd8f8996de7786f62bb79`  
		Last Modified: Sat, 05 May 2018 09:54:01 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:27a073aa7cb821f2b0d5a2e3fcb4c5492f2243c05f7c9d9c06086df2bcfc6525`  
		Last Modified: Tue, 15 May 2018 10:16:00 GMT  
		Size: 234.1 MB (234114677 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67b75c8ab00148ca7ff95fd4abef69478058a99a06ca3cfccde59468b8b1cb12`  
		Last Modified: Tue, 15 May 2018 11:38:11 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67c812994c0121dd678ccda74cfa2a2b3fcc6f851347f83974b64ade58495fc5`  
		Last Modified: Tue, 15 May 2018 11:38:12 GMT  
		Size: 8.9 MB (8946132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:855f8a82428e2469c4aa7f5f18760be7ac14bfcd59c76aa75738f239e430d112`  
		Last Modified: Tue, 15 May 2018 11:38:11 GMT  
		Size: 739.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cf579ddfd7be7438fcecf77a217b6e75e374813db283118fb7055688a75eeb05`  
		Last Modified: Tue, 15 May 2018 11:38:11 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; arm variant v7

```console
$ docker pull maven@sha256:35ee1bd0ec67d46068003208bf9960905b89185305eba639375c396729c806e1
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **353.2 MB (353159125 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f0da23c182518031917be4af328b99bc2f66e49107633eb50c9015ad3fb8d53d`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 12:02:19 GMT
ADD file:b8fa078b9ddc39737b1c9eaeea11c4d1a71fb53d2ac6747fa0eab346280119a5 in / 
# Sat, 28 Apr 2018 12:02:20 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:10:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:10:53 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:11:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:50:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:50:09 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:50:10 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:57:27 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:57:28 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 12:57:28 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 12:57:28 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 12:15:51 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 12:15:53 GMT
CMD ["jshell"]
# Tue, 15 May 2018 13:46:14 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 13:46:14 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 13:46:14 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 13:46:15 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 13:46:16 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 13:46:18 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 13:46:18 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 13:46:18 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 13:46:19 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 13:46:19 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 13:46:20 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 13:46:20 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:bd36ef86ab3a0249a38384d63e39dbf85bd3f64d4e9ae0179795e2da5754d3fc`  
		Last Modified: Sat, 28 Apr 2018 12:13:46 GMT  
		Size: 44.2 MB (44193727 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2182099ef994efdc26b1608eeb96ebb41405847c6f253e40c752ec9246cce60`  
		Last Modified: Sat, 05 May 2018 12:33:28 GMT  
		Size: 7.5 MB (7535807 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5fedbfebaf2860a81e319ee9a8c18137fb801f56d7729af7b4698f98e05c62b`  
		Last Modified: Sat, 05 May 2018 12:33:28 GMT  
		Size: 8.9 MB (8899307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:496b1250aadf8322a3300af60aa0258966c4b2c12109c11bd182477c5514ef26`  
		Last Modified: Sat, 05 May 2018 12:34:02 GMT  
		Size: 47.9 MB (47926773 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:629e5fac21e671f199fc1cac252e622d21a20f37e79fe3630532931d2bb40e5f`  
		Last Modified: Sat, 05 May 2018 13:12:55 GMT  
		Size: 871.5 KB (871492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa7a7248d3ef3e6ee57ebcf46bc34d79eb8c65a74f73193128b9736553a5e46d`  
		Last Modified: Sat, 05 May 2018 13:12:55 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40ffb0eda337052eb22effaa319f5fd5387c72976e3c0299e9f0e17d3a618893`  
		Last Modified: Sat, 05 May 2018 13:25:48 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0aa2f457b9e58bbd78061df46aaaddc765e75aee3071dbe4bf3293e82adbb6d`  
		Last Modified: Tue, 15 May 2018 12:56:49 GMT  
		Size: 234.8 MB (234784189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ba77b8bfd597bb82247a2d4e1abe49dd1af5507aa0074381fdb1b4bd66e4596`  
		Last Modified: Tue, 15 May 2018 13:52:53 GMT  
		Size: 227.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2ce42d44a4273f975cddf483e9703dbc84b849d3ebcce3d513366317e56608f`  
		Last Modified: Tue, 15 May 2018 13:52:55 GMT  
		Size: 8.9 MB (8946132 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70152ebaf056054be75962a597fb4ba7b234074ca12283835ef283ba07f527a0`  
		Last Modified: Tue, 15 May 2018 13:52:53 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99e3e3315a44d54fff665a1062084fbf817b5e205912e071b7c9ca5eaf70ddaa`  
		Last Modified: Tue, 15 May 2018 13:52:53 GMT  
		Size: 360.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; arm64 variant v8

```console
$ docker pull maven@sha256:2ff312c44795ed4f51b1caa57717b449b4a85b3b35a460655382b58daa678071
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **362.5 MB (362497309 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c1c8d0b58a03de9ef004330e744ec79963a161dc072555cc8eb31e915c5cef2`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Mon, 30 Apr 2018 23:27:31 GMT
ADD file:ebaa7f02c60ac8138d085ce979847d36a1a8ce243bcef9b7e81e3e667d060dcb in / 
# Mon, 30 Apr 2018 23:27:34 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:27:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:28:24 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:30:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 11:20:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 11:20:11 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 11:20:15 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 11:55:18 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 11:55:19 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 11:55:20 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 11:55:22 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 09:48:46 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:48:51 GMT
CMD ["jshell"]
# Tue, 15 May 2018 14:11:10 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 14:11:11 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 14:11:12 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 14:11:12 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 14:11:14 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 14:11:23 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 14:11:28 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 14:11:28 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 14:11:29 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 14:11:30 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 14:11:31 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 14:11:32 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:ed5c004c8effeb24e6eee983af18662b0d28341fbbd46983746399c6df3358c8`  
		Last Modified: Mon, 30 Apr 2018 23:47:36 GMT  
		Size: 45.6 MB (45610129 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8023415c45ba32335bb869e25328b3b2c70e3ad264f1129bb133addb1fbfef4a`  
		Last Modified: Sat, 05 May 2018 10:25:46 GMT  
		Size: 7.9 MB (7867437 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2793192206e4ab032f5152356b71ea402af9d6cfd3812ad4e29857c76a039af6`  
		Last Modified: Sat, 05 May 2018 10:25:45 GMT  
		Size: 9.2 MB (9190303 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04e033c04a8296917467f1a5f58f33424a0c62e7f1ad7bc521d1a04a30491463`  
		Last Modified: Sat, 05 May 2018 10:26:49 GMT  
		Size: 50.8 MB (50809602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8751d53eb40e199ecd3910be45e09c6c039df9cf93ff8d670dbeea5b482f73af`  
		Last Modified: Sat, 05 May 2018 12:42:04 GMT  
		Size: 881.3 KB (881341 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1938d575c214b836cf8b48efd7a34cc415cc6910744792cbf930f8a0db1a557d`  
		Last Modified: Sat, 05 May 2018 12:42:04 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e580a9e033f42bffcbaafd5b37a8f37b62c1a71c6c659abf776f2fe88cd7177`  
		Last Modified: Sat, 05 May 2018 12:56:58 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4d21011b6a541fea820173903bf6140f9ad59f833ef7aff2fa3ea741ca7bb04`  
		Last Modified: Tue, 15 May 2018 10:56:16 GMT  
		Size: 239.2 MB (239190791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1eba573ed2805ef7a6a40bd7b42faf1471fc8bc365a43c29df7c15f51e7631d`  
		Last Modified: Tue, 15 May 2018 14:18:44 GMT  
		Size: 228.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79aba2f570658f8e8cf5ebdc0e6e24c497f6a535bfb88667b51e1f3fd51a6648`  
		Last Modified: Tue, 15 May 2018 14:18:46 GMT  
		Size: 8.9 MB (8946003 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c47ff1fdefc4f9a3f672f9cc9b9e0efffe91d8b330a9f3babdb3eb171719e1f1`  
		Last Modified: Tue, 15 May 2018 14:18:44 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eed4abb3cf35549e70f21ef8343b79de3cd41fdf451500b2a1359eaadb1219bf`  
		Last Modified: Tue, 15 May 2018 14:18:43 GMT  
		Size: 363.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; 386

```console
$ docker pull maven@sha256:5efd3d74989ccf7de18eab025732029df8cb2dd9b4d9d1b09a0e150d0c85f924
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **401.6 MB (401604410 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b42bf7e6afb2256182d6af1baf109290e17d4c80b8e74ed1a70a147f2671b820`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 10:40:49 GMT
ADD file:cb21908d8f286f1381ea180209120314676afa1ce4d5d480e0310fe70a4c96d4 in / 
# Sat, 28 Apr 2018 10:40:49 GMT
CMD ["bash"]
# Sat, 05 May 2018 11:02:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 11:02:38 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 11:03:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:09:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:09:16 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:09:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:18:17 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:18:17 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 13:18:17 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 13:18:18 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 11:34:02 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 11:34:03 GMT
CMD ["jshell"]
# Tue, 15 May 2018 14:02:01 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 14:02:01 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 14:02:01 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 14:02:01 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 14:02:03 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 14:02:18 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 14:02:18 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 14:02:18 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 14:02:18 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 14:02:19 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 14:02:19 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 14:02:19 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:33fb16074d5de3f73c0e2941c01c03e5dc69cfb8f568b7fbc3e29926b575fef0`  
		Last Modified: Sat, 28 Apr 2018 10:47:25 GMT  
		Size: 49.1 MB (49090181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10c0106e7eaef0802d668a2b79bf9f1db764acfe5d6181a1f4d15dc548ad4a5d`  
		Last Modified: Sat, 05 May 2018 11:38:03 GMT  
		Size: 8.6 MB (8616091 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cdc872687358d61e714f879d08e972342c93b7d91f31c13f6b15916a9a4130cc`  
		Last Modified: Sat, 05 May 2018 11:38:03 GMT  
		Size: 9.7 MB (9738582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ac6d25d685d309dcc4052024c336526538390a1d9f3cf421b391e061e7332e90`  
		Last Modified: Sat, 05 May 2018 11:38:36 GMT  
		Size: 54.6 MB (54635475 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bf5d1e17b3b447248678dc258de267967eafbb75ad1860920cc4dc55b4e96a4`  
		Last Modified: Sat, 05 May 2018 13:30:46 GMT  
		Size: 903.7 KB (903694 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6265ee7450b8dc95a193042c039123180e5dcbd62090b4db7e2c7d805c3bbe4a`  
		Last Modified: Sat, 05 May 2018 13:30:46 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94e0f158b7fc710df091e2a8225873fd271825e86b7f16e0639119c169d8c30e`  
		Last Modified: Sat, 05 May 2018 13:40:22 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8206fb01db7f14750d4d136229484da67e26b22e15b904aaeed03de6ba72a336`  
		Last Modified: Tue, 15 May 2018 12:10:15 GMT  
		Size: 269.7 MB (269672712 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b840033cb70ec983076c39f88c422a1a801bbc786a4f0475f67952c0caa804f`  
		Last Modified: Tue, 15 May 2018 14:07:25 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af600f4ea443027e2e77cb9e0b3755bcda37fcffff6aa63af4ecf237189dfb1c`  
		Last Modified: Tue, 15 May 2018 14:07:31 GMT  
		Size: 8.9 MB (8945980 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dad03f43fd78daadb3ab77955c2010495a1f307ee99026d15ea4a11895042111`  
		Last Modified: Tue, 15 May 2018 14:07:25 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0c1c24847c00d7624c8a9bc949721460d93520b1ce0e3a284e92712743e7627`  
		Last Modified: Tue, 15 May 2018 14:07:25 GMT  
		Size: 362.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; ppc64le

```console
$ docker pull maven@sha256:7f73cdb4a80db4c94364ddea2a9117057ec69ac537e1365ce8c097d2b616ce42
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **379.7 MB (379661635 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d2db659163784f11022004e0455e5b3af1f8943044e53f7c37a19001f012e974`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 08:19:13 GMT
ADD file:320268259acdc4e2a105be735ea4ee0cb1398bb05ce729d46f4a54fa3c3c84e3 in / 
# Sat, 28 Apr 2018 08:19:15 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:16:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:16:49 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:21:27 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:48:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:48:57 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:49:00 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 14:23:40 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 14:23:41 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 14:23:42 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 14:23:43 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 08:50:20 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 08:50:22 GMT
CMD ["jshell"]
# Tue, 15 May 2018 10:51:24 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 10:51:33 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 10:51:42 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 10:51:45 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 10:52:05 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 10:52:17 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 10:52:19 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 10:52:24 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 10:52:27 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 10:52:31 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 10:52:33 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 10:52:35 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:354f055c313d4d07201e01fd4de9af4aca89e3df17572870e56c5b8945e48443`  
		Last Modified: Sat, 28 Apr 2018 08:27:42 GMT  
		Size: 49.8 MB (49754912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f77e4d2b61d28a226758713bae6bf933182cc9aa5eea6834696ef5865b36a2d2`  
		Last Modified: Sat, 05 May 2018 10:56:29 GMT  
		Size: 8.3 MB (8252158 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee38bf91c1472a5fafe06a2f5ba7ea5bf20d82e4c77308ccb3bb26c3068d95c5`  
		Last Modified: Sat, 05 May 2018 10:56:40 GMT  
		Size: 9.7 MB (9711623 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68a774996e1e41e16b05c537334faa52f62da8dc20585016b4be6783eecbfa27`  
		Last Modified: Sat, 05 May 2018 10:57:37 GMT  
		Size: 55.8 MB (55781554 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e73d6946d81354ab550331ff9f689d3cf70de0f32d141b34ea750d442597d8e1`  
		Last Modified: Sat, 05 May 2018 14:53:16 GMT  
		Size: 890.5 KB (890501 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fec613ebf835d7057b5111fe9afdbbb25415edc834a99e8b38022dd88922555`  
		Last Modified: Sat, 05 May 2018 14:53:15 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48ab1943e9a0ba77f36bb614452ff5adeb20afc8d1205c29843c1108aa428969`  
		Last Modified: Sat, 05 May 2018 15:06:41 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08e336e74e3f56d8609c8666316334e387e209116837c309f24d65d7229e6c9f`  
		Last Modified: Tue, 15 May 2018 09:37:24 GMT  
		Size: 246.3 MB (246323049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e42149fc202d850b70b18ef21afdc4d119e35117155b6debaafd1c32beefa2bf`  
		Last Modified: Tue, 15 May 2018 10:58:13 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cd2e2123c5f492100deef6208a12d8c9ec6d899ce54d096bd63190722623007a`  
		Last Modified: Tue, 15 May 2018 10:58:14 GMT  
		Size: 8.9 MB (8946139 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80e9d655e2db756bb431b34d052779d11dca62e1c6b4631489973b37f7916a57`  
		Last Modified: Tue, 15 May 2018 10:58:13 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:784f8e80d6323166d828bc1500081c44b7d744a7e10bccc7a3e8bf1f79ae3f05`  
		Last Modified: Tue, 15 May 2018 10:58:13 GMT  
		Size: 361.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `maven:3-jdk-9` - linux; s390x

```console
$ docker pull maven@sha256:ac411bd432e13c6a5789a843ae5d9460383db318a99deb49349e6351c5d92cf6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **348.2 MB (348204689 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:21999b5f2f0f953fc348cb50eb2666b890c92726e99745252bc4a2c836ead66e`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Sat, 28 Apr 2018 11:43:52 GMT
ADD file:2ebc77cf35fadaf6ffd85f0d203bf60b217e15aa3c15737aac14f71008535107 in / 
# Sat, 28 Apr 2018 11:43:52 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:33:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:34:01 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:34:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:05:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:05:56 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:05:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:11:03 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:11:03 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 13:11:04 GMT
ENV JAVA_VERSION=9.0.4+12
# Sat, 05 May 2018 13:11:04 GMT
ENV JAVA_DEBIAN_VERSION=9.0.4+12-4
# Tue, 15 May 2018 12:05:11 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-9-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 12:05:12 GMT
CMD ["jshell"]
# Tue, 15 May 2018 13:42:01 GMT
ARG MAVEN_VERSION=3.5.3
# Tue, 15 May 2018 13:42:02 GMT
ARG USER_HOME_DIR=/root
# Tue, 15 May 2018 13:42:02 GMT
ARG SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408
# Tue, 15 May 2018 13:42:03 GMT
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries
# Tue, 15 May 2018 13:42:04 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN ln -s /etc/java-9-openjdk /usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)/conf
# Tue, 15 May 2018 13:42:06 GMT
# ARGS: BASE_URL=https://apache.osuosl.org/maven/maven-3/3.5.3/binaries MAVEN_VERSION=3.5.3 SHA=b52956373fab1dd4277926507ab189fb797b3bc51a2a267a193c931fffad8408 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz   && echo "${SHA}  /tmp/apache-maven.tar.gz" | sha256sum -c -   && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1   && rm -f /tmp/apache-maven.tar.gz   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Tue, 15 May 2018 13:42:07 GMT
ENV MAVEN_HOME=/usr/share/maven
# Tue, 15 May 2018 13:42:07 GMT
ENV MAVEN_CONFIG=/root/.m2
# Tue, 15 May 2018 13:42:08 GMT
COPY file:fb726a12bbbf8ff54c8d9fceef4fa3018c11a435bfa04ee5f73156c544907861 in /usr/local/bin/mvn-entrypoint.sh 
# Tue, 15 May 2018 13:42:08 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Tue, 15 May 2018 13:42:09 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Tue, 15 May 2018 13:42:09 GMT
CMD ["mvn"]
```

-	Layers:
	-	`sha256:893cc85742608c84d1d6314416656d650a83dae134d0d1e22a839b39a03cbf3e`  
		Last Modified: Sat, 28 Apr 2018 11:49:42 GMT  
		Size: 47.4 MB (47350246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6465ae4acbbbfe22cde44168d0262178f375ac945898fbe73420bec2cc2ccbe0`  
		Last Modified: Sat, 05 May 2018 12:46:57 GMT  
		Size: 8.1 MB (8124442 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e47a8c562fcb2d700f3403a2f6b5d1c62f5961afce859416ff6a03520adf95a5`  
		Last Modified: Sat, 05 May 2018 12:46:57 GMT  
		Size: 9.4 MB (9414344 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:481f2ac0d700bc88441da57f26f2253a495063e8fcf46706e8462f4b16292b84`  
		Last Modified: Sat, 05 May 2018 12:47:23 GMT  
		Size: 52.3 MB (52257848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:755b496e7ed5d1a4f90f69efc1653169b1cf721f0fd65832ce1c7c1838017e19`  
		Last Modified: Sat, 05 May 2018 13:21:22 GMT  
		Size: 906.4 KB (906357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:340cd0adda5f0114369ab22dee2566c26d88ac2264cba92eb697d1858f314b95`  
		Last Modified: Sat, 05 May 2018 13:21:22 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fc5b570e41674b5cf67ba58622e59fc8bdfc409df50cb7f3643762ac67cf7ef`  
		Last Modified: Sat, 05 May 2018 13:25:00 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f21a62d1f1750eaf1c0f8fbe4d1a24564b53cf27f53785ea0238392820d720a`  
		Last Modified: Tue, 15 May 2018 12:37:17 GMT  
		Size: 221.2 MB (221203792 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d04b19415ac0e5d6f1e59fae38230057e0932ce71ba5338c7ca10a51b43b63d`  
		Last Modified: Tue, 15 May 2018 13:50:57 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c72ac458e65f9870c7898e54063e2019e9ea1411ea05be1f81e42ff6a9f5dada`  
		Last Modified: Tue, 15 May 2018 13:50:58 GMT  
		Size: 8.9 MB (8945968 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66f484a996fb8127caf915bc6e0568f4d3cb8d951bacb1b328ad3295f85d3643`  
		Last Modified: Tue, 15 May 2018 13:50:57 GMT  
		Size: 743.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b32a57bda51179be4e86262419560c61d3de9b1bd7b0de947d4fb8cdafea05a8`  
		Last Modified: Tue, 15 May 2018 13:50:57 GMT  
		Size: 358.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
