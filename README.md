# Character Segmentation using OpenCV

This repository contains Python code for character segmentation in images using OpenCV. Character segmentation is a fundamental step in many optical character recognition (OCR) systems and text extraction tasks.

## Usage

The code provided demonstrates character segmentation using edge detection and connected components analysis.

```python
import cv2
import numpy as np

# Load the image
image_path = "/path/to/your/image.png"  # Update with your image path
image = cv2.imread(image_path)
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Apply edge detection
edges = cv2.Canny(gray_image, 50, 150)
dilated_edges = cv2.dilate(edges, kernel, iterations=2)

# Use dilated edges as a mask for segmentation
segmented_image = cv2.bitwise_and(image, image, mask=dilated_edges)

# Display the segmented image
plt.imshow(cv2.cvtColor(segmented_image, cv2.COLOR_BGR2RGB))
plt.title("Segmented Image")
plt.show()
```

Replace `"/path/to/your/image.png"` with the path to your input image.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

--- 

In this README, I've provided a brief overview of the code usage, including only the key features such as loading the image, edge detection, segmentation, and displaying the segmented image. Adjustments can be made to the content based on your preferences and project requirements.
