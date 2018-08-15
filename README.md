# reductive_audio_trim

It seems like most CLI tools that offer trimming/removal of sections of audio and video files
only allow you to pass the sections you want to _keep_ as arguments -

e.g. if you have an audio file that is 60 seconds long, and you want to remove the time ranges 5s-15s and 45-50s, you have to call:

```
some_program --trim =0 =5 =15 =45 =50 [--end]
```

this is annoying.

the otherwise excellent library [ffmpeg](https://github.com/FFmpeg/FFmpeg) seems to have a currently unfixed [bug](https://trac.ffmpeg.org/ticket/4950) that prevents you from passing the time ranges you want to keep.

`reductive_audio_trim` allows you to pass the sections you want to remove instead.


## Requirements
[sox](https://github.com/chirlu/sox) is the only requirement.

## Usage
```
./audio_trim input.mp3 output.mp3 11,16 24,39
```

By default, it retains the bitrate of the input file.