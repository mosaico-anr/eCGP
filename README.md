
# eCGP
This repository is a meta repository for all the elements used to build our experimental cloud gaming platform.

* "game-stream-server" is the server part that streams its display to one or more client and applies their inputs.
* "game-stream-client" is the remote display element that plays the feeds provided by the server and send its user inputs (mouse, keyboard and controller).
* "game-stream-scream-proxy" contains both client and server proxies as they share a lot of code. They mostly forward traffic between each other. The server part implement SCReAM CCA for the video stream so it can adapt to network condition by providing feedback to the server (as recommended bitrate).

The platform global architecture can be represented as follow:
![eCGP architecture](https://github.com/mosaico-anr/eCGP/blob/main/image/Proxy.png?raw=true)

The cloud gaming server and client can work without SCReAM proxies and the proxies can also work without the cloud gaming part. Especially, the server-side proxy implements a RTP generator for basic tests with only the proxies. They are build as chains of blocks so they may be used for other purposes as well.

## Dependencies
FFmpeg 4.4.2 dev libs:
* libavdevice
* libavfilter
* libavformat
* libavcodec
* libswresample
* libswscale
* libavutil

SDL2 2.0.16 or newer
