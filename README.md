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

