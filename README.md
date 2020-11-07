# background

This project will show you how to setup rtmp dev environment including server, client, and libraries.

# server

## livego

```shell
$ go get github.com/gwuhaolin/livego
$ ./livego

## get the key for a live: movie
$ curl localhost:8090/control/get?room=movie

```



## nginx-rtmp

# client

## ffmpeg

```shell
## publish a stream from a local flv file
$ ./ffmpeg -stream_loop -1 -re  -i ~/demo.flv -c copy -f flv rtmp://localhost:1935/live/rfBd56ti2SMtYvSgD5xAV0YU99zampta7Z7S575KLkIZ9PYk

## play an live with the URL: rtmp://localhost:1935/live/movie
$ vlc rtmp://localhost:1935/live/movie
$ rtmpdump -r rtmp://localhost:1935/live/movie -o b.flv

```

* [rtmpdump source](http://rtmpdump.mplayerhq.hu/download/)
* [ffmpeg source](https://ffmpeg.org/download.html#releases)

# library

``` shell
## golang library gortmp
$ go get github.com/zhangpeihao/gortmp

## c library librtmp
$ wget http://rtmpdump.mplayerhq.hu/download/rtmpdump-2.3.tgz && tar xvf rtmpdump-2.3.tgz

## libyuv for yuv raw data scale and blit
$ git clone https://chromium.googlesource.com/libyuv/libyuv

```

# protocols

* [rtmp](https://www.adobe.com/devnet/rtmp.html)

* [amf0](https://www.adobe.com/content/dam/acom/en/devnet/pdf/amf0-file-format-specification.pdf)

* [amf3](https://www.adobe.com/content/dam/acom/en/devnet/pdf/amf-file-format-spec.pdf)

# tips

```shell
## play a yuv file
$ ffplay -f rawvideo -video_size 1920x1080 a.yuv


```

