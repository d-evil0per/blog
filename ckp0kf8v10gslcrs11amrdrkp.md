---
title: "Mp3 to Wav File Conversion using Python"
seoTitle: "Mp3 to Wav using Python"
seoDescription: "WAV and MP3 are file formats for storing digital audio. These can be differentiated by the fact that the MP3 is the lossy and compressed type of file where"
datePublished: Sun May 23 2021 02:32:23 GMT+0000 (Coordinated Universal Time)
cuid: ckp0kf8v10gslcrs11amrdrkp
slug: mp3-to-wav-file-conversion-using-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1621732937668/LwOWdMgTk.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1621737106304/9_to0j0hzU.jpeg
tags: python3, script, 2articles1week

---


Before we start discussing the conversion of these two audio file formats. Let's talk about what are these formats and what is the difference and when to use these formats.

#  [WAV ](https://en.wikipedia.org/wiki/WAV) vs [MP3 ](https://en.wikipedia.org/wiki/MP3)
[WAV ](https://en.wikipedia.org/wiki/WAV) and  [MP3 ](https://en.wikipedia.org/wiki/MP3) are file formats for storing digital audio. These can be differentiated by the fact that the [MP3 ](https://en.wikipedia.org/wiki/MP3)is the lossy and compressed type of file where some amount of information from the original audio source is discarded. On the other hand, the WAV  format is an uncompressed type of audio file. The size of the WAV file is very much higher than the MP3  file.

### Comparison Chart

| BASIS FOR COMPARISON	 | WAV | MP3 |
|-----------------------|-----|-----|
| Expands to            | Waveform Audio File Format    | MPEG layer 3   |
| Basic                 | Implement minimal changes in the original file.    | Removes the redundant portions of information from the file.   |
| Compression level     | Low   |  High   |
| Size                  | Larger   | Smaller    |
| Quality               | Good    | Moderate    |
| Developed By          | Microsoft and IBM    | MPEG   |

### Key Difference

- The audio encoding formats WAV and MP3 mainly differ by the extent of compression and quality. WAV  preserves the quality of the audio file by employing negligible changes in the source file. As against, MP3  can produce the smallest size version of the same file in WAV  format by removing similar data.
- By MP3  huge rates of compression can be achieved as compared to WAV.
- The size of the WAV file is generally higher than that of the MP3 file.
- MP3  format extremely degrades the audio quality while WAV file remains in good quality.
- WAV  was developed by Microsoft and IBM. On the contrary, MP3 was devised by MPEG and which is a patented format.

### Conclusion

Among the audio file formats, [WAV ](https://en.wikipedia.org/wiki/WAV) and [MP3 ](https://en.wikipedia.org/wiki/MP3), the WAV is compatible across various devices as it undergoes minimal alterations from the actual audio signals and also contains the absolute information required to translate analog audio to digital format. Conversely, in MP3 format the redundant information is discarded in order to reduce the size of the file to a higher extent.

# Convert mp3 to wav using Python

We can convert a mp3 file to wav file using two methods.

### **Method 1:**

First We Need To Install ffmpeg. It Is A Free Open Source Software Project Consist of a Large Suite Of Libraries And Programs For Handling Video, Audio, And Other Multimedia Files.

For Linux & MacOS:
<pre><code> sudo apt-get install ffmpeg  </code></pre>

For Windows:
- Go to the  [ffmpeg download site](https://ffmpeg.zeranoe.com/builds/)  and download the zip file that best fits your computer's specs. Choose the "static" linking and the "nightly git" version for the most current usability.
-Create a folder on your computer to unpack the zip file. This folder will be your "installation" folder. I chose `C:\Program Files\ffmpeg\.` This is a good idea because you will treat this as a regular program. Unpack the zip file into this folder.
- The folder should now contain a number of other folders, including one titled bin where `ffmpeg.exe` is saved. We're not done yet. Double-clicking that file does nothing. Remember, this is a command-line program. It runs in cmd.
- Before you can use `ffmpeg.exe` in cmd you have to tell your computer where it can find it. You need to add a new system path. First, right-click `This PC (Windows 10)` or `Computer (Windows 7)` then click `Properties > Advanced System Settings > Advanced tab > Environment Variables`.
- In the Environment Variables window, click the `"Path"` row under the `"Variable"` column, then click Edit
- The `"Edit environment variable"` window looks different for Windows 10 and 7. In Windows 10 click New then paste the path to the folder that you created earlier where `ffmpeg.exe` is saved. For this example, that is `C:\Program Files\ffmpeg\bin\ ![Add new system path Windows 10]]3` In Windows 7 all the variables are listed in a single string, separated by a semicolon. Simply go to the end of the string, type a semicolon (;), then paste in the path.
- Click Ok on all the windows we just opened up.
- `FFmpeg is now "installed".` The Command Prompt will now recognize FFmpeg commands and will attempt to run them. (If you are still having issues with Command Prompt not recognizing FFmpeg try running CMD as an admin. Alternatively, you can use Windows PowerShell instead of cmd. If it still does not work double-check to make sure each step was followed to completion.)

**Python Code**

It is a simple two-line script or code to convert an mp3 file to wav file.
<pre></code>
# import required modules
import subprocess

# convert mp3 to wav file
subprocess.call(['ffmpeg', '-i', 'hello.mp3',
				'converted_to_wav_file.wav'])

</code></pre>

### **Method 2:**

[pydub](https://pypi.org/project/pydub/), Audio Manipulation Module. Python Provides a Module Called pydub to Work With Audio Files. pydub is a Python library to work with only .wav files.
<pre><code> sudo apt-get install -y python-pydub </code></pre>
or 
<pre><code> pip install pydub </code></pre>

**Python Code**

<pre><code>
# import required modules
from os import path
from pydub import AudioSegment

# assign files
input_file = "hello.mp3"
output_file = "result.wav"

# convert mp3 file to wav file
sound = AudioSegment.from_mp3(input_file)
sound.export(output_file, format="wav")

</code></pre>

** The pydub module uses either FFmpeg or avconf programs to do the actual conversion. So you do have to install FFmpeg to make this work. But if you don’t need pydub for anything else, you can just use the built-in subprocess module to call a convertor program like FFmpeg **


	
