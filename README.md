# Reading Progress Tracker

A simple, serverless web application that helps you track your reading progress using Google Sheets as a backend.

## Features
- Track books and reading goals
- Log daily reading progress
- Calculate if you're on track with your reading goals
- View reading statistics and progress
- Responsive design that works on both desktop and mobile
- Beautiful, modern UI with an earthy color scheme

## Setup

1. Create a new Google Sheet with two tabs:

**Tab 1: Books**
| Book Title | Total Pages | Finish Date | Daily Goal | Start Date | Today Target Page |
|------------|-------------|-------------|------------|------------|-------------------|
| Example    | 300        | 2024-02-01  | =ROUNDUP(B2/(C2-TODAY()),0) | =TODAY() | =ROUNDUP((TODAY()-E2)*D2,0) |

**Tab 2: Progress**
| Book Title | Date | Pages Read |
|------------|------|------------|
| Example    | 2024-01-01 | 50 |

2. Set up Google Apps Script:
   - In your Google Sheet, go to Extensions > Apps Script
   - Create a new script and paste the following code:
   ```javascript
   function doGet(e) {
     const action = e.parameter.action;
     const sheet = e.parameter.sheet;
     
     if (action === 'fetch') {
       const data = SpreadsheetApp.getActiveSpreadsheet()
         .getSheetByName(sheet)
         .getDataRange()
         .getValues();
       return ContentService.createTextOutput(JSON.stringify({
         success: true,
         data: data
       })).setMimeType(ContentService.MimeType.JSON);
     }
     
     if (action === 'append') {
       const data = JSON.parse(e.parameter.data);
       SpreadsheetApp.getActiveSpreadsheet()
         .getSheetByName(sheet)
         .appendRow(data);
       return ContentService.createTextOutput(JSON.stringify({
         success: true
       })).setMimeType(ContentService.MimeType.JSON);
     }
   }
   ```
   - Deploy as a web app:
     - Click "Deploy" > "New deployment"
     - Choose "Web app"
     - Set "Execute as" to "Me"
     - Set "Who has access" to "Anyone"
     - Click "Deploy"
     - Copy the web app URL

3. Update the app:
   - Open `index.html`
   - Replace the `SCRIPT_URL` value with your Google Apps Script web app URL

## Usage

Simply open `index.html` in your web browser. No server required!

The app will:
- Show your reading statistics
- Display your book list with progress bars
- Allow you to log your reading progress
- Calculate if you're on track with your reading goals
- Show your recent reading history

## Technologies Used
- HTML/CSS/JavaScript
- Bootstrap 5 for styling
- Google Apps Script for backend
- Google Sheets for data storage
