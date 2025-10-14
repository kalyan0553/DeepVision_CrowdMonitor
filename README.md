**Deep Vision Crowd Monitor👥📷**

This project is called Deep Vision Crowd Monitor.
It uses Deep Learning + Computer Vision to count people in images and videos, and it can also raise alerts when the crowd size is too big.
We divided the project into 5 parts so that you can learn step by step and easily test everything in Google Colab.

**What this project does**

Counts people in images, videos, or live camera feed.
Uses the CSRNet model (a popular crowd counting CNN).
Can raise alerts if too many people are detected in real time.
Includes a Streamlit dashboard so you can upload images and see results in a simple web app.

**🛠️Project Structure**

The code is split into 5 clear parts:
Data Loader → Loads crowd images and density maps.
CSRNet Model → Deep learning model for crowd counting.
Training Scripts → Train CSRNet on your dataset.
Real-time Inference + Alerts → Test on new images/videos/live feed and trigger alerts if crowd is large.
Streamlit Dashboard → A simple web app where you can upload an image and see the predicted crowd count.

**📂 Files inside this repo**

data_loader.py → handles loading the dataset.
model.py → CSRNet model definition.
train.py → training script.
inference.py → for testing & real-time alerts.
app.py → Streamlit app for a nice user interface.
README.md → this file you are reading 🙂

**🖥️ Requirements**

This project is made for Google Colab, so installation is very easy.
But you can also run it on your PC if you have Python installed.

**Core Libraries**

Python 3.x
PyTorch
Torchvision
Numpy
Pillow
OpenCV
Matplotlib
Streamlit
Cloudflared (for Colab to make Streamlit accessible)

**🔧 Setup (Step by Step)**

**Option 1 → Run in Google Colab (Recommended ✅)**

Open the notebook in Colab.
Upload this repo or clone it:

       !git clone https://github.com/your-username/DeepVision_CrowdMonitor.git
       cd DeepVision_CrowdMonitor
       
Run each code cell step by step → starting from Data Loader → CSRNet → Training → Inference → Streamlit.
For the Streamlit dashboard, use Cloudflared to get a public link.

**Option 2 → Run Locally on your PC**

**Clone the repo:**

      git clone https://github.com/your-username/DeepVision_CrowdMonitor.git
      cd DeepVision_CrowdMonitor

**Create a virtual environment (recommended):**

      python -m venv venv
      source venv/bin/activate    # for Linux/Mac
      venv\Scripts\activate       # for Windows

**Install requirements:**

      torch>=1.12.0
      torchvision>=0.13.0
      numpy>=1.21.0
      pillow>=9.0.0
      opencv-python>=4.5.0
      matplotlib>=3.5.0
      streamlit>=1.12.0


**Run training or inference:**

      python train.py
      python inference.py

**Run the dashboard:**

      streamlit run app.py

**⚡ How to Use**

Training → Use train.py with your dataset to train CSRNet.
Testing/Inference → Run inference.py with an image/video to get predictions.
Real-time Alerts → The script checks the crowd size and warns if it’s too high.
Dashboard → Run app.py with Streamlit, upload an image, and get instant results.

**📊 Example Output**

Upload an image of a crowd → see crowd count in seconds.
Use real-time webcam/video → get alerts like "Warning: Too many people detected!".
In the dashboard, you can see both the uploaded image and the estimated number of people.
![img alt](https://github.com/springboardmentor-456/deepvision-crowd/blob/fe87c8a33f54d546729d0b090ca88a81a9eeae01/OUTPUT_Dashboard.png)

**🌟 Why this project is useful?**

Crowd safety monitoring (stadiums, events, public gatherings).
Helps beginners learn Deep Learning, Computer Vision, and Deployment.
Easy step-by-step learning → from data to model to dashboard.

**🙌 Contribution**

This project is built in a simple way so that anyone can understand and extend it.
Feel free to fork it, add improvements, or raise issues!

**👨‍💻 Author**

Project developed by **Kalyan Gugulothu** <br><br><br><br><br><br><br><br><br><br><br><br>













**Crowd Monitor Deep Vision🧑‍🤝‍🧑📊**<br>
**Project Overview:**

This project implements a crowd monitoring system using deep learning and computer vision.
It leverages Convolutional Neural Networks (CNNs) for crowd counting on the ShanghaiTech dataset and integrates:

  **Real-time visualization** with Matplotlib & OpenCV

  **SMS Alerts** via Twilio when crowd thresholds are exceeded

  **Web Deployment using Streamlit + Ngrok** (for public access)

 This solution can be applied in public safety monitoring, event management, and smart city surveillance.

**📂 Dataset**

 **ShanghaiTech Crowd Counting Dataset**

   part_A → dense crowds
   part_B → sparse crowds

 **Directory structure (inside Google Drive):**

    ShanghaiTech/
      ├── part_A/
      │   ├── train_data/
      │   │   ├── images/
      │   │   └── ground_truth/
      │   └── test_data/
      │       ├── images/
      │       └── ground_truth/


 ⚠️ Ensure your dataset is placed in Google Drive and update the image_dir and gt_dir paths inside the notebook.

**🚀 How to Run (Google Colab)**

**1. Open in Google Colab**
 Upload the notebook and mount Google Drive:

    from google.colab import drive
    drive.mount('/content/drive')


**2. Install Dependencies**

    %pip install torch torchvision opencv-python matplotlib pyngrok twilio streamlit


**3. Run DataLoader & Training**

  Loads ShanghaiTech dataset

  Trains CNN model for crowd counting

**4. Run Evaluation**

  Generates density maps

  Shows crowd count predictions

**5. Enable SMS Alerts**
 Configure Twilio credentials:

    account_sid = "YOUR_TWILIO_SID"
    auth_token = "YOUR_TWILIO_AUTH_TOKEN"
    from_ = "+1234567890"   # Twilio number
    to_ = "+919876543210"   # Your phone number (E.164 format)


 The system will send SMS alerts when crowd count > threshold.

**6. Deploy via Streamlit + Ngrok**

    !streamlit run app.py & npx localtunnel --port 8501


  Or in Python:

    from pyngrok import ngrok
    public_url = ngrok.connect(8501)
    print("App URL:", public_url)

**⚙️ Dependencies**

 Python 3.8+
 PyTorch
 Torchvision
 OpenCV
 NumPy, SciPy, Matplotlib
 Streamlit
 Pyngrok
 Twilio

**📱 Features**

 Crowd counting using CNNs
 Real-time density map visualization
 Threshold-based SMS alerts
 Streamlit web interface (with Ngrok for public access)

**📊 Example Output**

 **Input Image** → Crowd scene
 **Predicted Density Map** → Heatmap of people distribution
 **Predicted Count** → Numeric crowd estimate
 **SMS Alert** → "⚠️ Alert: Crowd exceeded safe limit at [Location]. Current count = 152."

**🙌 Credits**

 **Dataset:** ShanghaiTech Crowd Counting Dataset
 **Libraries: PyTorch, OpenCV, Streamlit, Twilio
 Developed as part of **Deep Vision Crowd Monitor Project**

 **🙌 Contribution**

This project is built in a simple way so that anyone can understand and extend it.
Feel free to fork it, add improvements, or raise issues!

**👨‍💻 Author**

Project developed by **Kalyan Gugulothu**
