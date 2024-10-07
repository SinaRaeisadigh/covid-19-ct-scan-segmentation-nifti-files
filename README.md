# covid-19-ct-scan-segmentation-nifti-files

This code implements a pipeline for segmenting infection regions in CT scans using a U-Net model. 

### Steps:
1. **Libraries and Dataset Path**: Necessary libraries like nibabel (for NIfTI files), OpenCV, TensorFlow, and sklearn are imported. The dataset path is defined.
   
2. **Data Loading and Visualization**:
   - Loads a sample `.nii` CT scan file, processes it into a NumPy array, and visualizes the 100th slice.
   
3. **Preprocessing**:
   - Normalizes CT scans and resizes them to a target shape (128x128).
   - Scans and masks are loaded and preprocessed using the `load_data` function.

4. **Data Splitting**: The dataset is split into training and testing sets using `train_test_split`.

5. **U-Net Model**:
   - A simple U-Net is built with downsampling (conv/max-pooling), a bottleneck, and upsampling layers for segmentation.
   - The model is compiled with binary cross-entropy loss and Adam optimizer.

6. **Training**: The model is trained for 10 epochs using the training set with 10% validation.

7. **Evaluation**: The model's performance is evaluated on the test set.

8. **Visualization**: Predicted masks are visualized alongside the original CT scans and ground truth masks for 5 samples with non-black masks.

