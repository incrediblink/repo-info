## `wordpress:php7.0-fpm-alpine`

```console
$ docker pull wordpress@sha256:cb379f24a5025c9d379168ea11e846370a8079b15b1d1b1d3cddca87f22e7232
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `wordpress:php7.0-fpm-alpine` - linux; amd64

```console
$ docker pull wordpress@sha256:036bcfea8486792fe39dfa83daddb2d7d53cd1e4b9819e2763530e3999d59e7f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.4 MB (40376738 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0fcc6fe586c97129d7f14a75fa6758475bff924d6ab591a6e0137df6257eb635`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Tue, 09 Jan 2018 21:12:40 GMT
ADD file:69848cb51056edaf120230b6f218a79968ac797295c2cef6728332e1801357be in / 
# Tue, 09 Jan 2018 21:12:40 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:00:23 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Wed, 10 Jan 2018 03:00:28 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		openssl
# Wed, 10 Jan 2018 03:00:35 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Wed, 10 Jan 2018 03:00:35 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Wed, 10 Jan 2018 03:00:36 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Wed, 10 Jan 2018 03:05:56 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 03:05:57 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 10 Jan 2018 03:54:25 GMT
ENV GPG_KEYS=1A4E8B7277C42E53DBA9C7B9BCAA30EA9C0D5763 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Fri, 27 Apr 2018 03:20:26 GMT
ENV PHP_VERSION=7.0.30
# Fri, 27 Apr 2018 03:20:27 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.0.30.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.0.30.tar.xz.asc/from/this/mirror
# Fri, 27 Apr 2018 03:20:27 GMT
ENV PHP_SHA256=c90892fb68ab9b8476519658d3f78f6388f2609ae1309bdc2a2e1cc9f92dd686 PHP_MD5=
# Fri, 27 Apr 2018 03:51:20 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 27 Apr 2018 03:51:20 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 05 May 2018 01:58:11 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		openssl-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--disable-cgi 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 05 May 2018 01:58:12 GMT
COPY multi:af8a06a5cfc82b17b169c6d1e48630a516582fa7ce00d8e59e5a378e100d064a in /usr/local/bin/ 
# Sat, 05 May 2018 01:58:12 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 05 May 2018 01:58:13 GMT
WORKDIR /var/www/html
# Sat, 05 May 2018 01:58:13 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = 9000'; 	} | tee php-fpm.d/zz-docker.conf
# Sat, 05 May 2018 01:58:13 GMT
EXPOSE 9000/tcp
# Sat, 05 May 2018 01:58:14 GMT
CMD ["php-fpm"]
# Sat, 05 May 2018 15:02:39 GMT
RUN apk add --no-cache 		bash 		sed
# Sat, 05 May 2018 15:03:13 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		libjpeg-turbo-dev 		libpng-dev 	; 		docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr; 	docker-php-ext-install gd mysqli opcache; 		runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local/lib/php/extensions 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)"; 	apk add --virtual .wordpress-phpexts-rundeps $runDeps; 	apk del .build-deps
# Sat, 05 May 2018 15:03:13 GMT
RUN { 		echo 'opcache.memory_consumption=128'; 		echo 'opcache.interned_strings_buffer=8'; 		echo 'opcache.max_accelerated_files=4000'; 		echo 'opcache.revalidate_freq=2'; 		echo 'opcache.fast_shutdown=1'; 		echo 'opcache.enable_cli=1'; 	} > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Sat, 05 May 2018 15:03:14 GMT
VOLUME [/var/www/html]
# Mon, 21 May 2018 21:37:14 GMT
ENV WORDPRESS_VERSION=4.9.6
# Mon, 21 May 2018 21:37:15 GMT
ENV WORDPRESS_SHA1=40616b40d120c97205e5852c03096115c2fca537
# Mon, 21 May 2018 21:37:18 GMT
RUN set -ex; 	curl -o wordpress.tar.gz -fSL "https://wordpress.org/wordpress-${WORDPRESS_VERSION}.tar.gz"; 	echo "$WORDPRESS_SHA1 *wordpress.tar.gz" | sha1sum -c -; 	tar -xzf wordpress.tar.gz -C /usr/src/; 	rm wordpress.tar.gz; 	chown -R www-data:www-data /usr/src/wordpress
# Mon, 21 May 2018 21:37:18 GMT
COPY file:3d3c99e98daa50fa9919315d4531e921f800fc011486bda46e9d6dcea82dd53c in /usr/local/bin/ 
# Mon, 21 May 2018 21:37:18 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 21 May 2018 21:37:18 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:81033e7c1d6a5b44a94bb6b40033a6e589f50fd6b61578da6fc809e61f83898d`  
		Last Modified: Tue, 09 Jan 2018 21:15:04 GMT  
		Size: 2.4 MB (2387570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:347280e4401ec27a2af6bcded9c9fe28c0acbe751f69f1d47c4fd6d2c82ba034`  
		Last Modified: Wed, 10 Jan 2018 04:40:03 GMT  
		Size: 1.3 MB (1324983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:575b1e17046fe1c06043ae027f4599ed64f34196604a884d74c8942cdf71873e`  
		Last Modified: Wed, 10 Jan 2018 04:40:02 GMT  
		Size: 1.3 KB (1274 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b26c263d6f029c4ccdfe4f8da176f53cbf3870d7d83f852d8b05ec3a606374d9`  
		Last Modified: Wed, 10 Jan 2018 04:40:00 GMT  
		Size: 167.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b051b5fa3beb9690c7eb93603b8b95437af19a5df2082fc73e3ff280def2e355`  
		Last Modified: Fri, 27 Apr 2018 05:47:51 GMT  
		Size: 12.0 MB (12049053 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ea547c20eb33ba712ff988c4b9f3476aebb158b89b789b647e15756b949de29`  
		Last Modified: Fri, 27 Apr 2018 05:47:47 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:425fc9fef9057023dafd233a65c5fc51b6543efde46a5b90a7863c3421c9ed7b`  
		Last Modified: Sat, 05 May 2018 02:45:07 GMT  
		Size: 14.6 MB (14640833 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:887b1edfdcb12c366d26a8391a6567c14b4fe8d08625d75f16bc7fbcd4eface7`  
		Last Modified: Sat, 05 May 2018 02:45:05 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:86cdc5bec98f85ee6ab20b5875b0f67140ff0407ad504cd87e431d42271a59c2`  
		Last Modified: Sat, 05 May 2018 02:45:05 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fc85c62edd677d6249e668b02a9b7689ec7b0d47f63c08fd313c5659c5e0ab8`  
		Last Modified: Sat, 05 May 2018 02:45:05 GMT  
		Size: 7.8 KB (7750 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d72f099f541408164e4f1829b37cb8c00918e11517dcb7d820e6beb5dbb79f0a`  
		Last Modified: Sat, 05 May 2018 15:42:54 GMT  
		Size: 611.7 KB (611749 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fff095cdb7a4a0e9626abafb03e0c0d1fc08783998c8ef74b45da276590484f`  
		Last Modified: Sat, 05 May 2018 15:42:55 GMT  
		Size: 746.4 KB (746426 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3aa9c0d09ef7622b3d5bfbb91f7579b44b6962706fdea5ce66931b0a9ccadd3b`  
		Last Modified: Sat, 05 May 2018 15:42:55 GMT  
		Size: 341.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adb2155f8e09bd0c82bf8275df5776c1e5c2286061ede4cde6c7e4b18020febf`  
		Last Modified: Mon, 21 May 2018 21:43:22 GMT  
		Size: 8.6 MB (8600441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fd93364f08f212d7d40bce9fe1d44e21a299cfa4a51955d702ee0c403d0aacf`  
		Last Modified: Mon, 21 May 2018 21:43:20 GMT  
		Size: 3.4 KB (3352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
