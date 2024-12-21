# 📚 Reading Tracker

A modern web application to track your reading progress and goals using Google Sheets as a backend. Track multiple books, set daily reading goals, and monitor your progress with a beautiful, responsive interface.

## ✨ Features

- 📖 Track multiple books simultaneously
- 📊 Visual progress bars for each book
- 🎯 Daily reading goals with progress tracking
- 📱 Responsive design for mobile and desktop
- 🎨 Modern UI with an earthy color palette
- ☁️ Google Sheets integration for data storage

## 🚀 Getting Started

1. Create a copy of the Google Sheet template (coming soon)
2. Deploy the Google Apps Script to your sheet
3. Copy your script URL to `config.js`:
   ```javascript
   const CONFIG = {
       SCRIPT_URL: 'YOUR_GOOGLE_APPS_SCRIPT_URL'
   };
   ```
4. Open `index.html` in your browser or deploy to GitHub Pages

## 💻 Local Development

1. Clone the repository
2. Copy `config.sample.js` to `config.js` and add your Google Apps Script URL
3. Start a local server:
   ```bash
   python3 -m http.server 8000
   ```
4. Open http://localhost:8000 in your browser

## 🎨 Color Palette

The app uses a modern, earthy color scheme:
- Primary: #606C38
- Primary Dark: #283618
- Light: #FEFAE0
- Accent: #DDA15E
- Accent Dark: #BC6C25

## 📱 Screenshots

Coming soon!

## Technologies Used
- HTML/CSS/JavaScript
- Bootstrap 5 for styling
- Google Apps Script for backend
- Google Sheets for data storage
