# Object_Detection_Project

This project is an object detection application built using Streamlit, OpenCV, and MediaPipe.

## Installation

To install the required dependencies, run:

```sh
pip install mediapipe opencv-python-headless streamlit
```
## Usage
Open the Jupyter notebook Object_Detection_Application.ipynb.
Run the cells to start the Streamlit application.
Upload an image to detect objects.

## Code Explanation
Image Upload and Processing
The uploaded image is read and processed using OpenCV:
```sh
file_bytes = np.asarray(bytearray(uploaded_image.read()), dtype=np.uint8)
img = cv2.imdecode(file_bytes, 1)
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
st.image(img, 'Uploaded Image', use_column_width=True)
```

## Object Detection
The image is then passed to MediaPipe for object detection:
```sh
mp_image = mp.Image(image_format=mp.ImageFormat.SRGB, data=img)
detection_result = detector.detect(mp_image)
```

## Visualization
The detection results are visualized on the image:

```sh
annotated_image = visualize(img, detection_result)
st.image(annotated_image, use_column_width=True)
```

## Contributing
Feel free to open issues or submit pull requests if you have any improvements or bug fixes.

## License
This project is licensed under the MIT License.