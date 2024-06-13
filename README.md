# ffmpeg_cheetsheet

#### mkv电影转mp4

`ffmpeg -i input.mkv -vf "subtitles=input.mkv:si=0" -c:v h264_videotoolbox -c:a aac -ac 2 output.mp4`

参数解释：</br>
- `-vf "subtitles=input.mkv:si=0"`：用滤镜来渲染字幕，其中`si=0`表示选择第一个字幕流。
- `-c:v h264_videotoolbox`：选择视频编解码库，此例中使用VideoToolbox在Apple M1芯片上进行硬件编解码，也可以用libx264。
- `-ac 2`：输出为双声道立体声。如果输入mkv为5.1声道，有些播放器可能不支持5.1声道的mp4文件，此处需要限制下。
