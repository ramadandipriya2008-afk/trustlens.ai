# 🔍 TrustLens AI
### Intelligent Synthetic Media Detection & Digital Content Verification Platform

<p align="center">
  <strong>See Beyond What You See. Verify Before You Trust.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AI-Powered-blueviolet?style=for-the-badge" alt="AI Powered"/>
  <img src="https://img.shields.io/badge/Python-FastAPI-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/React-Frontend-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React"/>
  <img src="https://img.shields.io/badge/Supabase-Database-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white" alt="Supabase"/>
  <img src="https://img.shields.io/badge/Status-Hackathon%20Project-orange?style=for-the-badge" alt="Hackathon Project"/>
</p>

---

## 🌐 Overview

*TrustLens AI* is an AI-powered synthetic media analysis platform designed to help users examine digital images, videos, and audio recordings for potential signs of AI-generated or manipulated content.

With the rapid growth of generative AI, synthetic images, deepfake videos, and AI-generated voices are becoming increasingly difficult to distinguish from authentic media.

TrustLens AI aims to address this challenge by providing an accessible platform that analyzes uploaded media using machine learning models and presents understandable assessment results.

The platform combines a modern web interface, a Python-based AI backend, and a secure database infrastructure to create a unified digital media analysis experience.

> *Our mission:* Make digital media verification more accessible, transparent, and understandable for everyone.

---

## 🚨 The Problem

Generative AI technologies have made it easier than ever to create convincing synthetic media.

This creates several challenges:

- *Misinformation:* AI-generated media can be used to spread misleading information.
- *Identity impersonation:* Synthetic faces and voices can imitate real individuals.
- *Digital fraud:* Manipulated media can be used in scams and fraudulent activities.
- *Trust issues:* Ordinary users often lack the technical knowledge to evaluate suspicious media.
- *Verification barriers:* Many existing detection approaches are difficult for non-technical users to access.

There is a growing need for accessible tools that help users investigate suspicious digital content.

## 💡 Our Solution

TrustLens AI provides a unified interface where users can submit media for AI-assisted analysis.

The system processes supported media through its corresponding analysis pipeline and returns an assessment with model information and relevant analysis details.

### Core capabilities

| Capability | Description |
|---|---|
| 🖼️ Image Analysis | Examines uploaded images using an image classification model. |
| 🎥 Video Analysis | Supports video analysis through a frame-based processing pipeline when a verified video model is configured. |
| 🎙️ Audio Analysis | Provides an audio analysis pipeline for compatible, verified audio models. |
| 📊 Analysis Dashboard | Displays users' previous analysis records. |
| 🔐 User Authentication | Supports account registration and login. |
| 📁 Analysis History | Stores analysis information securely for authenticated users. |
| 📱 Responsive Interface | Provides an accessible experience across desktop and mobile devices. |

---

## ✨ Key Features

### 1. AI-Powered Image Analysis
- Upload images for automated analysis.
- Process images through an EfficientNet-B0-based model.
- Generate a model score and assessment.
- Present results through an understandable interface.

### 2. Video Analysis
- Accept supported video uploads.
- Extract selected frames for analysis.
- Process video content through the configured video-analysis pipeline.
- Present results with appropriate model availability and limitations.

### 3. Audio Analysis
- Provide an audio analysis workflow.
- Support integration with an AASIST-based detection pipeline.
- Use compatible model architecture, preprocessing, and checkpoints.
- Avoid presenting unverified model results as confirmed detections.

### 4. User Dashboard
- View previous analysis records.
- Access analysis information.
- Track activity through a centralized dashboard.

### 5. Secure Authentication
- User registration and login.
- Supabase-powered authentication.
- User-specific data access through Row Level Security (RLS).

### 6. Modern User Experience
- Responsive design.
- Simple media upload workflow.
- Clear analysis result presentation.
- Intuitive navigation and dashboard experience.

---

## 🧠 How TrustLens AI Works

The platform follows a structured processing pipeline.

mermaid
flowchart TD
    A["User Opens TrustLens AI"] --> B["User Authentication"]
    B --> C["Upload Image / Video / Audio"]
    C --> D{"Select Media Type"}
    D --> E["Image Processing"]
    D --> F["Video Frame Extraction"]
    D --> G["Audio Preprocessing"]
    E --> H["Image AI Model"]
    F --> I["Configured Video Analysis Model"]
    G --> J["Verified Audio Model"]
    H --> K["Analysis Result"]
    I --> K
    J --> K
    K --> L["Result Display"]
    L --> M["Save Analysis Record"]
    M --> N["Supabase Database"]
    N --> O["User Dashboard"]


The availability of individual analysis pipelines depends on the corresponding model, checkpoint, and configuration being verified and enabled.

---

## 🏗️ System Architecture

TrustLens AI uses a modular architecture that separates the user interface, AI processing, and database infrastructure.

