# IMPLEMENTATION-OF-OPENING-AND-CLOSING
### NAME: SHARVESHWARAN M
### REG.NO: 212224240150
# Aim
To implement Opening and Closing morphological operations on an image using OpenCV in Python and display the output results.
# Algorithm
1. Import Libraries: Import OpenCV (cv2), NumPy (numpy), and Matplotlib (matplotlib.pyplot).
2. Create Input Image: Initialize a black image of size $500 \times 500$ with 3 color channels. Render the text "Open and Close" onto the image using cv2.putText().
3. Define Kernel: Create a $3 \times 3$ rectangular structuring element (kernel) consisting of all ones (np.ones((3, 3), np.uint8)).
4. Apply Opening Operation: Perform erosion followed by dilation using cv2.morphologyEx() with cv2.MORPH_OPEN. Convert the image from BGR to RGB and display it using Matplotlib.
5. Apply Closing Operation: Perform dilation followed by erosion using cv2.morphologyEx() with cv2.MORPH_CLOSE. Convert the image from BGR to RGB and display it using Matplotlib.
# Program
```
import cv2
import matplotlib.pyplot as plt
import numpy as np

# 1. Create a blank black image
image = np.zeros((600, 600, 3), dtype=np.uint8)

# 2. Add text on the image
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(
    image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA
)

# 3. Create a 3x3 structuring element (kernel)
kernel = np.ones((3, 3), np.uint8)

# 4. Perform Opening Operation (Erosion followed by Dilation)
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# 5. Perform Closing Operation (Dilation followed by Erosion)
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# 6. Display Results
plt.figure(figsize=(12, 4))

# Input Image
plt.subplot(1, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis("off")

# Opening Operation
plt.subplot(1, 3, 2)
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))
plt.title("Opening Operation")
plt.axis("off")

# Closing Operation
plt.subplot(1, 3, 3)
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()
```
# Output
<img width="987" height="875" alt="image" src="https://github.com/user-attachments/assets/5703dc06-2091-4fbf-bb85-82b202d853ae" />
<img width="1503" height="773" alt="image" src="https://github.com/user-attachments/assets/52487266-2d4d-46fc-baef-1187e10eebd4" />
<img width="1512" height="756" alt="image" src="https://github.com/user-attachments/assets/ada7b148-5987-412e-975e-f5bf4c6baf44" />
<img width="1507" height="757" alt="image" src="https://github.com/user-attachments/assets/e46c2215-11fb-4d00-b242-a2e45fcbf92a" />


# Result
The program for Opening and Closing morphological operations was successfully executed using OpenCV, and the resulting processed images were displayed.
