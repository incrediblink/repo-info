<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `mariadb`

-	[`mariadb:10`](#mariadb10)
-	[`mariadb:10.0`](#mariadb100)
-	[`mariadb:10.0.35`](#mariadb10035)
-	[`mariadb:10.1`](#mariadb101)
-	[`mariadb:10.1.33`](#mariadb10133)
-	[`mariadb:10.2`](#mariadb102)
-	[`mariadb:10.2.15`](#mariadb10215)
-	[`mariadb:10.3`](#mariadb103)
-	[`mariadb:10.3.6`](#mariadb1036)
-	[`mariadb:5`](#mariadb5)
-	[`mariadb:5.5`](#mariadb55)
-	[`mariadb:5.5.60`](#mariadb5560)
-	[`mariadb:latest`](#mariadblatest)

## `mariadb:10`

```console
$ docker pull mariadb@sha256:9c2d88ea65f3f60fdf977a1e1ecbe8dbe1cb1d4591137cb583a2f72e261bc702
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10` - linux; amd64

```console
$ docker pull mariadb@sha256:f6c011e32a50b1f61cf2b55beab62efc9ebaa31df1ecc2ec296bc1d89bfa00f5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.9 MB (136866048 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d0eec08837f9dae2daded5cad16bbb28fc5379fce2c8a7b16211236d496ace3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:51:28 GMT
ENV MARIADB_MAJOR=10.2
# Mon, 21 May 2018 21:23:40 GMT
ENV MARIADB_VERSION=10.2.15+maria~jessie
# Mon, 21 May 2018 21:23:41 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 21 May 2018 21:24:32 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 21 May 2018 21:24:33 GMT
VOLUME [/var/lib/mysql]
# Mon, 21 May 2018 21:24:33 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Mon, 21 May 2018 21:24:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Mon, 21 May 2018 21:24:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 21 May 2018 21:24:34 GMT
EXPOSE 3306/tcp
# Mon, 21 May 2018 21:24:34 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce9fcaa8405e831d89809cec7f1442648b1804d121d69076c54133145f49817`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59ec24cbcca586f3019d7d671b2eab7ee20bc5ca18422fb78b15be337f435896`  
		Last Modified: Mon, 21 May 2018 21:25:01 GMT  
		Size: 76.6 MB (76578170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da46fbd7f15f4c8c619f895a3bd3a8c570a8a2f9e8810be1b2b09da06b170d0c`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 2.5 KB (2547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd0d33730a5c3075778d67f0bbac6c7842845b2030e398b07cd89394058b49f7`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.0`

```console
$ docker pull mariadb@sha256:39000fdf9a9ea5e080c8cff5bbb32e6f835ee4588872e9f394b884b3dc298add
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.0` - linux; amd64

```console
$ docker pull mariadb@sha256:15a184ede109f2fc55df43016871b6f9dea0689cb3f7007d56119101310272ab
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **121.0 MB (120975588 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e62a348569b20425b478057315aae304fbd0806f8bbbfc8a283b383415348f49`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:18:43 GMT
ENV MARIADB_MAJOR=10.0
# Fri, 04 May 2018 23:39:18 GMT
ENV MARIADB_VERSION=10.0.35+maria-1~jessie
# Fri, 04 May 2018 23:39:19 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Fri, 04 May 2018 23:40:15 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Fri, 04 May 2018 23:40:16 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:37 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:38 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:38 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:38 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:39 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:169b14e62f0d9909dca5d7f94432eb6054f22a55c8cc02261e13f38cace47845`  
		Last Modified: Fri, 04 May 2018 23:40:39 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a5ede234be9e7d79e8fef34542f3d93a10c477df5753be22e9fe50d976e0857`  
		Last Modified: Fri, 04 May 2018 23:40:47 GMT  
		Size: 60.7 MB (60687718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55d78c89854e330b58ca90b3048ccfc34c0e53c20bc701897a19c3ca782ef324`  
		Last Modified: Wed, 09 May 2018 17:31:02 GMT  
		Size: 2.5 KB (2539 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4f6d76611f9722fe87a6c7ffe927e382d3f0703c240eb0a61373eb9ab170b7d`  
		Last Modified: Wed, 09 May 2018 17:31:02 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.0.35`

```console
$ docker pull mariadb@sha256:39000fdf9a9ea5e080c8cff5bbb32e6f835ee4588872e9f394b884b3dc298add
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.0.35` - linux; amd64

```console
$ docker pull mariadb@sha256:15a184ede109f2fc55df43016871b6f9dea0689cb3f7007d56119101310272ab
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **121.0 MB (120975588 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e62a348569b20425b478057315aae304fbd0806f8bbbfc8a283b383415348f49`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:18:43 GMT
ENV MARIADB_MAJOR=10.0
# Fri, 04 May 2018 23:39:18 GMT
ENV MARIADB_VERSION=10.0.35+maria-1~jessie
# Fri, 04 May 2018 23:39:19 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Fri, 04 May 2018 23:40:15 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Fri, 04 May 2018 23:40:16 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:37 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:38 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:38 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:38 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:39 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:169b14e62f0d9909dca5d7f94432eb6054f22a55c8cc02261e13f38cace47845`  
		Last Modified: Fri, 04 May 2018 23:40:39 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a5ede234be9e7d79e8fef34542f3d93a10c477df5753be22e9fe50d976e0857`  
		Last Modified: Fri, 04 May 2018 23:40:47 GMT  
		Size: 60.7 MB (60687718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55d78c89854e330b58ca90b3048ccfc34c0e53c20bc701897a19c3ca782ef324`  
		Last Modified: Wed, 09 May 2018 17:31:02 GMT  
		Size: 2.5 KB (2539 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4f6d76611f9722fe87a6c7ffe927e382d3f0703c240eb0a61373eb9ab170b7d`  
		Last Modified: Wed, 09 May 2018 17:31:02 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.1`

```console
$ docker pull mariadb@sha256:bb13e7be680e87512495d904ab88f169b5db649e80de4b3de0bcea8f2daa3dec
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.1` - linux; amd64

```console
$ docker pull mariadb@sha256:a1edc5287c2bb389501b8863cf59939945ca00b30f794d9f2a63ee0215a38c63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.6 MB (136644238 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:124d6faa1f6064511c2d4c883ce1248414534cbedc3c8469f0f197023873a49f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:02:33 GMT
ENV MARIADB_MAJOR=10.1
# Thu, 10 May 2018 20:33:30 GMT
ENV MARIADB_VERSION=10.1.33+maria-1~jessie
# Thu, 10 May 2018 20:33:31 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Thu, 10 May 2018 20:34:33 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Thu, 10 May 2018 20:34:33 GMT
VOLUME [/var/lib/mysql]
# Thu, 10 May 2018 20:34:34 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Thu, 10 May 2018 20:34:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 10 May 2018 20:34:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 10 May 2018 20:34:35 GMT
EXPOSE 3306/tcp
# Thu, 10 May 2018 20:34:35 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a73cbb5b570a9c19e9889b6ea8d740c2673320cd342c075fa11bf421b0564a96`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 324.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e52c529c3071267f13b406d595343dd2c9ad3b58856a9d6dcaadddad10e73c76`  
		Last Modified: Thu, 10 May 2018 20:35:42 GMT  
		Size: 76.4 MB (76356363 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebce962e375aa6ea5541c8a862efa0344a01065ff29fb76d9d7dc841304b4231`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 2.5 KB (2545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aaa1d6ac335261b941fbb2d0f12cba6a75a173c584604e363798208577333f50`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.1.33`

```console
$ docker pull mariadb@sha256:bb13e7be680e87512495d904ab88f169b5db649e80de4b3de0bcea8f2daa3dec
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.1.33` - linux; amd64

```console
$ docker pull mariadb@sha256:a1edc5287c2bb389501b8863cf59939945ca00b30f794d9f2a63ee0215a38c63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.6 MB (136644238 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:124d6faa1f6064511c2d4c883ce1248414534cbedc3c8469f0f197023873a49f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:02:33 GMT
ENV MARIADB_MAJOR=10.1
# Thu, 10 May 2018 20:33:30 GMT
ENV MARIADB_VERSION=10.1.33+maria-1~jessie
# Thu, 10 May 2018 20:33:31 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Thu, 10 May 2018 20:34:33 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Thu, 10 May 2018 20:34:33 GMT
VOLUME [/var/lib/mysql]
# Thu, 10 May 2018 20:34:34 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Thu, 10 May 2018 20:34:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Thu, 10 May 2018 20:34:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 10 May 2018 20:34:35 GMT
EXPOSE 3306/tcp
# Thu, 10 May 2018 20:34:35 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a73cbb5b570a9c19e9889b6ea8d740c2673320cd342c075fa11bf421b0564a96`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 324.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e52c529c3071267f13b406d595343dd2c9ad3b58856a9d6dcaadddad10e73c76`  
		Last Modified: Thu, 10 May 2018 20:35:42 GMT  
		Size: 76.4 MB (76356363 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebce962e375aa6ea5541c8a862efa0344a01065ff29fb76d9d7dc841304b4231`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 2.5 KB (2545 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aaa1d6ac335261b941fbb2d0f12cba6a75a173c584604e363798208577333f50`  
		Last Modified: Thu, 10 May 2018 20:35:31 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.2`

```console
$ docker pull mariadb@sha256:9c2d88ea65f3f60fdf977a1e1ecbe8dbe1cb1d4591137cb583a2f72e261bc702
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.2` - linux; amd64

```console
$ docker pull mariadb@sha256:f6c011e32a50b1f61cf2b55beab62efc9ebaa31df1ecc2ec296bc1d89bfa00f5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.9 MB (136866048 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d0eec08837f9dae2daded5cad16bbb28fc5379fce2c8a7b16211236d496ace3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:51:28 GMT
ENV MARIADB_MAJOR=10.2
# Mon, 21 May 2018 21:23:40 GMT
ENV MARIADB_VERSION=10.2.15+maria~jessie
# Mon, 21 May 2018 21:23:41 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 21 May 2018 21:24:32 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 21 May 2018 21:24:33 GMT
VOLUME [/var/lib/mysql]
# Mon, 21 May 2018 21:24:33 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Mon, 21 May 2018 21:24:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Mon, 21 May 2018 21:24:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 21 May 2018 21:24:34 GMT
EXPOSE 3306/tcp
# Mon, 21 May 2018 21:24:34 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce9fcaa8405e831d89809cec7f1442648b1804d121d69076c54133145f49817`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59ec24cbcca586f3019d7d671b2eab7ee20bc5ca18422fb78b15be337f435896`  
		Last Modified: Mon, 21 May 2018 21:25:01 GMT  
		Size: 76.6 MB (76578170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da46fbd7f15f4c8c619f895a3bd3a8c570a8a2f9e8810be1b2b09da06b170d0c`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 2.5 KB (2547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd0d33730a5c3075778d67f0bbac6c7842845b2030e398b07cd89394058b49f7`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.2.15`

```console
$ docker pull mariadb@sha256:9c2d88ea65f3f60fdf977a1e1ecbe8dbe1cb1d4591137cb583a2f72e261bc702
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.2.15` - linux; amd64

```console
$ docker pull mariadb@sha256:f6c011e32a50b1f61cf2b55beab62efc9ebaa31df1ecc2ec296bc1d89bfa00f5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.9 MB (136866048 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d0eec08837f9dae2daded5cad16bbb28fc5379fce2c8a7b16211236d496ace3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:51:28 GMT
ENV MARIADB_MAJOR=10.2
# Mon, 21 May 2018 21:23:40 GMT
ENV MARIADB_VERSION=10.2.15+maria~jessie
# Mon, 21 May 2018 21:23:41 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 21 May 2018 21:24:32 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 21 May 2018 21:24:33 GMT
VOLUME [/var/lib/mysql]
# Mon, 21 May 2018 21:24:33 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Mon, 21 May 2018 21:24:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Mon, 21 May 2018 21:24:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 21 May 2018 21:24:34 GMT
EXPOSE 3306/tcp
# Mon, 21 May 2018 21:24:34 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce9fcaa8405e831d89809cec7f1442648b1804d121d69076c54133145f49817`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59ec24cbcca586f3019d7d671b2eab7ee20bc5ca18422fb78b15be337f435896`  
		Last Modified: Mon, 21 May 2018 21:25:01 GMT  
		Size: 76.6 MB (76578170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da46fbd7f15f4c8c619f895a3bd3a8c570a8a2f9e8810be1b2b09da06b170d0c`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 2.5 KB (2547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd0d33730a5c3075778d67f0bbac6c7842845b2030e398b07cd89394058b49f7`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.3`

```console
$ docker pull mariadb@sha256:99b523beedb55d3aedc6b0fa6784176563a9b17c029a5419dc91df4cdbef7804
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.3` - linux; amd64

```console
$ docker pull mariadb@sha256:41f5147d786e554a889bfe655faaf4b823a4f3e060c4220b3759a68eced4cdc3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **137.3 MB (137345212 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:802f90d5da0d84609ae5fce593f5e0e14264042fabbd166711c5556e23cbe870`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:38:22 GMT
ENV MARIADB_MAJOR=10.3
# Mon, 30 Apr 2018 15:38:22 GMT
ENV MARIADB_VERSION=1:10.3.6+maria~jessie
# Mon, 30 Apr 2018 15:38:23 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 30 Apr 2018 15:39:13 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 30 Apr 2018 15:39:13 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:18 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:19 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:19 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:19 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:19 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c37437a05bfb2e126bf48b095df41eb75fc826c4f5c8d7616dde6b9269fbcfec`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 323.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a67d20fcd23a3d65c4b5be9d71ef5f91c5777ac99e2ea8ae26423c8a4bf73157`  
		Last Modified: Mon, 30 Apr 2018 16:33:02 GMT  
		Size: 77.1 MB (77057342 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3eea0e76ce16e93a061a1c3f7fbbdb2ad84ab6c855cec34ce6c4abd02241ec0`  
		Last Modified: Wed, 09 May 2018 17:29:56 GMT  
		Size: 2.5 KB (2541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42e0e587cc3887a7a34125162f7a8eb52bda51d9e1c489e82c9fc43830a76d93`  
		Last Modified: Wed, 09 May 2018 17:29:57 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:10.3.6`

```console
$ docker pull mariadb@sha256:99b523beedb55d3aedc6b0fa6784176563a9b17c029a5419dc91df4cdbef7804
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:10.3.6` - linux; amd64

```console
$ docker pull mariadb@sha256:41f5147d786e554a889bfe655faaf4b823a4f3e060c4220b3759a68eced4cdc3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **137.3 MB (137345212 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:802f90d5da0d84609ae5fce593f5e0e14264042fabbd166711c5556e23cbe870`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:38:22 GMT
ENV MARIADB_MAJOR=10.3
# Mon, 30 Apr 2018 15:38:22 GMT
ENV MARIADB_VERSION=1:10.3.6+maria~jessie
# Mon, 30 Apr 2018 15:38:23 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 30 Apr 2018 15:39:13 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 30 Apr 2018 15:39:13 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:18 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:19 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:19 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:19 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:19 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c37437a05bfb2e126bf48b095df41eb75fc826c4f5c8d7616dde6b9269fbcfec`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 323.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a67d20fcd23a3d65c4b5be9d71ef5f91c5777ac99e2ea8ae26423c8a4bf73157`  
		Last Modified: Mon, 30 Apr 2018 16:33:02 GMT  
		Size: 77.1 MB (77057342 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3eea0e76ce16e93a061a1c3f7fbbdb2ad84ab6c855cec34ce6c4abd02241ec0`  
		Last Modified: Wed, 09 May 2018 17:29:56 GMT  
		Size: 2.5 KB (2541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42e0e587cc3887a7a34125162f7a8eb52bda51d9e1c489e82c9fc43830a76d93`  
		Last Modified: Wed, 09 May 2018 17:29:57 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:5`

```console
$ docker pull mariadb@sha256:43df44e7def558a94b8ca4ddf62941ccc7eed57bbac5041af62f3b9bf05e5643
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:5` - linux; amd64

```console
$ docker pull mariadb@sha256:dbd2a5699da0e956a542bb5f4fe91e1196398c99fd43f375339bec8befa3b358
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **98.2 MB (98173814 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:19f7d427152fe4816381eb43ad043e5500efbad53cc488cabdda8813eeb262a4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 07:36:32 GMT
ADD file:344df33141429b2c1c775197ce8c8d620acc38617d2a66ce04d81fb4dc6a7a0e in / 
# Sat, 28 Apr 2018 07:36:33 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 16:20:04 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 16:20:04 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 16:20:23 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 16:20:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 16:20:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 16:20:34 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 16:20:36 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 16:20:37 GMT
RUN echo "deb https://repo.percona.com/apt wheezy main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_MAJOR=5.5
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_VERSION=5.5.60+maria-1~wheezy
# Mon, 30 Apr 2018 16:20:38 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian wheezy main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 30 Apr 2018 16:20:53 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 30 Apr 2018 16:20:53 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:44 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:45 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:45 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:45 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:fbb9e26f3a43e50b0cb6e1d3ece41f31ed4547f268081650b06c636dec569819`  
		Last Modified: Sat, 28 Apr 2018 10:02:44 GMT  
		Size: 39.3 MB (39339142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43129a0df16487055366f24c242704b4abb7b44eed7a963aad9f75dd3dee17c9`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 1.7 KB (1739 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3792da1faa8ee858ad158355be006619c8690b15116df4efee64e58db2ffb2e`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 959.9 KB (959858 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fcac96c7b78cd1ae254abfbf2eb932ca08217a3c202ab11bba8158c06678eb4`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f9684182f2449d340dcb035c205b7bbd5b45cfb04fa4a6bad939da6e9a83b7f`  
		Last Modified: Mon, 30 Apr 2018 17:25:50 GMT  
		Size: 4.7 MB (4673767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e373cc8171eb25978fcf0b37b1ed77035ced4d76a0281b69c59ad7ea4d75d0c2`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 20.9 KB (20863 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6588ac1c2283c2749a9636b6b999d61f1acab62bd1cbcb73c7ea80351c9ab752`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 316.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:699977231f020c7b8f272f7eef772278a1170abc9a287a30adc2868d58c5a09d`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 326.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:041e561c88a13d62a59a579e0c2f140141cde8ef64dd33f3c30455d237ddd030`  
		Last Modified: Mon, 30 Apr 2018 17:25:59 GMT  
		Size: 53.2 MB (53175024 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:791295a9f502e5967da83d85475a678ef3108aa61d7b5dd1086115bd5e8dc179`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 2.5 KB (2543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c55ff9f5bdba13cab893fa284d2dd71d3e27ee44f3e332cbbe0b64d66bc8b83`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:5.5`

```console
$ docker pull mariadb@sha256:43df44e7def558a94b8ca4ddf62941ccc7eed57bbac5041af62f3b9bf05e5643
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:5.5` - linux; amd64

```console
$ docker pull mariadb@sha256:dbd2a5699da0e956a542bb5f4fe91e1196398c99fd43f375339bec8befa3b358
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **98.2 MB (98173814 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:19f7d427152fe4816381eb43ad043e5500efbad53cc488cabdda8813eeb262a4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 07:36:32 GMT
ADD file:344df33141429b2c1c775197ce8c8d620acc38617d2a66ce04d81fb4dc6a7a0e in / 
# Sat, 28 Apr 2018 07:36:33 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 16:20:04 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 16:20:04 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 16:20:23 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 16:20:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 16:20:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 16:20:34 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 16:20:36 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 16:20:37 GMT
RUN echo "deb https://repo.percona.com/apt wheezy main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_MAJOR=5.5
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_VERSION=5.5.60+maria-1~wheezy
# Mon, 30 Apr 2018 16:20:38 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian wheezy main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 30 Apr 2018 16:20:53 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 30 Apr 2018 16:20:53 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:44 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:45 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:45 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:45 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:fbb9e26f3a43e50b0cb6e1d3ece41f31ed4547f268081650b06c636dec569819`  
		Last Modified: Sat, 28 Apr 2018 10:02:44 GMT  
		Size: 39.3 MB (39339142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43129a0df16487055366f24c242704b4abb7b44eed7a963aad9f75dd3dee17c9`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 1.7 KB (1739 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3792da1faa8ee858ad158355be006619c8690b15116df4efee64e58db2ffb2e`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 959.9 KB (959858 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fcac96c7b78cd1ae254abfbf2eb932ca08217a3c202ab11bba8158c06678eb4`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f9684182f2449d340dcb035c205b7bbd5b45cfb04fa4a6bad939da6e9a83b7f`  
		Last Modified: Mon, 30 Apr 2018 17:25:50 GMT  
		Size: 4.7 MB (4673767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e373cc8171eb25978fcf0b37b1ed77035ced4d76a0281b69c59ad7ea4d75d0c2`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 20.9 KB (20863 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6588ac1c2283c2749a9636b6b999d61f1acab62bd1cbcb73c7ea80351c9ab752`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 316.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:699977231f020c7b8f272f7eef772278a1170abc9a287a30adc2868d58c5a09d`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 326.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:041e561c88a13d62a59a579e0c2f140141cde8ef64dd33f3c30455d237ddd030`  
		Last Modified: Mon, 30 Apr 2018 17:25:59 GMT  
		Size: 53.2 MB (53175024 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:791295a9f502e5967da83d85475a678ef3108aa61d7b5dd1086115bd5e8dc179`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 2.5 KB (2543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c55ff9f5bdba13cab893fa284d2dd71d3e27ee44f3e332cbbe0b64d66bc8b83`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:5.5.60`

```console
$ docker pull mariadb@sha256:43df44e7def558a94b8ca4ddf62941ccc7eed57bbac5041af62f3b9bf05e5643
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:5.5.60` - linux; amd64

```console
$ docker pull mariadb@sha256:dbd2a5699da0e956a542bb5f4fe91e1196398c99fd43f375339bec8befa3b358
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **98.2 MB (98173814 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:19f7d427152fe4816381eb43ad043e5500efbad53cc488cabdda8813eeb262a4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 07:36:32 GMT
ADD file:344df33141429b2c1c775197ce8c8d620acc38617d2a66ce04d81fb4dc6a7a0e in / 
# Sat, 28 Apr 2018 07:36:33 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 16:20:04 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 16:20:04 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 16:20:23 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 16:20:24 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 16:20:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 16:20:34 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 16:20:36 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 16:20:37 GMT
RUN echo "deb https://repo.percona.com/apt wheezy main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_MAJOR=5.5
# Mon, 30 Apr 2018 16:20:37 GMT
ENV MARIADB_VERSION=5.5.60+maria-1~wheezy
# Mon, 30 Apr 2018 16:20:38 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian wheezy main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 30 Apr 2018 16:20:53 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 30 Apr 2018 16:20:53 GMT
VOLUME [/var/lib/mysql]
# Wed, 09 May 2018 17:29:44 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Wed, 09 May 2018 17:29:45 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 09 May 2018 17:29:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 09 May 2018 17:29:45 GMT
EXPOSE 3306/tcp
# Wed, 09 May 2018 17:29:45 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:fbb9e26f3a43e50b0cb6e1d3ece41f31ed4547f268081650b06c636dec569819`  
		Last Modified: Sat, 28 Apr 2018 10:02:44 GMT  
		Size: 39.3 MB (39339142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43129a0df16487055366f24c242704b4abb7b44eed7a963aad9f75dd3dee17c9`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 1.7 KB (1739 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3792da1faa8ee858ad158355be006619c8690b15116df4efee64e58db2ffb2e`  
		Last Modified: Mon, 30 Apr 2018 17:25:51 GMT  
		Size: 959.9 KB (959858 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fcac96c7b78cd1ae254abfbf2eb932ca08217a3c202ab11bba8158c06678eb4`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f9684182f2449d340dcb035c205b7bbd5b45cfb04fa4a6bad939da6e9a83b7f`  
		Last Modified: Mon, 30 Apr 2018 17:25:50 GMT  
		Size: 4.7 MB (4673767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e373cc8171eb25978fcf0b37b1ed77035ced4d76a0281b69c59ad7ea4d75d0c2`  
		Last Modified: Mon, 30 Apr 2018 17:25:49 GMT  
		Size: 20.9 KB (20863 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6588ac1c2283c2749a9636b6b999d61f1acab62bd1cbcb73c7ea80351c9ab752`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 316.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:699977231f020c7b8f272f7eef772278a1170abc9a287a30adc2868d58c5a09d`  
		Last Modified: Mon, 30 Apr 2018 17:25:46 GMT  
		Size: 326.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:041e561c88a13d62a59a579e0c2f140141cde8ef64dd33f3c30455d237ddd030`  
		Last Modified: Mon, 30 Apr 2018 17:25:59 GMT  
		Size: 53.2 MB (53175024 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:791295a9f502e5967da83d85475a678ef3108aa61d7b5dd1086115bd5e8dc179`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 2.5 KB (2543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c55ff9f5bdba13cab893fa284d2dd71d3e27ee44f3e332cbbe0b64d66bc8b83`  
		Last Modified: Wed, 09 May 2018 17:31:19 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `mariadb:latest`

```console
$ docker pull mariadb@sha256:9c2d88ea65f3f60fdf977a1e1ecbe8dbe1cb1d4591137cb583a2f72e261bc702
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mariadb:latest` - linux; amd64

```console
$ docker pull mariadb@sha256:f6c011e32a50b1f61cf2b55beab62efc9ebaa31df1ecc2ec296bc1d89bfa00f5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.9 MB (136866048 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d0eec08837f9dae2daded5cad16bbb28fc5379fce2c8a7b16211236d496ace3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Mon, 30 Apr 2018 15:37:27 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 30 Apr 2018 15:37:28 GMT
ENV GOSU_VERSION=1.10
# Mon, 30 Apr 2018 15:37:56 GMT
RUN set -ex; 		fetchDeps=' 		ca-certificates 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 		chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Mon, 30 Apr 2018 15:37:57 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 30 Apr 2018 15:38:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Mon, 30 Apr 2018 15:38:16 GMT
ENV GPG_KEYS=199369E5404BD5FC7D2FE43BCBCB082A1BB943DB 	430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Mon, 30 Apr 2018 15:38:21 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mariadb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 30 Apr 2018 15:38:22 GMT
RUN echo "deb https://repo.percona.com/apt jessie main" > /etc/apt/sources.list.d/percona.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=Percona Development Team'; 		echo 'Pin-Priority: 998'; 	} > /etc/apt/preferences.d/percona
# Mon, 30 Apr 2018 15:51:28 GMT
ENV MARIADB_MAJOR=10.2
# Mon, 21 May 2018 21:23:40 GMT
ENV MARIADB_VERSION=10.2.15+maria~jessie
# Mon, 21 May 2018 21:23:41 GMT
RUN echo "deb http://ftp.osuosl.org/pub/mariadb/repo/$MARIADB_MAJOR/debian jessie main" > /etc/apt/sources.list.d/mariadb.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release o=MariaDB'; 		echo 'Pin-Priority: 999'; 	} > /etc/apt/preferences.d/mariadb
# Mon, 21 May 2018 21:24:32 GMT
RUN { 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password password 'unused'; 		echo "mariadb-server-$MARIADB_MAJOR" mysql-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		"mariadb-server=$MARIADB_VERSION" 		percona-xtrabackup-24 		socat 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf /etc/mysql/conf.d/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Mon, 21 May 2018 21:24:33 GMT
VOLUME [/var/lib/mysql]
# Mon, 21 May 2018 21:24:33 GMT
COPY file:a568cdb8d6fe0ea550605f3c2bc75f2ac3946fa8bdc6bf5718404d55b70e0a92 in /usr/local/bin/ 
# Mon, 21 May 2018 21:24:34 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Mon, 21 May 2018 21:24:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 21 May 2018 21:24:34 GMT
EXPOSE 3306/tcp
# Mon, 21 May 2018 21:24:34 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6a779d83f57640f88ed719545d1ed334a18d3c33fc9f139892918a096a4d8e`  
		Last Modified: Mon, 30 Apr 2018 16:32:45 GMT  
		Size: 2.1 KB (2093 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c1d272f25d5af59f1fd4ef77ceda35839f86b003d508422e3c2df599aea4824`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 988.8 KB (988761 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:672dd5e0b768c3edb1bbaa087e9429f69a5868fff2d52fe6bdf9b9acfb22a468`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a7291b59963b500d05381c558ed9f10f7f6c371aad60f9677e999b1f1452a2`  
		Last Modified: Mon, 30 Apr 2018 16:32:44 GMT  
		Size: 5.0 MB (5010207 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:92edc8e8d33d5d8c415410920d87e13793e39eb14122ba089349f530d5be23e1`  
		Last Modified: Mon, 30 Apr 2018 16:32:43 GMT  
		Size: 20.8 KB (20829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f86a8206781789fc2d99b603104734bf3eae64b1e3e72e81fd17dc7695a13be4`  
		Last Modified: Mon, 30 Apr 2018 16:32:41 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce9fcaa8405e831d89809cec7f1442648b1804d121d69076c54133145f49817`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 325.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59ec24cbcca586f3019d7d671b2eab7ee20bc5ca18422fb78b15be337f435896`  
		Last Modified: Mon, 21 May 2018 21:25:01 GMT  
		Size: 76.6 MB (76578170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da46fbd7f15f4c8c619f895a3bd3a8c570a8a2f9e8810be1b2b09da06b170d0c`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 2.5 KB (2547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd0d33730a5c3075778d67f0bbac6c7842845b2030e398b07cd89394058b49f7`  
		Last Modified: Mon, 21 May 2018 21:24:50 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
