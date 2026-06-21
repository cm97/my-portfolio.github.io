# 📁 About-Me Portfolio Page & Image Uploader

A lightweight, single-page portfolio sub-page designed to be hosted on GitHub Pages. It features a completely serverless, client-side profile picture uploader.

## 🚀 Features
* **Zero Backend Required:** Uses the HTML5 **FileReader API** to process image uploads locally in the browser.
* **Persistent Sessions:** Saves your chosen profile picture to **`localStorage`**, keeping it saved even if you refresh or close the page.
* **Fully Themeable:** Built with CSS Custom Properties (variables) for instant color and style changes.
* **Responsive Layout:** Clean, modern card UI optimized for both desktop and mobile screens.

## 🛠️ Built With
* HTML5
* CSS3 (Flexbox & Custom Variables)
* JavaScript (Vanilla ES6)

## ⚙️ How It Works
Because GitHub Pages handles static hosting, it cannot accept traditional file uploads to a server. 
1. When a file is selected, JavaScript converts the image into a **Base64 Data URL string**.
2. This string is stored directly in your browser's local database.
3. Upon page load, the script retrieves the string and updates the profile image source instantly.

## 🎨 Quick Customization
* **Edit Bio:** Open `index.html` and update the text within the `<h1>` and `<p>` tags.
* **Change Theme:** Modify the `--primary-color` hex value inside the `:root` block in the CSS.
* **Make Live Globally:** To lock in an image for all public visitors, upload your photo to GitHub and update the `<img>` tag `src` attribute to point directly to your file path (e.g., `src="profile.jpg"`).
