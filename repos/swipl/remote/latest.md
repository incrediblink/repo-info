## `swipl:latest`

```console
$ docker pull swipl@sha256:d2dbfaf9b839f799d00860ed4ade0d624f0b81842eec81d6cad82cf2e8d58a83
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7

### `swipl:latest` - linux; amd64

```console
$ docker pull swipl@sha256:51be2a0ad1fdbfb4655a962eca83428a9a0e292eb056f054a5e96dc296ebc833
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **56.3 MB (56296834 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c00185bb6054011860ec905d3f7169091dbdf33473d1ed5edf2e72d2252fa55`
-	Default Command: `["swipl"]`

```dockerfile
# Sat, 28 Apr 2018 07:09:59 GMT
ADD file:ec5be7eec56a749752ca284359ece04f5eb0b981eac08b8855454c6b16e3893c in / 
# Sat, 28 Apr 2018 07:09:59 GMT
CMD ["bash"]
# Wed, 02 May 2018 10:46:29 GMT
LABEL maintainer=Dave Curylo <dave@curylo.org>, Michael Hendricks <michael@ndrix.org>
# Wed, 02 May 2018 10:46:56 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends     libarchive13     libgmp10     libossp-uuid16     libssl1.1     ca-certificates     libdb5.3     libpcre3     libedit2     libgeos-c1v5     libspatialindex4v5     unixodbc     odbc-postgresql     tdsodbc     libmariadbclient18     libsqlite3-0     libserd-0-0     libraptor2-0 &&     dpkgArch="$(dpkg --print-architecture)" &&     { [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || apt-get install -y --no-install-recommends librocksdb4.5; } &&     rm -rf /var/lib/apt/lists/*
# Wed, 16 May 2018 20:14:42 GMT
RUN set -eux;     SWIPL_VER=7.7.14;     SWIPL_CHECKSUM=91ac11bad692261b567e409f485cb19fa061a0c4175ec18e1c09ef88c05cf7ab;     BUILD_DEPS='make gcc g++ wget git autoconf libarchive-dev libgmp-dev libossp-uuid-dev libpcre3-dev libreadline-dev libedit-dev libssl-dev zlib1g-dev libdb-dev unixodbc-dev libsqlite3-dev libserd-dev libraptor2-dev libgeos++-dev libspatialindex-dev';     dpkgArch="$(dpkg --print-architecture)";     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || BUILD_DEPS="$BUILD_DEPS librocksdb-dev";     apt-get update; apt-get install -y --no-install-recommends $BUILD_DEPS; rm -rf /var/lib/apt/lists/*;     mkdir /tmp/src;     cd /tmp/src;     wget http://www.swi-prolog.org/download/devel/src/swipl-$SWIPL_VER.tar.gz;     echo "$SWIPL_CHECKSUM  swipl-$SWIPL_VER.tar.gz" >> swipl-$SWIPL_VER.tar.gz-CHECKSUM;     sha256sum -c swipl-$SWIPL_VER.tar.gz-CHECKSUM;     tar -xzf swipl-$SWIPL_VER.tar.gz;     cd swipl-$SWIPL_VER;     sed -e '/PREFIX=$HOME/c\PREFIX=/usr'         -e '/# export DISABLE_PKGS/c\export DISABLE_PKGS="jpl xpce"'         -e 's/# *\(EXTRA.*--disable-libdirversion\)/\1/'            build.templ > build;     chmod u+x build; ./build;     mkdir -p /usr/lib/swipl/pack;     cd /usr/lib/swipl/pack;     rm -rf /tmp/src;     install_addin () {         git clone "$2" "$1";         git -C "$1" checkout -q "$3";         if [ "$1" = 'space' ]; then (cd "$1"; ln -s configure.ac configure.in); fi;         if [ "$1" = 'prosqlite' ]; then rm -rf "$1/lib"; fi;         swipl -g "pack_rebuild($1)" -t halt;         find "$1" -mindepth 1 -maxdepth 1 ! -name lib ! -name prolog ! -name pack.pl -exec rm -rf {} +;         find "$1" -name .git -exec rm -rf {} +;     };     dpkgArch="$(dpkg --print-architecture)";     install_addin space https://github.com/JanWielemaker/space.git cd6fefa63317a7a6effb61a1c5aee634ebe2ca05;     install_addin prosqlite https://github.com/nicos-angelopoulos/prosqlite.git a1d915d07933ece27ea5fd68f07c83d10583e7a0;     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || install_addin rocksdb https://github.com/JanWielemaker/rocksdb.git 29eaee6fcdb6dce690ed187ef68b80ee94739412;     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] ||  install_addin hdt https://github.com/JanWielemaker/hdt.git e0a0eff87fc3318434cb493690c570e1255ed30e;     install_addin rserve_client https://github.com/JanWielemaker/rserve_client.git 72838bbfa3976a83d19fb38bdae04378e30f4b0d;     apt-get purge -y --auto-remove $BUILD_DEPS
# Wed, 16 May 2018 20:14:43 GMT
ENV LANG=C.UTF-8
# Wed, 16 May 2018 20:14:43 GMT
CMD ["swipl"]
```

-	Layers:
	-	`sha256:f2aa67a397c49232112953088506d02074a1fe577f65dc2052f158a3e5da52e8`  
		Last Modified: Sat, 28 Apr 2018 09:31:20 GMT  
		Size: 22.5 MB (22496029 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9af33a0646336672d16452176d805af179a15e9147b348813aa5c537067a88f`  
		Last Modified: Wed, 02 May 2018 11:18:52 GMT  
		Size: 26.3 MB (26259851 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964eb41fb03d08767d5ab26465e8fe4017a37d662c8ed709f8f2228a3e0efe62`  
		Last Modified: Wed, 16 May 2018 20:15:14 GMT  
		Size: 7.5 MB (7540954 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `swipl:latest` - linux; arm variant v7

```console
$ docker pull swipl@sha256:95c5b1477d7842a6910a5ec0ca50740aad102f9ac87e02e84e0d995304ea298b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **48.8 MB (48838995 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:022e4e270100e5fae77f427900e512189919d85cfcc5fe3814d276e63fa2c6a0`
-	Default Command: `["swipl"]`

```dockerfile
# Sat, 28 Apr 2018 12:04:59 GMT
ADD file:f8bb9e9954bfe2f550e8a786c4be1dd5fca4a373b82b372b80c163e5640bd5a4 in / 
# Sat, 28 Apr 2018 12:05:00 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 13:38:19 GMT
LABEL maintainer=Dave Curylo <dave@curylo.org>, Michael Hendricks <michael@ndrix.org>
# Sat, 28 Apr 2018 13:38:39 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends     libarchive13     libgmp10     libossp-uuid16     libssl1.1     ca-certificates     libdb5.3     libpcre3     libedit2     libgeos-c1v5     libspatialindex4v5     unixodbc     odbc-postgresql     tdsodbc     libmariadbclient18     libsqlite3-0     libserd-0-0     libraptor2-0 &&     dpkgArch="$(dpkg --print-architecture)" &&     { [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || apt-get install -y --no-install-recommends librocksdb4.5; } &&     rm -rf /var/lib/apt/lists/*
# Thu, 17 May 2018 12:05:10 GMT
RUN set -eux;     SWIPL_VER=7.7.14;     SWIPL_CHECKSUM=91ac11bad692261b567e409f485cb19fa061a0c4175ec18e1c09ef88c05cf7ab;     BUILD_DEPS='make gcc g++ wget git autoconf libarchive-dev libgmp-dev libossp-uuid-dev libpcre3-dev libreadline-dev libedit-dev libssl-dev zlib1g-dev libdb-dev unixodbc-dev libsqlite3-dev libserd-dev libraptor2-dev libgeos++-dev libspatialindex-dev';     dpkgArch="$(dpkg --print-architecture)";     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || BUILD_DEPS="$BUILD_DEPS librocksdb-dev";     apt-get update; apt-get install -y --no-install-recommends $BUILD_DEPS; rm -rf /var/lib/apt/lists/*;     mkdir /tmp/src;     cd /tmp/src;     wget http://www.swi-prolog.org/download/devel/src/swipl-$SWIPL_VER.tar.gz;     echo "$SWIPL_CHECKSUM  swipl-$SWIPL_VER.tar.gz" >> swipl-$SWIPL_VER.tar.gz-CHECKSUM;     sha256sum -c swipl-$SWIPL_VER.tar.gz-CHECKSUM;     tar -xzf swipl-$SWIPL_VER.tar.gz;     cd swipl-$SWIPL_VER;     sed -e '/PREFIX=$HOME/c\PREFIX=/usr'         -e '/# export DISABLE_PKGS/c\export DISABLE_PKGS="jpl xpce"'         -e 's/# *\(EXTRA.*--disable-libdirversion\)/\1/'            build.templ > build;     chmod u+x build; ./build;     mkdir -p /usr/lib/swipl/pack;     cd /usr/lib/swipl/pack;     rm -rf /tmp/src;     install_addin () {         git clone "$2" "$1";         git -C "$1" checkout -q "$3";         if [ "$1" = 'space' ]; then (cd "$1"; ln -s configure.ac configure.in); fi;         if [ "$1" = 'prosqlite' ]; then rm -rf "$1/lib"; fi;         swipl -g "pack_rebuild($1)" -t halt;         find "$1" -mindepth 1 -maxdepth 1 ! -name lib ! -name prolog ! -name pack.pl -exec rm -rf {} +;         find "$1" -name .git -exec rm -rf {} +;     };     dpkgArch="$(dpkg --print-architecture)";     install_addin space https://github.com/JanWielemaker/space.git cd6fefa63317a7a6effb61a1c5aee634ebe2ca05;     install_addin prosqlite https://github.com/nicos-angelopoulos/prosqlite.git a1d915d07933ece27ea5fd68f07c83d10583e7a0;     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] || install_addin rocksdb https://github.com/JanWielemaker/rocksdb.git 29eaee6fcdb6dce690ed187ef68b80ee94739412;     [ "$dpkgArch" = 'armhf' ] || [ "$dpkgArch" = 'armel' ] ||  install_addin hdt https://github.com/JanWielemaker/hdt.git e0a0eff87fc3318434cb493690c570e1255ed30e;     install_addin rserve_client https://github.com/JanWielemaker/rserve_client.git 72838bbfa3976a83d19fb38bdae04378e30f4b0d;     apt-get purge -y --auto-remove $BUILD_DEPS
# Thu, 17 May 2018 12:05:13 GMT
ENV LANG=C.UTF-8
# Thu, 17 May 2018 12:05:13 GMT
CMD ["swipl"]
```

-	Layers:
	-	`sha256:6c8a025e90b325dd5af06b0297cc1608120a47d4ab0e1cedb26c8cda811091d6`  
		Last Modified: Sat, 28 Apr 2018 12:16:08 GMT  
		Size: 19.3 MB (19286790 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e5b7199fb784e326d63387ad1cd1e03b6353af3e45c9b219576ad31e27aae85`  
		Last Modified: Sat, 28 Apr 2018 13:42:50 GMT  
		Size: 22.7 MB (22684188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e52777ba38f75180f09f3fc64b218ff7912e9af6b63810811c4db741c6d6cdd`  
		Last Modified: Thu, 17 May 2018 12:05:43 GMT  
		Size: 6.9 MB (6868017 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
