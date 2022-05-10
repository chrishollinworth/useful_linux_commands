ffmpeg -hwaccel cuda -hwaccel_output_format cuda -i input.mkv -c:a copy -c:v h264_nvenc -preset slow output.mkv

