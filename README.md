🪔 Celebration.ai — Diwali Greeting Web App
🎉 Overview

Celebration.ai is a festive interactive web app that sends personalized Diwali greetings with fireworks animation and a custom video message.
Visitors enter their name, receive a dynamic greeting with sparkling fireworks, and then enjoy a Diwali-themed video — all while their name is automatically saved in a connected Google Sheet for tracking or analytics.

🌟 Features

✅ Name Input + Greeting Flow — User enters their name and gets a personalized Diwali message.
✅ Google Sheets Integration — Automatically saves each visitor’s name with timestamp.
✅ Fireworks Animation — Beautiful animated fireworks (center for mobile, side bursts for wide screens).
✅ Responsive Design — Works perfectly on both mobile and desktop screens.
✅ Video Playback — Plays a festive video (hapy.mp4) full screen with soft edges and glow effect.
✅ Web Counter Integration — Tracks total visitors using a simple hit counter.

🧠 Tech Stack
Technology	Purpose
HTML5	Page structure
CSS3	Styling, responsiveness, and animation layout
JavaScript (Vanilla)	Interactivity, fireworks animation, Google Sheets API integration
Google Apps Script	Backend for saving data to Google Sheets
HitWebCounter	Visitor counter
⚙️ Setup Instructions
1. Clone or Download
git clone https://github.com/yourusername/celebration-ai.git
cd celebration-ai

2. Add Your Video

Place your Diwali video in the same directory and name it:

hapy.mp4

3. Connect Google Sheet

Create a new Google Sheet with columns:

Timestamp | Name


Open Google Apps Script from the Sheet (Extensions → Apps Script).

Paste the following script:

function doPost(e) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const data = JSON.parse(e.postData.contents);
  sheet.appendRow([new Date(), data.name]);
  return ContentService.createTextOutput("Success");
}


Click Deploy → New deployment

Select Web App

Execute as: Me

Who has access: Anyone

Copy the Web App URL

Replace the URL inside your HTML file:

fetch("YOUR_WEB_APP_URL", {
  method: "POST",
  body: JSON.stringify({ name })
})

4. Run Locally

Simply open index.html in your browser or serve it using VS Code Live Server.

📱 User Flow

User opens the greeting page.

Enters their name and clicks OK.

Fireworks appear + personalized Diwali greeting pops up.

After a short delay, fireworks continue at sides, and the video plays in full view.

Name and timestamp are saved in your connected Google Sheet.

🎇 Customization
Element	How to Change
Video	Replace hapy.mp4 with any .mp4 video
Background Image	Update background-image in .container
Fireworks Duration	Modify stopFireworksAfter(ms) in script
Message Text	Edit the alert() text in startGreeting() function
💡 Future Enhancements

🌍 Capture user city/country automatically (via IP geolocation API).

📧 Send automatic email greeting or WhatsApp share link.

🪩 Add background music synced with fireworks.

🖼️ Save screenshot of greeting + name.

🧑‍💻 Author

Ankit — Creative Developer
Project: Diwali Greeting Web Experience
✨ "Spreading light, code, and joy!"
