# YouTube Mashup Generator

This project implements a complete Mashup system consisting of:

1. Command Line Mashup Program  
2. Web Service Mashup Generator with Email Delivery  

Live Website:  
https://mashup-xwsv.onrender.com/

The system downloads multiple YouTube songs of a given singer, extracts audio, trims them, merges them into a single mashup file, and delivers the final output.

---

# Program 1 – Command Line Mashup

File: `102303872.py`

## Features

- Downloads N videos of a given singer from YouTube
- Converts videos to MP3 audio
- Cuts first Y seconds from each audio
- Merges all trimmed audios into one final mashup file
- Validates user inputs
- Handles exceptions properly

## Usage

```
python 102303872.py <SingerName> <NumberOfVideos> <AudioDuration> <OutputFileName>
```

### Example

```
python 102303872.py "Sharry Maan" 20 20 102303872-output.mp3
```

## Input Constraints

- NumberOfVideos ≥ 10
- AudioDuration ≥ 20 seconds
- Output file must end with `.mp3`
- Correct number of parameters required

If invalid input is provided, appropriate error messages are displayed.

## Required Packages

```
pip install yt-dlp pydub
```

FFmpeg must be installed for audio conversion.

---

# Program 2 – Web Service Mashup Generator

File: `app.py`  
Frontend: `templates/index.html`

Built using Flask and deployed on Render.

Production URL:  
https://mashup-xwsv.onrender.com/

## Features

- User inputs:
  - Singer Name
  - Number of Videos
  - Duration (seconds)
  - Email ID
- Validates integer inputs and email format
- Generates mashup
- Creates ZIP file
- Sends ZIP file via email
- Allows direct download from browser

## Running Locally

### Install Dependencies

```
pip install flask yt-dlp pydub python-dotenv
```

### Configure Email (.env file)

Create a `.env` file:

```
SENDER_EMAIL=your_email@gmail.com
SENDER_PASSWORD=your_app_password
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
```

For Gmail, use an App Password.

### Run Server

```
python app.py
```

Server runs at:

```
http://127.0.0.1:5000
```

---

# Processing Flow

1. Download videos  
2. Convert to MP3  
3. Cut first Y seconds  
4. Merge into single mashup  
5. Create ZIP file  
6. Send email  
7. Provide download link  

---

# Technologies Used

- Python
- Flask
- yt-dlp
- pydub
- SMTP
- FFmpeg
- Render (Cloud Deployment)

---

# Notes

- CLI minimum videos: 10  
- Web minimum videos: 2  
- Minimum duration: 20 seconds  
- Internet connection required  
- FFmpeg required for audio processing  

This project demonstrates YouTube media extraction, audio processing, web service development, file handling, email automation, and cloud deployment.