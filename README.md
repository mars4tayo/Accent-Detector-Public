# Accent Detector


https://github.com/user-attachments/assets/3722924d-5c75-4211-b7c5-21cdf96ff7ad


A web application that analyzes video or audio content to detect English accents using AI/ML techniques.

## Features

- 🎤 Accent detection for English speech
- 🎥 Support for video and audio files
- 🌐 YouTube and direct media URL support
- 📝 Speech transcription using OpenAI Whisper
- 🎯 Confidence scoring for predictions
- 🌍 Supports American, British, Australian, and Canadian accents

## Local Development

### Prerequisites

- Python 3.9+
- FFmpeg (for audio extraction)

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd accent-detector
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the application:
```bash
python app.py
```

5. Open your browser and navigate to `http://localhost:5000`

## Deployment on Render

1. Push your code to GitHub
2. Connect your GitHub repository to Render
3. Create a new Web Service
4. Use the following settings:
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn --bind 0.0.0.0:$PORT app:app --timeout 300 --workers 1`
   - **Python Version**: 3.9.16

## Usage

1. Enter a YouTube URL or direct media link
2. Click "Analyze Accent"
3. Wait for the analysis to complete
4. View the results including:
   - Detected accent
   - Confidence score
   - Speech transcript
   - Analysis summary

## Technical Details

- **Backend**: Flask web framework
- **AI Models**: OpenAI Whisper for transcription, scikit-learn for classification
- **Audio Processing**: librosa, soundfile
- **Media Download**: yt-dlp
- **Frontend**: HTML/CSS/JavaScript

## Limitations

- Currently uses a mock classifier for demonstration
- Requires clear English speech for best results
- Processing time depends on media length
- Some YouTube videos may be restricted

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License
```

## 2. Now let's set up the GitHub repository:

```bash
git init
```

```bash
git add .
```

```bash
git commit -m "Initial commit: Accent detector web application"
```

```bash
git branch -M main
```

```bash
git remote add origin https://github.com/yourusername/accent-detector.git
```

```bash
git push -u origin main
```

## 3. Deploy to Render:

1. **Create a Render account** at https://render.com
2. **Connect your GitHub repository**:
   - Go to Render Dashboard
   - Click "New +" → "Web Service"
   - Connect your GitHub account
   - Select your `accent-detector` repository

3. **Configure the deployment**:
   - **Name**: `accent-detector`
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn --bind 0.0.0.0:$PORT app:app --timeout 300 --workers 1`
   - **Instance Type**: Choose based on your needs (Free tier available)

4. **Environment Variables** (if needed):
   - You can add any environment variables in the Render dashboard

5. **Deploy**: Click "Create Web Service"

## Important Notes:

1. **Memory Requirements**: The Whisper model and audio processing require significant memory. You may need to upgrade from the free tier for better performance.

2. **Timeout Settings**: Audio processing can take time, so I've set longer timeouts (300 seconds).

3. **FFmpeg**: The Dockerfile includes FFmpeg installation for audio processing.

4. **File Structure**: Make sure your project structure looks like this:
   ```
   accent-detector/
   ├── app.py
   ├── requirements.txt
   ├── Dockerfile
   ├── render.yaml
   ├── .gitignore
   ├── README.md
   └── templates/
       └── index.html
