## Gesture Detection with OpenCV (SIFT)

This project implements a gesture detection system in a video based on a reference gesture video using OpenCV and SIFT features.

**Features:**

* Detects gestures in real-time video based on a pre-recorded reference video.
* Uses SIFT (Scale-Invariant Feature Transform) for robust feature extraction.
* Applies image pre-processing techniques to enhance features.
* Visualizes the detected video with a green "DETECTED" text overlay.

**Requirements:**

* Python 3.x
* OpenCV library (install using `pip install opencv-python`)

**Running the Script:**

1. Save the script as `gesture_detection.py`.
2. Place your reference gesture video (`train_gesture.mp4`) and the test video (`skip_test2.mp4`) in the same directory as the script.
3. Run the script from the command line: `python gesture_detection.py`

**Explanation:**

The script consists of two main functions:

1. `preprocess_frame(frame)`: This function preprocesses a video frame by converting it to grayscale, applying Gaussian blur for noise reduction, and thresholding to enhance edges.
2. `detect_gesture(video_path, reference_path, threshold=0.1345)`: This function takes the paths to the test video and reference video as input. It performs the following steps:
    * Loads the reference video and extracts SIFT features.
    * Opens the test video and processes each frame:
        * Preprocesses the frame.
        * Extracts SIFT features from the preprocessed frame.
        * Performs matching between features in the reference and test frame using a Brute-force matcher.
        * Checks if the number of good matches exceeds a threshold percentage of features in the reference video. If so, it sets a flag indicating a gesture is detected.
        * Overlays a green "DETECTED" text on the frame if a gesture is detected.
    * Displays the video with a delay and allows exiting with the 'q' key.

**Example Usage:**

The script includes an example usage at the bottom that demonstrates how to call the `detect_gesture` function with specific video paths. You can modify these paths to use your own videos.

**Note:**

* This is a basic implementation and may require adjustments depending on your specific videos and lighting conditions.
* The threshold values 0.1345 was found to be good for this particular test case
