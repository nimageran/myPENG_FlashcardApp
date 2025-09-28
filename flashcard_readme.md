# 📚 PENG NPPE Flashcards App

A mobile-first flashcard study app for **Professional Engineer (PEng) NPPE exam preparation**. Features voice reading, smart image support, and progress tracking.

## 🚀 Quick Setup

### 1. File Structure
```
your-repo/
├── index.html
├── README.md
└── assets/
    ├── cards.csv
    └── images/           (optional: for flashcard images)
        ├── 1.jpg
        ├── 2.jpg
        └── ...
```

### 2. Create Your CSV
Create `assets/cards.csv` with your study material:

```csv
Question,Answer
What does PEng stand for?,Professional Engineer
What is Ohm's Law?,V = I × R
Calculate power when V=12V and I=2A,P = V × I = 24 watts
What is the SI unit for force?,Newton (N)
```

### 3. Enable GitHub Pages
1. Go to **Settings** → **Pages**
2. Select **Deploy from a branch** → **main** → **Save**
3. Your app will be live at: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

## ✨ Key Features

- **🔊 Voice Reading** - Automatically reads flashcards aloud
- **🖼️ Smart Images** - Add diagrams and technical drawings
- **🎲 Random/Sequential** - Toggle study modes
- **📊 Progress Tracking** - Mark cards as Know/Partial/Don't Know
- **📱 Mobile-First** - Optimized for phone and tablet
- **⚡ Offline Ready** - Works without internet after first load

## 🖼️ Adding Images

Place images in `assets/images/` folder with these names:

- `1.jpg` - for first CSV row
- `2.jpg` - for second CSV row
- `3.jpg` - for third CSV row
- etc.

Supported formats: JPG, PNG, GIF, WebP

## 🎮 How to Use

1. **Open the app** - Cards load automatically
2. **Click card** to flip and see answer
3. **Mark knowledge** - ✅ Know It / ⚠️ Partial / ❌ Don't Know
4. **Toggle voice** - 🔊/🔇 button to turn audio on/off
5. **Random mode** - 🎲 button for random card order
6. **Update cards** - Edit CSV and click "Reload CSV"

## ⌨️ Shortcuts

- **Space/Enter** - Flip card
- **Arrow Keys** - Navigate
- **1/2/3** - Mark knowledge level
- **V** - Toggle voice
- **R** - Toggle random mode

## 🔄 Updating Content

1. Edit your `assets/cards.csv` file
2. Commit changes to GitHub
3. Click "📁 Reload CSV" in the app
4. New cards load instantly

---

**Perfect for PENG NPPE exam prep! 🎓⚙️**,./assets/circular-shaft.png
What does this P&ID symbol represent?,Gate Valve,./assets/gate-valve-symbol.png
Define factor of safety,FOS = Ultimate Strength / Working Stress,
What is the efficiency formula for pumps?,η = (ρ × g × Q × H) / P,
```

## 🎮 How to Use

### Basic Navigation
- **Click card** to flip and see answer
- **Use arrow buttons** or swipe to navigate
- **Mark knowledge level** after viewing answer
- **Toggle Random mode** for varied practice

### Voice Features  
- **Auto-reading** - Cards are read aloud automatically
- **Voice toggle** - Turn on/off with button or 'V' key
- **Technical pronunciation** - Optimized for engineering terms

### Progress Tracking
- **Green (Know It)** - Cards you've mastered
- **Yellow (Partial)** - Cards you partially understand  
- **Red (Don't Know)** - Cards you need to study more
- **Progress persists** between sessions

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|---------|
| `Space` or `Enter` | Flip card |
| `←` `→` | Navigate cards |
| `1` | Mark as "Know It" |
| `2` | Mark as "Partial" |  
| `3` | Mark as "Don't Know" |
| `R` | Toggle Random mode |
| `V` | Toggle Voice on/off |
| `S` | Stop current speech |

## 📊 Data Storage

### Local Storage (Browser-Based)
- **Knowledge tracking** saved in browser localStorage
- **Study statistics** persist between sessions  
- **Settings** (voice, random mode) remembered
- **Device-specific** - each device tracks separately
- **No account required** - completely private

### Data Location
```javascript
// Your progress is saved as:
localStorage.pengKnowledge     // Which cards you know/don't know
localStorage.pengStats         // Study statistics
localStorage.pengVoiceEnabled  // Voice setting
localStorage.pengRandomMode    // Random mode setting
```

## 🔄 Updating Your Cards

1. **Edit** your `assets/cards.csv` file
2. **Commit and push** changes to GitHub
3. **In the app**, click "📁 Reload CSV" button
4. **New cards load** immediately with all features working

## 📱 Installation

### Mobile (iOS/Android)
1. Open the app in your browser
2. Look for "Add to Home Screen" option
3. App installs like a native app
4. Works offline after installation

### Desktop  
1. Chrome/Edge will show "Install" button
2. Or bookmark for quick access
3. Works in any modern browser

## 🛠️ Customization

### Voice Settings
- **Rate**: Modify `utterance.rate = 0.85` in code
- **Pitch**: Modify `utterance.pitch = 1.0` in code  
- **Volume**: Modify `utterance.volume = 0.8` in code

### Styling
- Edit CSS variables in the `<style>` section
- Colors, fonts, and animations are all customizable
- Mobile-responsive design adapts automatically

## 🔧 Technical Requirements

### Browser Support
- **Chrome** 60+ (recommended)
- **Firefox** 55+
- **Safari** 12+
- **Edge** 79+

### Features Used
- **Web Speech API** (for voice reading)
- **localStorage** (for progress tracking)
- **CSV parsing** (PapaParse library)
- **Progressive Web App** (PWA) features

## 📈 Study Tips

### Effective Usage
1. **Start with sequential mode** for new topics
2. **Switch to random mode** for review sessions
3. **Use voice feature** for hands-free study
4. **Mark honestly** - it helps track real progress
5. **Review "Don't Know" cards** more frequently

### PENG NPPE Specific
- **Add diagrams** for complex engineering concepts
- **Include formulas** with proper mathematical notation
- **Use technical terminology** exactly as it appears in references
- **Practice calculations** with step-by-step solutions
- **Review ethics questions** and professional practices

## 🤝 Contributing

Feel free to:
- Report issues or bugs
- Suggest new features  
- Submit improvements
- Share your study materials (following copyright guidelines)

## 📜 License

This project is open source. Feel free to use, modify, and share for educational purposes.

## 🎯 Perfect For

- **PENG NPPE exam preparation**
- **Engineering students** studying technical subjects
- **Professional development** and continuing education
- **Technical certification** exam prep
- **Any subject** requiring memorization and recall

---

**Good luck with your PENG NPPE exam! 🎓⚙️**

*Study hard, study smart, and let technology help you succeed.*