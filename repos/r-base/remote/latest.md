## `r-base:latest`

```console
$ docker pull r-base@sha256:a388266f9cafd4fa5d198441090ebb8ee3dc63acc2bfb9b7a4caade6daedea24
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `r-base:latest` - linux; amd64

```console
$ docker pull r-base@sha256:ca727ea324963466078fbc09016406ee1a2de895eccb36e1458c638d39ddeeb3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **292.4 MB (292383784 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3cb19d24626792d6e70cd6132129531e6f6150734c3606e59cd0389705066d17`
-	Default Command: `["R"]`

```dockerfile
# Sat, 28 Apr 2018 07:34:19 GMT
ADD file:4083b281ac0fff9f921dc4ae956315316315bc0886a65d77b31686d67147a249 in / 
# Sat, 28 Apr 2018 07:34:19 GMT
CMD ["bash"]
# Fri, 04 May 2018 16:24:44 GMT
MAINTAINER "Carl Boettiger and Dirk Eddelbuettel" rocker-maintainers@eddelbuettel.com
# Fri, 04 May 2018 16:24:46 GMT
RUN useradd docker 	&& mkdir /home/docker 	&& chown docker:docker /home/docker 	&& addgroup docker staff
# Fri, 04 May 2018 16:25:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ed 		less 		locales 		vim-tiny 		wget 		ca-certificates 		fonts-texgyre 	&& rm -rf /var/lib/apt/lists/*
# Fri, 04 May 2018 16:25:08 GMT
RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen 	&& locale-gen en_US.utf8 	&& /usr/sbin/update-locale LANG=en_US.UTF-8
# Fri, 04 May 2018 16:25:08 GMT
ENV LC_ALL=en_US.UTF-8
# Fri, 04 May 2018 16:25:09 GMT
ENV LANG=en_US.UTF-8
# Fri, 04 May 2018 16:25:09 GMT
RUN echo "deb [trusted=yes] https://eddelbuettel.github.io/drr35/ ./" > /etc/apt/sources.list.d/debian-r-3.5.list
# Fri, 04 May 2018 16:25:10 GMT
ENV R_BASE_VERSION=3.5.0
# Sat, 05 May 2018 04:03:46 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		littler                 r-cran-littler 		r-base=${R_BASE_VERSION}-* 		r-base-dev=${R_BASE_VERSION}-* 		r-recommended=${R_BASE_VERSION}-*         && echo 'options(repos = c(CRAN = "https://cloud.r-project.org/"), download.file.method = "libcurl")' >> /etc/R/Rprofile.site         && echo 'source("/etc/R/Rprofile.site")' >> /etc/littler.r 	&& ln -s /usr/lib/R/site-library/littler/examples/install.r /usr/local/bin/install.r 	&& ln -s /usr/lib/R/site-library/littler/examples/install2.r /usr/local/bin/install2.r 	&& ln -s /usr/lib/R/site-library/littler/examples/installGithub.r /usr/local/bin/installGithub.r 	&& ln -s /usr/lib/R/site-library/littler/examples/testInstalled.r /usr/local/bin/testInstalled.r 	&& install.r docopt 	&& rm -rf /tmp/downloaded_packages/ /tmp/*.rds 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 04:03:46 GMT
CMD ["R"]
```

-	Layers:
	-	`sha256:ae5da26d7cb2cb22d27c9edbae4639e74326f509b5bd8ec5d0cf1491e8e51667`  
		Last Modified: Sat, 28 Apr 2018 09:44:58 GMT  
		Size: 48.3 MB (48303208 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0b880925732c0e6612b43bfa67a101a7ef3c11e4e7a247a2ef58dabe688807a`  
		Last Modified: Sat, 05 May 2018 04:04:01 GMT  
		Size: 2.0 KB (1975 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb316a3c58d9b8fc774deeed44ff36e1016bd117e6b55680cf6975fd3075e814`  
		Last Modified: Sat, 05 May 2018 04:04:07 GMT  
		Size: 24.8 MB (24803554 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d37c7c25f9e504e91998d0a3d0183efca0616f0442bc36494db44ed9dd16c2f2`  
		Last Modified: Sat, 05 May 2018 04:04:02 GMT  
		Size: 426.6 KB (426570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5b0ac6f1c26414a11403a08d8cd0809fb566e2c75c28b3389aa2ff39be305c7`  
		Last Modified: Sat, 05 May 2018 04:04:01 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee2c8250c48760148d99199c6630f799e4d4d20a4319d2ff01d7c2feb2e4e2b1`  
		Last Modified: Sat, 05 May 2018 04:04:28 GMT  
		Size: 218.8 MB (218848239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
