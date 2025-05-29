
# AutoStitch

## 1. Introduction

AutoStitch is a tool primarily designed for storing and organizing newspaper articles. It is a WYSIWYG (What You See Is What You Get) tool that allows you to 'scrapbook' articles by placing them on a customizable background.

Whether you’re dealing with images that are too large, too small, or simply not in the right format, AutoStitch offers a highly customizable solution for stitching, annotating, and fine-tuning your articles to your exact specifications. AutoStitch runs on most standard web browsers. Along with any “snippet” tool like Windows Snipping Tool, you’re good to go.

## 2. Download the Tool… or Not.

### Option 1: From the GitHub Releases Page (Recommended)

Download the latest version of `AutoStitch.htm` from the [Releases page](https://github.com/2rude/Autostitch/releases), then open it in your web browser.

### Option 2: Clone the Repository Manually

```bash
git clone https://github.com/2rude/Autostitch.git
```

Then open the `AutoStitch.htm` file locally in your browser.

---

## 3. Getting Started

### Step 1: Open the Tool
Open the tool in a separate browser tab or window (window recommended for ease of alt-tabbing). It will load and be waiting for an image.

### Step 2: Set Up the Zoom Level
On your other browser window, open your archive and use its built-in tools to zoom until the article is the size you want. AutoStitch will handle an article of nearly any width as long as you can see it. **Start at the top of the article.**

### Step 3: Open Snipping Tool
Use Windows + Shift + S or type "Snipping Tool" in the search bar. Once open, the tool automatically enters "snip" mode. Move it out of the way if needed.

---

## 4. Taking Screenshots

### Step 4: Capture Your First Image
Click and drag to highlight the top of the article. You **must start at the top** and work down. Grab a little extra above and to the sides, especially if the article is slanted.

### Step 5: Paste the Screenshot into AutoStitch
Use Alt-Tab to switch to AutoStitch, then press `Ctrl + V` to paste. The image should appear with a red dotted outline near the bottom — this is your guide. Align the top of your next snippet with this area.

---

## 5. Stitching Images Together

### Step 6: Add the Next Image
Alt-Tab back to the archive, scroll so you can see the guide line, snip again, and paste into AutoStitch. Always match the top of the snippet to the previous guide.

### Step 7: AutoStitching
AutoStitch will stitch the images and give you a new guide. Keep repeating until the article is complete. When you're done, click the **Done** button.

---

## 6. Rotation and Cropping

### Step 8: Crop and Rotate the Image
The dark blue area is the crop area. Crop and rotation are done together. Use the rotation buttons for 1°, 0.1°, or 0.01° increments. Click and drag crop lines to adjust.

### Step 9: Finalize the Crop and Rotation
Continue adjusting until only the article remains. Then click **Done**.

---

## 7. Border and Annotation

### Step 10: Adjust Padding and Color
You can change border size, background color, and text color. If you always change these settings, see the [Customization](#11-customization-optional) section.

---

## 8. Annotation

### Step 11: Add Annotation
Select the number of lines (1–5). Each line has its own text box and formatting options. **Autofit** resizes the font to fit the image width.

> ⚠️ Autofit must be **unchecked** to use font size buttons.

As you type and format, you'll see changes in real-time. Click **Done** when finished.

---

## 9. Finalizing and Downloading the Image

### Step 12: Download the Image
Give the image a name (optional), then click **JPG** or **PNG**. File size estimates are shown. You can also right-click the image and choose **Save As**.

Want to start over? Click the **George** button or reload the page.

---

## 10. Troubleshooting

- **I can’t paste an image.**  
  Make sure the AutoStitch window is focused. Click the large gray area, then press `Ctrl + V`.

- **It failed to stitch.**  
  If stitching fails, you'll see both images shown vertically. If the guide and cut line don’t match, redo the snippet. If they *do* match, reload AutoStitch — sometimes JS acts up.

- **Autofit isn’t working.**  
  Autofit works best with **Courier New**. For other fonts, disable Autofit and adjust font size manually.

---

## 11. Customization (Optional)

> 🛠️ *Customization settings begin around line **1080** in `AutoStitch.htm`.*
> 
If you use AutoStitch often, you may want to customize the defaults by editing `AutoStitch.htm` in a **plain text editor** (not Word!).

### Border Size
```js
let borderSize = 25;       // Default
const borderSizeMin = 0;
const borderSizeMax = 50;
const borderSizeInc = 5;
```
To use `12px` instead of `25px`:
```js
let borderSize = 12;
const borderSizeMin = 0;
const borderSizeMax = 24;
const borderSizeInc = 6;
```

### Colors
```js
let imageBgColor = "#000000";       // Black background
let textAppendColor = "#FFFFFF";    // White text
```
Change to any valid CSS color: `#000`, `pink`, `rgb(8, 43, 233)`, etc.

### Fonts
```js
const standardFonts = [
  "Arial", 
  "Times New Roman", 
  "Courier New", 
  "Verdana", 
  "Georgia", 
  "Trebuchet MS", 
  "Tahoma"
];
```
Add other safe fonts like `"Impact"`, `"Comic Sans MS"`, etc. Be careful with commas — no trailing comma after the last item.

### Custom Fonts
```js
// const customFontPath = "path/to/coolfont.ttf";
// const customFontName = "Cool Font";
```
Uncomment and adjust the path. If the font file is in the same folder as `AutoStitch.htm`, just use `"coolfont.ttf"`.

Set a default font like this:
```js
let selectedFont = "Courier New";
```
Change to `"Comic Sans MS"`, `"Cool Font"`, etc. Note: **Autofit works best with Courier New**.
