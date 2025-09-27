# 📚 PENG NPPE Flashcards App

A comprehensive flashcard study app designed specifically for **Professional Engineer (PEng) National Professional Practice Examination (NPPE)** preparation. Features voice reading, image support, progress tracking, and works perfectly on both mobile and desktop.

## 🎯 Features

### ✨ Core Functionality
- **📱 Mobile-First Design** - Optimized for phone and tablet use
- **🔊 Voice Reading** - Automatically reads flashcards aloud (both front and back)
- **🖼️ Image Support** - Add diagrams, formulas, and technical drawings
- **🎲 Study Modes** - Sequential or Random card order
- **📊 Progress Tracking** - Mark cards as Know/Partial/Don't Know
- **⚡ Offline Ready** - Works without internet after first load
- **⌨️ Keyboard Shortcuts** - Full keyboard navigation support

### 🧠 Learning Features
- **Knowledge Persistence** - Remembers which cards you've mastered
- **Study Statistics** - Track total cards studied and mastery progress
- **Visual Progress Bar** - See completion status for current session
- **Auto-Advance** - Automatically moves to next card after marking knowledge

### 🔧 Technical Features
- **Auto-Load CSV** - Automatically loads flashcards from your CSV file
- **Smart Voice** - Optimized speech for engineering terms and formulas
- **PWA Support** - Installable as a native-like app
- **Cross-Platform** - Works on iOS, Android, Windows, Mac, Linux

## 🚀 Quick Start

### 1. Setup Your Repository
```
your-repo-name/
├── index.html          (the flashcard app)
├── README.md          (this file)
└── assets/
    ├── cards.csv      (your flashcard data)
    ├── image1.png     (optional: question images)
    └── image2.jpg     (optional: more images)
```

### 2. Create Your Flashcards
Create `assets/cards.csv` with your PENG NPPE study material:

**Basic Format (2 columns):**
```csv
Question,Answer
What does PEng stand for?,Professional Engineer
What is Ohm's Law?,V = I × R
Calculate power when V=12V and I=2A,P = V × I = 24 watts
What is the SI unit for force?,Newton (N)
```

**With Images (3 columns):**
```csv
Question,Answer,Image
Identify this electrical symbol,Resistor,./assets/resistor-symbol.png
What formula is shown in the diagram?,Bernoulli's equation,./assets/bernoulli-diagram.jpg
Calculate the moment for this beam,M = F × d,./assets/beam-diagram.png
```

### 3. Enable GitHub Pages
1. Go to your repository **Settings**
2. Scroll to **Pages** section  
3. Under **Source**, select **Deploy from a branch**
4. Choose **main** branch and **/ (root)**
5. Click **Save**

Your app will be live at: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

## 📝 CSV Format Guide

### Column Names (Auto-Detected)
The app automatically detects these column names:

**Front/Question columns:** `Front`, `Question`, `Q`, `Term`, `Problem`, `Word`, `Prompt`
**Back/Answer columns:** `Back`, `Answer`, `A`, `Solution`, `Definition`, `Explanation`  
**Image columns:** `Image`, `Img`, `Picture`, `Photo`

### Engineering Content Examples
```csv
Question,Answer,Image
What is the formula for stress?,σ = F/A,
Calculate the moment of inertia for a solid circular shaft,I = πd⁴/64,./assets/circular-shaft.png
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