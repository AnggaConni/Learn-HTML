# 🚀 Notepad Modernizer: Legacy to Layout

Notepad Modernizer is a single-file coding simulation educational game designed to guide beginners and legacy-era developers in transitioning from old-school design mindsets (like using <table> and <center>) to Modern Web Design standards.

Learning web development has never been this fun! With a retro, hacker-vibes terminal aesthetic, you will be guided to build a modern Landing Page step-by-step.

✨ Key Features

🎮 90 Interactive Levels: A complete curriculum from basic HTML structure to advanced CSS Animations.

🧠 Dual Mode Learning:

Choice Mode (Build): Learn to choose the correct modern HTML logic and structure (Code will be injected automatically).

Sandbox Mode (Edit): A free-form creative area to modify CSS, colors, text, and layout as you wish.

👁️ Real-time Live Preview: A split-screen display showing your code results instantly (similar to CodePen).

💾 Export to HTML: Download your work at any level as a complete .html file that can be opened in a local browser.

🌐 Bilingual Support: Supports English and Indonesian, switchable at any time.

⚡ Zero Setup: Everything runs on a single HTML file. No server, database, or NPM installation required!

📚 Curriculum (90 Levels)

This game is divided into 6 main Chapters simulating real-world website creation processes:

Chapter 1: Basic Structure (Levels 1-12)
Container structure, header creation, flexbox navigation integration, hero banner, initial grid layout, and footer.

Chapter 2: Forms & Input (Levels 13-25)
Modern Contact Form creation, input styling, labels, interactive buttons, text areas, and custom form validation.

Chapter 3: CSS Variables & Themes (Levels 26-40)
Introduction to CSS Custom Properties (:root), color systems, typography scales, and Dark Mode implementation.

Chapter 4: Advanced Grid Layouts (Levels 41-60)
Deep dive into grid-area, Bento Grids, asymmetrical layouts, Holy Grail Pattern, and digital magazine-style layouts.

Chapter 5: Responsive Design (Levels 61-80)
Implementation of Media Queries, Mobile-First approach, font responsiveness (viewport units), and adaptable designs.

Chapter 6: Animations & Polish (Levels 81-90)
Use of transitions, keyframes animations, modern hover effects, fade transitions, and loading indicators.

🛠️ Internal Tech Stack

Although distributed as a single .html file, under the hood, this game uses:

React 18 (via CDN) for state management and level progression.

Babel (via CDN) for in-browser JSX compilation.

Tailwind CSS (via CDN) for styling the Terminal UI.

Iframe Sandboxing for a secure Live Preview area.

🤝 Contributing

Very open to contributions! If you want to add levels, improve translations, or fix bugs, please create a Pull Request. An internal guide for future developers (or AI) has been embedded in the hidden __AI_DEVELOPER_ROADMAP__ object within the source code.

Built for the Notepad generation who wants to keep growing and stay relevant with modern web technologies. 💻✨


# NP_MODERNIZER - Save & Load Feature Guide

## 🎮 New Features Added!

### 💾 SAVE/EXPORT Button
- **What it does**: Exports your website HTML with embedded progress data
- **Filename format**: `my-website-level-XX.html` (XX = current level number)
- **Special feature**: The exported file contains a hidden HTML comment with your:
  - Current level (levelIdx)
  - Selected language (lang)
  - Complete code state

### 📂 LOAD Button  
- **What it does**: Loads a previously saved HTML file and restores your progress
- **How to use**: 
  1. Click the purple "MUAT/LOAD" button
  2. Select an HTML file you previously exported
  3. Your level, language, and code will be instantly restored!

### ❓ HELP Button
- **What it does**: Shows detailed instructions about save/load functionality
- **Access**: Click the "?" button in the top navigation
- **Languages**: Instructions available in both English and Indonesian

## 🔧 How It Works (Technical)

### During Export:
```javascript
// Save data is embedded as an HTML comment at the end of file
<!-- NP_MOD_SAVE_DATA: {"levelIdx": 25, "lang": "id", "code": "..."} -->
```

### During Load:
```javascript
// RegEx extracts the save data comment
const saveDataRegex = /<!--\s*NP_MOD_SAVE_DATA:\s*({.*?})\s*-->/;
const match = fileContent.match(saveDataRegex);

// Parse JSON and restore state
const saveData = JSON.parse(match[1]);
setLevelIdx(saveData.levelIdx);
setLang(saveData.lang);
setCode(saveData.code);
```

### Key Features:
- ✅ The exported HTML file works as a **normal website** when opened in browser
- ✅ The save data comment is **invisible** to browsers (it's an HTML comment)
- ✅ You can **share the website** with others - it's a fully functional HTML file
- ✅ Only when loaded back into NP_MODERNIZER will it restore your progress

## 📁 Files Included

1. **notepad-modernizer-90-levels.html** - Main application with save/load feature
2. **example-exported-website-level-26.html** - Example of exported file with save data

## 🚀 Usage Example

### Scenario 1: Save Your Work
1. Complete levels 1-25
2. Click "SIMPAN/SAVE" button
3. File downloads: `my-website-level-26.html`
4. File contains your website + hidden progress data
5. You can open it in browser to see your website!

### Scenario 2: Continue Later
1. Open NP_MODERNIZER later
2. Click "MUAT/LOAD" button
3. Select your `my-website-level-26.html` file
4. You're instantly back at Level 26 with all your code!

### Scenario 3: Share Your Website
1. The exported HTML works as a standalone website
2. Share it with friends/teachers
3. They see a beautiful website
4. If they load it in NP_MODERNIZER, they can see how you built it!

## ⚠️ Important Notes

1. **Browser doesn't save progress automatically** - Always click SAVE before closing!
2. **Save data is only in exported files** - Not in browser localStorage
3. **Files with save data can be loaded** - Files without save data load as plain HTML
4. **Save regularly** - Don't lose your hard work!

## 🎯 Benefits

- **No Database Required**: Everything is self-contained in one HTML file
- **Portable**: Take your work anywhere, no cloud needed
- **Backwards Compatible**: Old exports still work as websites
- **Educational**: Students can see the full HTML/CSS they created
- **Shareable**: One file = website + learning progress

Enjoy building! 🚀

