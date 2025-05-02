

# PPT背景音乐处理

## 步骤
1、在线上找一个音频；
2、播放，用手机录音成m4a格式；
3、手机上剪辑，使用ffmpeg加工一下即可。


## 将m4a转换为mp3

```bash
ffmpeg -i input.m4a -c:a libmp3lame -q:a 0 output.mp3
```

## 使用ffmpeg降低音频播放速度

```bash
ffmpeg -i input.mp3 -filter:a "atempo=0.9" -vn output.mp3
```

> `atempo=0.9` 表示音频速度减慢为原来的 90%，可以设置 0.5～2.0 之间的值。  
  如果需要更慢的速度（如 0.7），必须分段处理或使用 `rubberband` 插件等。