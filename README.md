# Day 1 - YOLO Environment Setup and Basic Object Detection

## Objective
To set up the YOLO environment and run the first object detection task as part of the internship.

## Steps Performed
1. Created a new conda environment using:
   ```bash
   conda create -n yolovenv python=3.10
   conda activate yolovenv
   ```
2. Installed YOLO using:
   ```bash
   pip install ultralytics
   ```
3. Verified installation using:
   ```bash
   yolo
   ```
4. Performed object detection on a sample image:
   ```bash
   yolo predict model=yolov11n.pt source='https://ultralytics.com/images/bus.jpg'
   ```

## Output
The prediction result was saved in:
```
runs/detect/predict/
```

Example result screenshot can be placed here:
`screenshots/detection_result.jpg`

## Environment Details
- Python: 3.10  
- YOLO: ultralytics (latest)  
- Platform: Windows 11  
- Tool: Anaconda + Jupyter Notebook

## Challenges Faced During Environment Setup:-

Setting up the YOLO environment initially involved a few challenges, especially in configuring dependencies and ensuring GPU support. Some of the main issues I encountered were:

1.Environment and Package Conflicts:
While creating the new Conda environment, some Python packages such as torch and opencv had version conflicts. I resolved this by installing each dependency one at a time and verifying compatibility with the ultralytics package.

2.Installation Errors with YOLO Dependencies
During the pip install ultralytics step, there were warnings related to torch not being installed properly. After checking the YOLO documentation, I manually installed a compatible version of PyTorch using:
 ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
   ```
This fixed the issue and allowed YOLO to recognize GPU support.

3.Path and Command Issues in Anaconda Prompt
At first, running the yolo command gave an error saying it wasn’t recognized. The problem was that the environment wasn’t activated properly. I re-activated the environment using:
``` bash
conda activate yolovenv
```
After that, the yolo command worked correctly.

4.GPU Utilization Check
I wanted to make sure YOLO was running on my NVIDIA GPU (since my laptop supports it). I verified this by running:
``` bash
nvidia-smi
```
and confirmed that the GPU was being used during inference.

5.Directory Navigation Issues in Jupyter
While running Jupyter Notebook, I had to learn how to navigate to the correct working directory (my project folder) before executing YOLO commands. Once I understood that process, the workflow became smooth.

6.Isolated Dependency Installation
With guidance from my mentor (ChatGPT Assistant), I learned to install all required dependencies inside a dedicated Conda environment instead of globally. This ensured that other projects and system Python installations weren’t affected by version conflicts, keeping my setup clean and stable.

## Learning Outcome:-

These challenges helped me understand the importance of managing environments properly, checking library compatibility, and ensuring that GPU acceleration is set up correctly for deep learning tasks. It also taught me to maintain isolated environments for each project to prevent dependency issues and improve reproducibility. Overall, this experience strengthened my understanding of practical system setup and troubleshooting for AI projects.
