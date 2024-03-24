
## Trancoding h265 to h264 using Nvidia CUDA

ffmpeg -hwaccel cuda -hwaccel_output_format cuda -i input.mkv -c:a copy -c:v h264_nvenc -preset slow output.mkv
## Convert mpegts to mp4

ffmpeg -hwaccel cuda -i input.ts -r 24 -c:v h264_nvenc output.mp4