# MTCNN: 
- MTCNN a deep cascaded multi-task framework - structure 3 stages —> predict face and landmark location


With given image, we initially resize it to different scales to build an image pyramid

- Stage 1(P-Net - Proposal Network):
    - A shallow CNN
    - Obtain the candidate windows and their bounding box regression vectors
    - Use the estimated bounding box regression vectors to calibrate the candidates
    - Employ non-maximum suppression (NMS) to merge highly overlapped candidates
- Stage 2 (R-Net - Refine Network):
    - All candidates are fed to R-Net (CNN)
    - Rejects a large number of false candidates
    - Performs calibration with bounding box regression, and NMS candidate merge
- Stage 3 (O-Net): similar R-Net
    - Refine the result and output facial landmarks positions.
    - Architecture:
        - Input: Image
        - 32-Conv1: 3x3 —> MaxPooling: 3x3
        - 64-Conv2: 3x3 —> MaxPooling 3x3
        - 64-Conv3: 3x3 —> MaxPooling 2x2
        - 128-Conv4: 2x2
        - Fully-connected layer
            - Output: bounding boxes, probability, facial landmarks
