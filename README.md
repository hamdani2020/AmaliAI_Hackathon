### **1. Overview**
This application combines object detection and conversational AI to analyze uploaded images and provide meaningful insights. Key features include:
- Object detection using a YOLO model.
- Integration with AmaliAI for conversational capabilities.
- Visualization of detected objects.
- Interactive user interface built with Streamlit.

---

### **2. Dependencies**
The application requires the following Python libraries:
- **Streamlit**: For building the web-based interface.
- **YOLO (Ultralytics)**: For performing object detection on uploaded images.
- **Pillow**: For image manipulation.
- **OpenCV**: For drawing bounding boxes and visualizing detected objects.
- **NumPy**: For handling arrays.
- **Requests**: For making API requests to AmaliAI.
- **Dotenv**: For loading environment variables.
- **Base64**: For encoding images for API requests.

---

### **3. Features**

#### **a. Object Detection**
- **Model Loading**: 
  - The YOLO model is loaded using the `load_yolo_model()` function and cached for performance.
- **Detection**:
  - The `detect_objects(image)` function performs object detection on the uploaded image and returns bounding boxes, confidence scores, and class names.
- **Visualization**:
  - Detected objects are visualized using `visualize_detections(image, detections)`, which draws bounding boxes and labels.

#### **b. Conversational AI Integration**
- Uses the AmaliAI API to interact with users.
- The function `send_amaliai_request()` sends prompts to AmaliAI and receives responses, with support for both streaming and non-streaming modes.

#### **c. Streamlit Interface**
- **File Uploader**:
  - Users can upload images for object detection.
- **Sidebar**:
  - Displays conversation history and allows clearing of history.
  - Provides advanced settings for configuring model IDs and toggling response streaming.
- **Main Content**:
  - Displays detected objects, bounding boxes, and a text input for posing questions related to the image.

---

### **4. Code Structure**

#### **a. Global Variables**
- **Environment Variables**: 
  - `AMALIAI_BASE_URL`, `AMALIAI_API_KEY`, and `DEFAULT_MODEL_ID` are loaded using `dotenv`.
- **Session State**:
  - Manages conversation history, parent message ID, and unique conversation IDs.

#### **b. Key Functions**
- **`load_yolo_model()`**: Loads and caches the YOLO model.
- **`detect_objects(image)`**: Detects objects in an image using YOLO.
- **`visualize_detections(image, detections)`**: Draws bounding boxes and labels on the detected image.
- **`send_amaliai_request()`**: Handles API requests to AmaliAI for generating responses.
- **`display_conversation_history()`**: Displays past conversation messages in the sidebar.

#### **c. Main Function**
- **`main()`**: The entry point for the Streamlit application. It orchestrates the UI components, handles file uploads, and integrates object detection and conversational features.

---

### **5. Usage Instructions**
1. **Setup**:
   - Create a `.env` file with the required environment variables:
     ```
     AMALIAI_BASE_URL=<Your API Base URL>
     AMALIAI_API_KEY=<Your API Key>
     AMALIAI_DEFAULT_MODEL_ID=<Default Model ID>
     ```

2. **Run the Application**:
   - Execute the script using Streamlit:
     ```bash
     streamlit run app.py
     ```

3. **Features**:
   - Upload an image for object detection.
   - View detected objects and ask questions about the image.
   - Explore conversation history in the sidebar.

---

### **6. Key Functionalities**

#### **Object Detection**
- Detects objects and displays bounding boxes with class names and confidence scores.
- Uses YOLO for real-time detection.

#### **Conversational AI**
- Integrates with AmaliAI for interactive discussions about uploaded images.

#### **UI Features**
- File upload, detected object visualization, and a question input for user queries.

---

### **7. Potential Enhancements**
- Add error handling for unsupported image formats.
- Include more pre-trained models for flexibility.
- Enhance conversation history visualization for better readability.
- Improve the object detection results display with additional details like object counts.

This documentation ensures clarity for developers maintaining or extending the functionality of this application.
