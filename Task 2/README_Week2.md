# Week 2 _Task_2:– Multi-Image Object Detection and Confidence Tuning using YOLO

##  Objective
To perform object detection on multiple images using YOLO and observe how adjusting confidence thresholds and image quality impacts detection accuracy.

---

## Steps Performed

1. **Imported and Loaded YOLO Model**
   ```python
   from ultralytics import YOLO
   model = YOLO("yolov11n.pt")
   ```

2. **Fetched All Images from the Folder**
   ```python
   import glob
   image_paths = glob.glob("images/*.jpg")
   ```

3. **Predicted Results for Each Image**
   ```python
   for img in image_paths:
       results = model.predict(source=img, conf=0.4)
   ```

4. **Saved Output Predictions**
   - Output directory: `runs/detect/predict/`
   - Each image saved with bounding boxes and labels.

---

##  Output
Example result screenshots:  
- `Task_2\runs\detect\predict2\SD.jpg`  
- `Task_2\runs\detect\predict2\TK.jpg`
---

## Challenges & Improvements

###  1. Fewer Predictions at First
At default confidence (0.5), very few objects were detected.  
**Solution:** Decreased confidence to **0.25**, which increased the number of valid detections.

###  2. Image Quality Issues
Some images were low-resolution, causing poor detection accuracy.  
**Solution:** Replaced them with **higher-resolution images**, which improved bounding box clarity and accuracy.

###  3. Output Folder Confusion
Each YOLO run created new folders like `predict`, `predict2`, etc.  
**Solution:** Cleared or renamed output folders before each run for clean experiment tracking.

---

## Learning Outcome
- Understood the effect of YOLO’s **confidence parameter** on prediction results.  
- Gained experience handling **multiple input images** using Python.  
- Learned to interpret and compare results visually.  
- Improved workflow organization for experiment reproducibility.
---