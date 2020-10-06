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


## Install FFMPEG (Ubuntu)

```
sudo apt-get update
sudo apt-get install ffmpeg
ffmpeg -version
```




