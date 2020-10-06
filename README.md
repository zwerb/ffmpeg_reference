# FFMPEG Commands Reference

ffmpeg -i input -map 0 -c copy output.mkv


This will stream copy (re-mux) all streams:
```
ffmpeg -i input -map 0 -c copy output.mp4
```


This will re-encode the video to H.264 and stream copy the audio:
```
ffmpeg -i input.ts -c:v libx264 -c:a copy output.mp4
```

The next example will re-encode both video and audio:
```
ffmpeg -i input.ts -c:v libx264 -c:a aac output.mp4
```

Lossless H.264 example:
```
ffmpeg -i input.ts -c:v libx264 -crf 0 -c:a copy output.mp4
```

ffmpeg -i ts_files/drone_video-001.ts -map 0 -c copy mp4_remux/drone_video-001.mp4


## Install FFMPEG (Ubuntu)

```
sudo apt-get update
sudo apt-get install ffmpeg
ffmpeg -version
```

## Install GPU Acceleration for FFMPEG
```
git clone https://git.videolan.org/git/ffmpeg/nv-codec-headers.git
cd nv-codec-headers && sudo make install && cd –
git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg/
sudo apt-get install build-essential yasm cmake libtool libc6 libc6-dev unzip wget libnuma1 libnuma-dev
./configure --enable-nonfree -–enable-cuda-sdk –enable-libnpp --extra-cflags=-I/usr/local/cuda/include --extra-ldflags=-L/usr/local/cuda/lib64
make -j 8
sudo make install
```



