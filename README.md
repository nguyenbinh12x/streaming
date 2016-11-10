# streaming

## About Streaming
Streaming media is multimedia that is constantly received by and presented to an end-user while being delivered by a provider. 
Live streaming refers to Internet content delivered in real-time, as events happen, much as live television broadcasts its contents over the airwaves via a television signal.

-> Microsoft developed a media player known as ActiveMovie in 1995 that allowed streaming media and included a proprietary streaming format
-> In June 1999 Apple also introduced a streaming media format in its QuickTime 4 application
-> Around 2002, the interest in a single, unified, streaming format and the widespread adoption of Adobe Flash prompted the development of a video streaming format through Flash

HTTP Live Streaming (also known as HLS) is an HTTP-based media streaming communications protocol implemented by Apple Inc.
Wowza Streaming Engine powers streaming of high-quality video and audio to any device, anywhere.

The name of the project is inspired by the MPEG video standards group, together with "FF" for "fast forward"FFmpeg is a free software project that produces libraries and programs for handling multimedia data.


*File format*
->M3U8 files are the basis for the HTTP Live Streaming (HLS) format originally developed by Apple to stream video. M3U is a computer file format for a multimedia playlist.

-> WebM is a video file format. WebM initially supported VP8 video and Vorbis audio streams. In 2013 it was updated to accommodate VP9 video and Opus audio. YouTube offers WebM videos as part of its HTML5 player

*References*:
```
[1]. http://www.webmproject.org
[2]. https://www.ffmpeg.org
[3]. http://trac.ffmpeg.org/wiki
[4]. https://github.com/arut/nginx-rtmp-module
[5]. http://trac.ffmpeg.org/wiki/CompilationGuide/Ubuntu
```
## How to build Steaming System

This guide install ffmpeg on Ubuntu OS. See more than above link.
Main steps to install ffmpeg as following:

*Get the Dependencies:*

```
sudo apt-get update
sudo apt-get -y install autoconf automake build-essential libass-dev libfreetype6-dev \
  libsdl1.2-dev libtheora-dev libtool libva-dev libvdpau-dev libvorbis-dev libxcb1-dev libxcb-shm0-dev \
  libxcb-xfixes0-dev pkg-config texinfo zlib1g-dev
```

*Installation lib dependencies:*

See more than this link http://trac.ffmpeg.org/wiki/CompilationGuide/Ubuntu
```
	Yasm
	libx264
	libfdk-aac
	libmp3lame
	libopus
	libvpx
	xvid
	libtheora
	aacenc
	libvorbic
	libogg
	ffmpeg
```
*Installation nginx with nginx-rtmp-module:*

https://github.com/arut/nginx-rtmp-module

```
wget http://nginx.org/download/nginx-1.6.2.tar.gz
tar -zxvf nginx-1.6.2.tar.gz

git clone https://github.com/arut/nginx-rtmp-module.git
cd nginx-1.6.2
./configure --add-module=../nginx-rtmp-module --with-http_ssl_module --with-http_gzip_static_module --with-poll_module
make
make install

```


## Using Ansible to deploy one streaming system

Assumption is running on ubuntu os, we have some components as:
+ ubuntu os
+ install lib dependencies
+ install ffmpeg
+ install nginx with nginx-rtmp-module
+ streaming with player

Sample files as 
```
vars
roles
```
