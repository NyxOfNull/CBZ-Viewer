# 🖼️ CBZ Folder Viewer (Long Strip Mode)

A self-contained, single-file HTML application designed to view Comic Book Zip archives (`.cbz`) as a continuous, vertically scrolling "long strip" format, ideal for webtoons or sequential comic viewing.

This viewer is designed to work **offline** and allows you to load an entire folder containing multiple CBZ/CBR files for easy, sequential reading.

---

## ✨ Features

- **Single-File Application:** Runs entirely from one `index.html` file (plus two required dependency files).  
- **Long Strip View:** Displays all comic pages vertically in a single column for seamless scrolling.  
- **Folder Support:** Load an entire folder containing dozens of CBZ files, allowing you to jump between them using the navigation controls.  
- **Integrated CBZ Navigation:** Easily switch to the previous or next CBZ file in the loaded folder, or select a specific one from the dropdown menu.  
- **Full-Page Zoom:** Dynamically zoom the entire comic strip in and out while preserving smooth scrolling behavior.  
- **Offline Ready:** After initial setup, the viewer requires no internet connection.  

---

## 🚀 Getting Started (Offline Setup)

Because this application uses utility classes for styling, it requires the **Tailwind CSS framework**. To ensure it works without an internet connection, you need to provide the CSS file locally.

### 1. Download the Dependencies

This project relies on three key files to function:

- `index.html` (The main application code)  
- `jszip.min.js` (Library for reading the `.cbz` zip archives)  
- `tailwind.min.css` (The full, compiled CSS framework)  

**Action Required:**  
You must manually download the full, minified version of the Tailwind CSS stylesheet and JSZip, and place them into their respective folders.

**Download Tailwind CSS:** Copy the content of a stable Tailwind CSS CDN link (e.g., Tailwind v2.2.19 CDN) or a similar static link.

**Organize Folders & Files:**

1. Create a subfolder named `CSS`.  
2. Save the Tailwind content into a new file named `tailwind.min.css` inside the `CSS` folder.  
3. Create a subfolder named `JS`.  
4. Place the `jszip.min.js` file inside the `JS` folder.  

Your final directory structure should look like this:

<pre> ``` 
  /Your-Project-Folder 
  ├── index.html 
  ├── CSS 
  │   └── tailwind.min.css
  └── JS 
      └── jszip.min.js ``` </pre>


### 2. Run the Viewer

Simply **double-click the `index.html`** file to open the application in your web browser (Chrome or Firefox are recommended).

---

## 📖 Usage Instructions

### Loading Your Comics

1. Click the **"Select Folder Containing CBZ Files"** button.  
2. In the file explorer dialog, navigate to and select the folder that contains your `.cbz` and/or `.cbr` files.  
3. The application will automatically read the folder contents, sort the files, and load the first detected comic book.  

### Navigation

The application uses the file structure of your selected folder for navigation:

- **Chapter Dropdown (Top & Bottom):** Use the dropdown menu to quickly switch to any other CBZ file in the folder by name.  
- **"PREV CBZ" / "NEXT CBZ" Buttons:** Use these buttons at the bottom to sequentially move between the loaded comic archives.  

### Zoom Controls

- Use the **+** and **-** buttons located in the bottom-left corner to adjust the zoom level of the entire long-strip view.  
- The application automatically adjusts the scrolling area to match the scaled content, ensuring smooth, natural page scrolling.

---

## ⚙️ Technical Details

| Dependency   | Purpose                                                                                          | Source Location         |
|-------------|--------------------------------------------------------------------------------------------------|------------------------|
| Tailwind CSS | Styling and responsive design utilities.                                                        | Local: CSS/tailwind.min.css |
| JSZip       | Decompressing and reading the contents of `.cbz` (zip) archives.                                | Local: JS/jszip.min.js |
| CBZ Support | Files are read from the local file system using the experimental `webkitdirectory` attribute on the file input. | N/A                    |
| CBR Support | Currently, `.cbr` (RAR) files are recognized but require the underlying JSZip library to support RAR format, which it generally does not natively. They are filtered alongside `.cbz` but may not load correctly without a custom RAR decompressor. | N/A                    |
