# Lip Sync Code

This code performs *lip-syncing* operations using the `Wav2Lip` model. It takes an input audio file and a video file to generate a new video with synchronized lip movements.

## How It Works

The code utilizes the **MoviePy** library to process video files. Here's how it works:
- It checks the video duration, and if it exceeds 70 seconds, a warning is issued, as processing such long videos can be time-consuming.
- If the video resolution is greater than or equal to 1920x1080, it resizes the video to 720p (1280x720). Lower resolution videos typically yield better lip-sync results.
- The final video has no audio, as lip-syncing involves replacing the original audio with synchronized lip movements.

The final video file along with audio file are passed to the selected model.
<div style="display: flex; justify-content: center;">
    <video src='https://github.com/khethan123/LipSync/assets/100506743/19b33171-7de8-47d4-9015-7287fbc3f40a' width=60/> 
</div>

## How to Run

Follow these steps to use the code:
1. Open the code in a Python environment that supports Jupyter notebooks or Colab notebooks.
2. Ensure you have the required libraries installed (MoviePy, OpenCV, ffmpeg).
3. Upload your audio and video files to the environment.
4. Enter the file paths for the audio and video in the provided cells.
5. Run the code, and make sure to select GPU as the runtime type if using Google Colab.
6. Customize parameters like padding and the selected model, then play the edited video.

Feel free to experiment with different video files and resolutions to observe the code's performance.

Use FFmpeg to change the resolution of a video from 720p to another resolution. You can use this command in a Google Colab notebook or on a local machine if you want to change the resolution of the output video file.
* In Google Colab Notebook
``` python
!ffmpeg -i "input/file/path" -vf "scale=1920:1080:flags=lanczos" -sws_dither ed -c:v libx264 -crf 18 -preset slow "output/file/path"
``` 
* In Local Machine
```bash
ffmpeg -i "input/file/path" -vf "scale=1920:1080:flags=lanczos" -sws_dither ed -c:v libx264 -crf 18 -preset slow "output/file/path"
```
Make sure to adjust the input and output file paths to your specific requirements and also change scale according to your preference.<br>
**Note: When using Google Colab, remember to change the runtime type to GPU for faster video processing.**

### Final output.
<div style="display: flex; justify-content: center;">
    <video src='https://github.com/khethan123/LipSync/assets/100506743/ac446396-3933-4ebb-9c02-4743892542a0' width=60/>
</div>
