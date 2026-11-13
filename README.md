# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

  ## Name: Priyadharshini S  
  ### Register No: 212225230218

---

## Output
## Original Image:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread(r"C:\Users\acer\Downloads\butterfli.jpg")

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="417" height="346" alt="image" src="https://github.com/user-attachments/assets/68ceb1f5-2b0c-40a7-8275-0517e5d00b1b" />

### Sobel Edge Detector:
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
## OUTPUT:
<img width="426" height="372" alt="image" src="https://github.com/user-attachments/assets/4881cdf3-26fe-4c35-ba72-0c5487c6ca27" />

### Prewitt Edge Detector:
```
image = cv2.imread("C:\\Users\\manas\\OneDrive\\Desktop\\Manasa\\image.jpg") 

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')
```
## OUTPUT:
<img width="431" height="347" alt="image" src="https://github.com/user-attachments/assets/da9a34e7-0939-4387-bea9-35f15c530e94" />

## Roberts Edge Detector:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread(r"C:\Users\acer\Downloads\butterfli.jpg")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

roberts_x = np.array([[1, 0],
                      [0, -1]], dtype=np.float32)

roberts_y = np.array([[0, 1],
                      [-1, 0]], dtype=np.float32)

gx = cv2.filter2D(gray, cv2.CV_32F, roberts_x)
gy = cv2.filter2D(gray, cv2.CV_32F, roberts_y)

roberts = cv2.magnitude(gx, gy)
roberts = cv2.normalize(roberts, None, 0, 255, cv2.NORM_MINMAX)
roberts = roberts.astype(np.uint8)

plt.imshow(roberts, cmap="gray")
plt.title("Roberts Edge Detection")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="427" height="357" alt="image" src="https://github.com/user-attachments/assets/b6bc2cd5-802e-42d7-800b-946f6f1f30c3" />

### Laplacian Edge Detector:
```
import cv2
import matplotlib.pyplot as plt
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
laplacian_8bit = cv2.convertScaleAbs(laplacian)
plt.imshow(laplacian_8bit, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="432" height="352" alt="image" src="https://github.com/user-attachments/assets/20eb92e1-6f19-4cd6-88a9-6df4122be65a" />

### Canny Edge Detector:
```
import cv2
import matplotlib.pyplot as plt
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="417" height="347" alt="image" src="https://github.com/user-attachments/assets/99c6aafe-5d6c-4371-a42b-ac3cede279b5" />


## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
