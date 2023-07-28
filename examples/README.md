# HLS & DASH example

## Running this example locally

You can run this example locally with Docker

```
% docker run -d -p 8080:80 -v $PWD/videos:/opt/static/videos -v $PWD/nginx.conf:/usr/local/nginx/conf/nginx.conf nginx-vod-module
```

After running this command, you should be able to play the following URLs:

- HLS: https://video.localhost:444/hls/devito720p.mp4/master.m3u8
- Dash: http://localhost:8080/dash/devito,360p.mp4,480p.mp4,720p.mp4,.en_US.vtt,.urlset/manifest.mpd
- Thumbnail: http://localhost:8080/thumb/devito360p.mp4/thumb-1000.jpg

http://localhost:8080/hls/devito720p.mp4,.urlset/master.m3u8
http://localhost:8080/hls/example1080p.mp4,.urlset/master.m3u8

docker run -d -p 444:444 -v $PWD/videos:/opt/static/videos -v $PWD/nginx.conf:/usr/local/nginx/conf/nginx.conf -v /etc/ssl/private/video.localhost.key:/etc/ssl/private/video.localhost.key -v /etc/ssl/certs/video.localhost.crt:/etc/ssl/certs/video.localhost.crt --name nginx-vod nginx-vod-module
