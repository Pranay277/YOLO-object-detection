# Week 3 - Video Download and Frame Extraction using yt-dlp and FFmpeg

## Objective
To learn how to download publicly available (non-copyrighted) videos using **yt-dlp**, and extract frames from them using **FFmpeg** for computer vision tasks.

---

## Steps Performed

### 1. Installed yt-dlp
To enable downloading public YouTube videos:
```bash
pip install yt-dlp
```

### 2. Downloaded a Public Video
Downloaded a non-copyrighted, public video from YouTube and saved it as `input.mp4`:
```bash
yt-dlp -f mp4 "https://www.youtube.com/watch?v=VIDEO_ID" -o input.mp4
```

> **Note:** This command downloads the video in MP4 format and stores it as `input.mp4` in the current working directory.

### 3. Installed FFmpeg
Installed FFmpeg using Conda (within the YOLO environment):
```bash
conda install -c conda-forge ffmpeg
```

> **Important:**  
> FFmpeg is installed **inside the Conda environment** (`yolovenv`), not in the local project folder.

### 4. Verified FFmpeg Installation
Checked if FFmpeg was successfully installed:
```bash
ffmpeg -version
```

### 5. Extracted Frames using FFmpeg
Converted the downloaded video into a sequence of image frames:
```bash
ffmpeg -i input.mp4 frames/frame_%04d.jpg
```
This command created a folder named `frames` containing individual image files like:
```
frame_0001.jpg, frame_0002.jpg, frame_0003.jpg, ...
```

---

## Output
- **Video File:** `input.mp4`  
- **Extracted Frames Folder:** `frames/`  
- Each frame stored sequentially as `.jpg` files

Example output structure:
```
📂 frames/
 ├── frame_0001.jpg
 ├── frame_0002.jpg
 ├── frame_0003.jpg
 └── ...
```

---

## Environment Details
- Environment: `yolovenv`  
- Python: 3.10  
- Packages: yt-dlp, ffmpeg  
- Platform: Windows 11  
- Tool: Anaconda + Jupyter Notebook / Command Prompt  

---

## Challenges Faced During Setup

1. **Permission & Copyright Concerns**  
   Initially, I learned that not all YouTube videos can be downloaded legally. I made sure to only use **public and non-copyrighted** videos for educational and research purposes.

2. **Frame Extraction Path Error**  
   I got an error initially because I didn’t have the `frames` command and folder properly set up. Later, after installing FFmpeg correctly and creating the folder, it worked fine.

3. **Working Directory Issues in Jupyter**  
   I had to make sure my Jupyter Notebook was running in the same directory where `input.mp4` was stored. Using `os.getcwd()` and `os.chdir()` helped fix path mismatches.

---

## Learning Outcome

Through this exercise, I learned:
- How to **safely and legally download** public videos using `yt-dlp`.
- How to **extract image frames** efficiently using **FFmpeg**.
- The importance of environment management using **Conda**.
- How to handle **path, dependency, and directory issues** in real-world setups.

This task provided a strong foundation for preparing video datasets for future computer vision tasks like object detection, segmentation, and tracking.

---
