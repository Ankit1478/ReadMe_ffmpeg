# Work Flow of FFMPEG 

1. Input: ffmpeg(inputPath of file ) takes the  file as input.
2. Processing the task you want to perform
3. Output

Example 1. we extract the audio from a video file.

```
const ffmpeg = require('fluent-ffmpeg');
const path = require('path');

// Input and output paths
const inputVideo = path.join(__dirname, 'input-video.mp4');
const outputAudio = path.join(__dirname, 'output-audio.mp3');

// Extracting audio from the video file
ffmpeg(inputVideo)
  .output(outputAudio) // Convert to mp3 audio
  .noVideo() // Remove the video stream, keeping only the audio

  .on('end', function() {
    console.log('Audio extraction finished successfully');
  })
  .on('error', function(err) {
    console.error('Error during processing:', err.message);
  })
  .run();
   ```