mermaid
flowchart TB
    U["User"] --> FE["React Frontend"]
    FE --> API["Python FastAPI Backend"]
    FE <--> AUTH["Supabase Authentication"]
    API --> ML["AI / ML Processing"]
    ML --> IMG["EfficientNet-B0 Image Model"]
    ML --> VID["Video Analysis Pipeline"]
    ML --> AUD["AASIST Audio Pipeline"]
    API --> DB["Supabase Database"]
    DB --> DASH["Analysis History"]
    DASH --> FE


### Architecture components

| Layer | Technology | Responsibility |
|---|---|---|
| Frontend | React | User interface and interactions |
| Backend | Python + FastAPI | API endpoints and processing |
| Image AI | EfficientNet-B0 | Image classification |
| Video | Frame-based pipeline | Video frame analysis |
| Audio | AASIST integration | Audio analysis when verified |
| Database | Supabase / PostgreSQL | Analysis records |
| Authentication | Supabase Auth | User account management |
| Hosting | Vercel + Render | Frontend and backend deployment |

---

## 🛠️ Technology Stack

### Frontend
- React
- JavaScript
- HTML5
- CSS3
- Responsive UI components

### Backend
- Python
- FastAPI
- Uvicorn
- REST API architecture

### Artificial Intelligence & Machine Learning
- PyTorch
- EfficientNet-B0
- ONNX Runtime
- OpenCV
- NumPy
- AASIST integration for audio analysis

### Database & Authentication
- Supabase
- PostgreSQL
- Supabase Authentication
- Row Level Security (RLS)

### Development & Deployment
- Git
- GitHub
- Vercel
- Render
- Visual Studio Code / Antigravity

---

## 🧪 AI & ML Methodology

TrustLens AI uses a modular approach to synthetic media analysis.

### Image Detection — EfficientNet-B0

EfficientNet-B0 is used as the image classification architecture.

The image pipeline involves:

1. Receiving the uploaded image.
2. Validating the image format.
3. Preprocessing the image according to model requirements.
4. Running inference using the configured model.
5. Interpreting the model output.
6. Returning the assessment and associated score.

The image model is based on the CIFAKE dataset, which contains real and AI-generated images.

*Important:* Model scores are classification outputs, not guaranteed probabilities that an image is fake. Performance depends on the input distribution and evaluation conditions.

### Video Analysis

The video pipeline is designed around frame-based analysis.

1. Receive the video.
2. Validate the media file.
3. Extract selected frames.
4. Preprocess frames.
5. Run the configured analysis model.
6. Aggregate supported frame-level results.
7. Return an overall assessment.

Video detection requires independent validation. An image classifier does not automatically become a reliable video deepfake detector simply by applying it to video frames.

### Audio Analysis — AASIST

The audio pipeline is designed to support AASIST-based synthetic speech analysis.

Its workflow includes:

1. Audio upload and validation.
2. Audio preprocessing.
3. Feature preparation.
4. Model inference using a compatible implementation and checkpoint.
5. Interpretation of the model output.
6. Returning the analysis result.

Only compatible, verified model configurations should be used for actual inference.

---

## 📂 Project Structure

The repository is organized into separate frontend and backend directories.

text
trustlens-ai/
│
├── frontend/
│   ├── public/
│   ├── src/
│   ├── package.json
│   ├── index.html
│   └── ...
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── services/
│   │   └── ...
│   ├── models/
│   ├── requirements.txt
│   └── serve.py
│
├── .gitignore
└── README.md


The exact files and subdirectories may differ depending on the final implementation.

---

## ⚙️ Installation & Local Setup

### Prerequisites

Make sure you have:

- Python 3.10 or a compatible version supported by your dependencies.
- Node.js and npm.
- Git.
- A Supabase project.
- The required model files and dependencies.

### 1. Clone the repository

bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd trustlens-ai


### 2. Backend Setup

Navigate to the backend directory:

bash
cd backend


Create a Python virtual environment:

bash
python -m venv .venv


Activate it on Windows:

powershell
.venv\Scripts\Activate.ps1


Install dependencies:

bash
pip install -r requirements.txt


Configure the required backend environment variables using the provided .env.example, if available.

Start the backend using the project's configured entry point. For example, if serve.py exposes the FastAPI application:

bash
uvicorn serve:app --host 127.0.0.1 --port 8000


API documentation, when enabled:

text
http://127.0.0.1:8000/docs


### 3. Frontend Setup

Open another terminal:

bash
cd frontend


Install frontend dependencies:

bash
npm install


Create the frontend environment configuration using the variable names required by the application.

Example:

env
VITE_API_BASE_URL=http://127.0.0.1:8000
VITE_SUPABASE_URL=YOUR_SUPABASE_URL
VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_PUBLISHABLE_KEY


Start the frontend:

bash
npm run dev


Open the local development URL shown in the terminal, 
https://trustlensai-beta.vercel.app/


---

## 🔐 Security & Privacy

TrustLens AI follows security-conscious development practices.

