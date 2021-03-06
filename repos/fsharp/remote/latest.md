## `fsharp:latest`

```console
$ docker pull fsharp@sha256:c306e9851e855c0dc5626e19385e47dc9501cbf9ee25b15eaf09946c7438e49c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `fsharp:latest` - linux; amd64

```console
$ docker pull fsharp@sha256:6c1f8e55b292d16d7aa88986fa66e5be6bd72a01648b9578d59611ff580e2e1f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **155.0 MB (155007506 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a1efede0b0b114a3d0c3f5e196726f7aaa0bcb878c7e5d656bb8cd9fdb79b6c7`
-	Default Command: `["fsharpi"]`

```dockerfile
# Sat, 28 Apr 2018 07:09:59 GMT
ADD file:ec5be7eec56a749752ca284359ece04f5eb0b981eac08b8855454c6b16e3893c in / 
# Sat, 28 Apr 2018 07:09:59 GMT
CMD ["bash"]
# Sat, 05 May 2018 04:33:41 GMT
LABEL maintainer=Dave Curylo <dave@curylo.org>, Steve Desmond <steve@stevedesmond.ca>
# Sat, 05 May 2018 04:33:42 GMT
ENV MONO_THREADS_PER_CPU=50
# Sat, 05 May 2018 04:41:49 GMT
RUN MONO_VERSION=5.8.0.127 &&     FSHARP_VERSION=10.0.2 &&     FSHARP_BASENAME=fsharp-$FSHARP_VERSION &&     FSHARP_ARCHIVE=$FSHARP_VERSION.tar.gz &&     FSHARP_ARCHIVE_URL=https://github.com/fsharp/fsharp/archive/$FSHARP_VERSION.tar.gz &&     export GNUPGHOME="$(mktemp -d)" &&     apt-get update && apt-get --no-install-recommends install -y gnupg dirmngr &&     apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF &&     echo "deb https://download.mono-project.com/repo/debian stretch/snapshots/$MONO_VERSION main" | tee /etc/apt/sources.list.d/mono-official-stable.list &&     apt-get install -y apt-transport-https &&     apt-get update -y &&     apt-get --no-install-recommends install -y pkg-config make nuget mono-devel msbuild ca-certificates-mono &&     rm -rf /var/lib/apt/lists/* &&     mkdir -p /tmp/src &&     cd /tmp/src &&     printf "namespace a { class b { public static void Main(string[] args) { new System.Net.WebClient().DownloadFile(\"%s\", \"%s\");}}}" $FSHARP_ARCHIVE_URL $FSHARP_ARCHIVE > download-fsharp.cs &&     mcs download-fsharp.cs && mono download-fsharp.exe && rm download-fsharp.exe download-fsharp.cs &&     tar xf $FSHARP_ARCHIVE &&     cd $FSHARP_BASENAME &&     make &&     make install &&     cd ~ &&     rm -rf /tmp/src /tmp/NuGetScratch ~/.nuget ~/.config ~/.local "$GNUPGHOME" &&     apt-get purge -y make gnupg dirmngr &&     apt-get clean
# Sat, 05 May 2018 04:41:49 GMT
WORKDIR /root
# Sat, 05 May 2018 04:41:50 GMT
CMD ["fsharpi"]
```

-	Layers:
	-	`sha256:f2aa67a397c49232112953088506d02074a1fe577f65dc2052f158a3e5da52e8`  
		Last Modified: Sat, 28 Apr 2018 09:31:20 GMT  
		Size: 22.5 MB (22496029 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e914d22f23b3d6c1fbab26820f91cf3a79f765cc384d9871e7eb6889d9612df`  
		Last Modified: Sat, 05 May 2018 04:54:48 GMT  
		Size: 132.5 MB (132511477 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
