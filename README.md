# BirdNET Analyzer CSV-converter

This is a project where I host some file conversion scripts that convert BirdNET Analyzer CSV-files to other formats. 

- [BirdNET CSV to SRT](/docs/csv-to-srt.html)

## BirdNET CSV to SRT

I use this to create subtitles for bird-watching videos.  
It is a static website that is entirely client-side Javascript based that allows "uploading" a CSV-file from BirdNET Analyzer and converts it into an Subtitle SRT-file for use in my bird videos. 

The conversion does two alterations worth mentioning:
- BirdNET Analyzer generates 3 second segments (by default) so the same bird may be listed for a number of lines consecutively. These will be merged into a single caption with a longer duration, either until a different bird is detected or there is a pause.
- Only the Common name and he scientific name is included in the conversion, formatted as `Common name (Scientific name)`.

The converter converts all lines, including "Engine (engine)". You may want to clean those out if you do not want them in your subtitles. I don't edit the files, but I do remove those captions while editing the subtitles in Davinci Resolve.


The conversion is shown in a text field for copy, in case you don't trust downloads from somewhat unknown sources, but there is also a button to download the content as a `.srt` file with the same name as the upload, apart from the file extension obviously. 

The website is *super* simple, because I am not a web developer.

I have only tested it on my personal systems, which is Safari on MacOS 15 so far. And the files have been successfully imported into Davinci Resolve timelines. 

### Suggested workflow

Here's how I use the tool:
1. Record and edit the video
2. Make sure bird sound levels are decent enough  
(to make BirdNET detections more accurate)
3. When happy with the edit and sound, render/export *audio only* wav-file
4. Do a batch-job analysis of the wav-file with CSV-output enabled
5. Upload the csv-file to the tool and download the resulting SRT
6. Create a new subtitle track (unless there is one already) and import the SRT
7. Add any additional captions and subtitles to the track if necessary
8. Render video with subtitles. Sometimes I render the video with the subtitles burned into the video, sometimes I make them optional for those that want them on Youtube.

Sometimes I use multiple subtitle tracks; for example one for action closed captions for screen readers, one for commentary and one for bird sounds. For vision-impaired viewers/listeners, having the subtitles as closed captions on youtube will enable their screen readers to read out loud the bird names.

