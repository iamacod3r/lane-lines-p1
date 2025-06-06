# Lane Detection Project Setup Guide

This project implements lane line detection for self-driving cars using computer vision techniques including color selection, region of interest selection, grayscaling, Gaussian smoothing, Canny Edge Detection, and Hough Transform line detection.

## Prerequisites

- Python 3.11 or higher
- Git (for cloning the repository)

## Setup Options

### Option 1: Using pip (Recommended)

1. **Clone the repository** (if not already done):
   ```bash
   git clone git@github.com:iamacod3r/lane-lines-p1.git
   cd lane-lines-p1
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv self-driving-env
   ```

3. **Activate the virtual environment**:
   - On Linux/macOS:
     ```bash
     source self-driving-env/bin/activate
     ```
   - On Windows:
     ```bash
     self-driving-env\Scripts\activate
     ```

4. **Install dependencies**:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

### Option 2: Using conda

1. **Create conda environment from file**:
   ```bash
   conda env create -f environment.yml
   ```

2. **Activate the environment**:
   ```bash
   conda activate lane-detection
   ```

## Running the Project

1. **Start Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

2. **Open the main notebook**:
   - Navigate to `P1.ipynb` in the Jupyter interface
   - Click to open the notebook

3. **Run the cells**:
   - Execute cells sequentially using Shift+Enter
   - Or run all cells: Cell → Run All

## Project Structure

```
lane-lines-p1/
├── P1.ipynb                 # Main Jupyter notebook
├── test_images/             # Test images for lane detection
├── test_videos/             # Test videos for processing
├── examples/                # Example outputs
├── writeup.md              # Project writeup
├── requirements.txt        # Python dependencies
├── environment.yml         # Conda environment file
├── SETUP.md               # This setup guide
└── README.md              # Project README
```

## Key Dependencies

- **OpenCV**: Computer vision operations (edge detection, line detection)
- **NumPy**: Numerical computations and array operations
- **Matplotlib**: Plotting and image visualization
- **MoviePy**: Video processing capabilities
- **Jupyter**: Interactive notebook environment

## Troubleshooting

### Common Issues

1. **OpenCV installation issues**:
   ```bash
   pip uninstall opencv-python opencv-contrib-python
   pip install opencv-python opencv-contrib-python
   ```

2. **MoviePy ffmpeg issues**:
   ```bash
   pip install imageio-ffmpeg
   ```

3. **Jupyter kernel issues**:
   ```bash
   python -m ipykernel install --user --name=lane-detection
   ```

### System-specific Notes

- **Linux**: You may need to install system packages:
  ```bash
  sudo apt-get update
  sudo apt-get install python3-dev python3-pip
  
  # For OpenCV (choose based on your Ubuntu version):
  # Ubuntu 20.04+ (newer versions):
  sudo apt-get install libgl1-mesa-dev libglib2.0-0
  
  # Alternative if above doesn't work:
  sudo apt-get install libgl1 libglib2.0-0
  
  # For older Ubuntu versions (18.04 and earlier):
  # sudo apt-get install libgl1-mesa-glx
  
  # Additional packages that might be needed:
  sudo apt-get install libgtk-3-dev libavcodec-dev libavformat-dev libswscale-dev
  sudo apt-get install libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
  sudo apt-get install libpng-dev libjpeg-dev libopenexr-dev libtiff-dev libwebp-dev
  ```

- **macOS**: Install Xcode command line tools:
  ```bash
  xcode-select --install
  ```

- **Windows**: Ensure Visual C++ Build Tools are installed

## Testing the Setup

To verify your environment is set up correctly:

1. Open a Python terminal or Jupyter cell
2. Run this test:
   ```python
   import cv2
   import numpy as np
   import matplotlib.pyplot as plt
   from moviepy.editor import VideoFileClip
   
   print("✅ All imports successful!")
   print(f"OpenCV version: {cv2.__version__}")
   print(f"NumPy version: {np.__version__}")
   ```

## Project Goals

This project focuses on:
- **Color Selection**: Identifying lane lines using color thresholds
- **Region of Interest**: Masking relevant areas of the image
- **Edge Detection**: Using Canny edge detection to find edges
- **Line Detection**: Using Hough Transform to detect lane lines
- **Video Processing**: Applying the pipeline to video streams

## Next Steps

1. Review the notebook cells to understand the pipeline
2. Experiment with different parameter values
3. Test on your own images/videos
4. Complete the project writeup

For more details, refer to the main README.md and the project notebook P1.ipynb. 