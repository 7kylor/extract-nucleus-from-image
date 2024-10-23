# Extract Nucleus from Image

This project provides a script to extract the nucleus from an image using OpenCV. It identifies the contours of the nucleus and extracts it from the image.

## Usage

I used the Jupyter notebook to develop and test the idea.
You can run the notebook to see the code in action.

## Requirements

- Python 3.8+
- OpenCV
- NumPy

All of the requirements can be installed using pip:

```bash
pip install -r requirements.txt
```

## using conda

```bash
conda install -c conda-forge opencv
```

```bash
cd /path/to/your/project
python3 -m venv venv
source venv/bin/activate  # For macOS/Linux
# venv\Scripts\activate    # For Windows
pip install --upgrade pip
pip install opencv-python numpy
python -c "import cv2; print(cv2.__version__)"
python -c "import numpy; print(numpy.__version__)"
```

## Enhanced Nucleus Extraction

The `extract_nuclei` function has been refined to improve the detection and segmentation of nuclei in histopathology images. The enhancements ensure that only clear, non-empty nuclei with defined characteristics are extracted and saved.

### Features

- **Color-Based Segmentation**: Utilizes HSV color space to accurately isolate dark violet nuclei.
- **Noise Reduction**: Applies morphological operations to clean the mask.
- **Contour Filtering**: Filters out irrelevant contours based on area and circularity to ensure only valid nuclei are processed.
- **Validation Checks**: Ensures that extracted images are non-empty and meet size requirements.
- **Detailed Logging**: Provides informative logs for successful operations and skipped contours.

### NOTE

- The results of the `notebook-hexa.ipynb` file output is "/extracted-nuclei"
- the output of the `notebook.ipynb` file is "/extracted-cells"
- With that said, the hexa processing is far better hence it targets the dark violet by targeting a the lowe and upper bound of the color