- Supabase Authentication manages user authentication.
- Row Level Security protects user-specific analysis records.
- Users should only access records belonging to their authenticated accounts.
- Environment variables are used for configuration.
- Secret keys must never be committed to the GitHub repository.
- Uploaded files should be validated before processing.
- Production API communication should use HTTPS.

*Security note:* Frontend publishable keys are intended for client-side use with appropriate database policies. Supabase service-role keys and other privileged credentials must remain server-side.

---

## ☁️ Deployment Architecture

TrustLens AI separates frontend and backend hosting.

| Component | Deployment Platform |
|---|---|
| Frontend | Vercel |
| Python Backend | Render |
| Authentication | Supabase |
| Database | Supabase PostgreSQL |
| Source Code | GitHub |

### Deployment Workflow

1. Push frontend and backend source code to GitHub.
2. Connect the repository to Render.
3. Configure the backend directory, dependencies, start command, and environment variables.
4. Deploy the Python API.
5. Connect the same repository to Vercel.
6. Configure the frontend root directory and build settings.
7. Set the production API URL in the frontend environment variables.
8. Configure backend CORS to allow the deployed frontend domain.
9. Configure Supabase production authentication URLs.
10. Test the complete application after deployment.

---

## 🎯 Real-World Applications

TrustLens AI is designed around practical digital media verification scenarios.

| Application | Potential Use |
|---|---|
| Digital Journalism | Preliminary examination of suspicious media |
| Social Media | Investigating potentially synthetic content |
| Cybersecurity | Supporting digital threat awareness |
| Education | Teaching media literacy and AI awareness |
| Digital Forensics | Assisting preliminary media examination |
| Personal Safety | Helping users investigate suspicious media |

TrustLens AI is an analysis-support tool, not a replacement for professional forensic examination or independent fact-checking.

---

## 🚀 Future Enhancements

We aim to expand TrustLens AI with additional capabilities:

- Improved detection models trained and evaluated on diverse datasets.
- Stronger video-specific deepfake detection.
- More robust synthetic speech detection.
- Explainable AI and visual analysis indicators.
- Frame-level video analysis reports.
- Advanced audio analysis visualization.
- Model benchmarking and evaluation dashboards.
- Media metadata and provenance analysis.
- Batch media analysis.
- API integrations for third-party platforms.
- Continuous model performance monitoring.
- Improved detection against previously unseen generation methods.

---

## ⚠️ Limitations & Responsible AI

AI-based media detection is an evolving research area.

TrustLens AI results should be interpreted carefully.

- No detection model guarantees 100% accuracy.
- Image classification results may be affected by compression, editing, resizing, and unfamiliar image distributions.
- Video results require validation on representative video datasets.
- Audio results require verified model weights and preprocessing.
- A high or low model score should not be treated as definitive proof of authenticity.
- A detection result alone should not be used to accuse an individual or make high-impact decisions.

*TrustLens AI aims to support informed judgment, not replace it.*

---

## 👥 Team

*Project:* TrustLens AI

*Project Category:* Artificial Intelligence / Machine Learning / Digital Media Security

*Development:* Frontend, Backend, AI/ML Integration, Database & Deployment

| Responsibility | Contributor |
|---|---|
| AI/ML & Python Backend | [Your Name] |
| Frontend Development | [Friend's Name] |
| Research & UI/UX Support | [Contributor Names, if applicable] |

Update the contributor names and roles to accurately reflect each person's contribution.

---

## 🏆 Hackathon Project

TrustLens AI was developed as a solution to the growing challenge of synthetic digital media and the difficulty of identifying potentially manipulated content.

The project demonstrates the integration of:

- Artificial Intelligence and Machine Learning.
- Full-stack web development.
- Python-based model inference.
- Secure authentication and database infrastructure.
- Practical digital media analysis.

Our goal is to make AI-assisted media examination more accessible through a single, user-friendly platform.

---

## 📸 Screenshots & Demo

Add your actual application screenshots here to help visitors understand the platform.

| Application Interface | Description |
|---|---|
| Home / Dashboard | Main application interface |
| Image Analysis | Image upload and analysis |
| Video Analysis | Video analysis interface |
| Audio Analysis | Audio analysis interface |
| Results Page | Analysis results and scores |
| User Dashboard | Previous analysis records |

*Live Demo:* [Add your deployed Vercel URL]

*Backend API:* [Add your deployed Render URL]

*API Documentation:* [Add your deployed API docs URL, if enabled]

---

## 📜 License

This project is developed for educational, research, and hackathon purposes.

Add a suitable open-source license only after confirming that the project's code, datasets, model weights, and dependencies permit the intended redistribution.

---

<p align="center">
  <strong>TrustLens AI</strong><br/>
  <em>See Beyond What You See. Verify Before You Trust.</em>
</p>

<p align="center">
  Built with ❤️ using Artificial Intelligence, Python, and modern web technologies.
</p>
