# 🎨 Carpet Pattern Analyzer

AI-powered tool to analyze carpet and rug patterns, extract color palettes, and generate visual grids for interior design, material specification, and design analysis.

![Carpet Pattern Analyzer](https://img.shields.io/badge/Built%20with-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Claude AI](https://img.shields.io/badge/Claude-AI-7C3AED?style=for-the-badge)

---

## 📋 Table of Contents

- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Installation Guide](#-installation-guide)
- [Getting Your API Key](#-getting-your-api-key)
- [Running the App](#-running-the-app)
- [How to Use](#-how-to-use)
- [Export Options](#-export-options)
- [Troubleshooting](#-troubleshooting)
- [Use Cases](#-use-cases)
- [Technical Details](#-technical-details)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### Core Capabilities
- 📤 **Image Upload**: Support for PNG, JPG, JPEG, and WEBP formats
- 🎯 **Customizable Grid**: Generate grids from 2×2 up to 100×100 cells
- 🎨 **Smart Color Extraction**: Automatically extract colors from each grid cell
- 🔧 **Color Quantization**: Simplify patterns by grouping similar colors (3-20 color range)
- 🤖 **AI Pattern Analysis**: Get expert analysis of pattern style, design elements, and color harmony using Claude AI

### Export Options
- 📥 **PNG Export**: High-resolution grid images (300 DPI) for presentations
- 📊 **Excel Export**: Interactive spreadsheets with color-coded cells and hex codes
- 📝 **Text Export**: Complete color palette list with hex and RGB values

### Additional Features
- ⚡ Real-time grid updates as you adjust settings
- 🎭 Visual color palette display with hex codes
- 💡 Automatic text color contrast (white/black text based on cell brightness)
- 🔒 Secure API key management

---

## 📦 Prerequisites

Before you begin, make sure you have:

### 1. **Python 3.10 or Higher**
- Check if installed: Open terminal/command prompt and type `python --version`
- If not installed: Download from [python.org](https://www.python.org/downloads/)
- **Important**: During installation, check "Add Python to PATH"

### 2. **Git** (for cloning the repository)
- Check if installed: Type `git --version` in terminal
- If not installed: Download from [git-scm.com](https://git-scm.com/downloads)

### 3. **Code Editor** (recommended)
- [VS Code](https://code.visualstudio.com/) - Beginner-friendly
- Or any text editor of your choice

### 4. **Anthropic API Key** (for AI analysis feature)
- Free tier available with $5 credit for new users
- See [Getting Your API Key](#-getting-your-api-key) section below

---

## 🚀 Installation Guide

### Step 1: Clone the Repository

Open your terminal (Command Prompt on Windows, Terminal on Mac/Linux) and run:

```bash
git clone https://github.com/azarrinr/carpet-pattern-analyzer.git
```

Navigate into the project folder:

```bash
cd carpet-pattern-analyzer
```

---

### Step 2: Install Required Packages

Install all dependencies with one command:

```bash
pip install -r requirements.txt
```

**What gets installed:**
- `streamlit` - Web interface framework
- `pillow` - Image processing
- `numpy` - Numerical computations
- `matplotlib` - Grid visualization
- `scikit-learn` - Color clustering
- `anthropic` - Claude AI integration
- `openpyxl` - Excel file generation

**Expected time:** 2-5 minutes depending on your internet speed

---

### Step 3: Set Up Your API Key

#### Create the Configuration Folder

**On Windows:**
```bash
mkdir .streamlit
```

**On Mac/Linux:**
```bash
mkdir .streamlit
```

#### Create the Secrets File

**On Windows:**
```bash
notepad .streamlit\secrets.toml
```

**On Mac/Linux:**
```bash
nano .streamlit/secrets.toml
```

#### Add Your API Key

In the file that opens, add this line:

```toml
ANTHROPIC_API_KEY = "sk-ant-your-actual-api-key-here"
```

**Important:** 
- Replace `sk-ant-your-actual-api-key-here` with your real API key
- Keep the quotes around your key
- Save the file and close the editor

**On nano (Mac/Linux):**
- Press `Ctrl + O` to save
- Press `Enter` to confirm
- Press `Ctrl + X` to exit

---

## 🔑 Getting Your API Key

### Create an Anthropic Account

1. **Go to:** [console.anthropic.com](https://console.anthropic.com/)
2. **Sign up** for a free account
3. **Verify** your email address

### Generate Your API Key

1. **Click "API Keys"** in the left sidebar
2. **Click "Create Key"** button
3. **Give it a name** (e.g., "Carpet Analyzer")
4. **Copy the key** - it starts with `sk-ant-`
5. **Save it somewhere safe** - you won't be able to see it again!

### Free Tier Information

- New accounts get **$5 in free credits**
- Claude Sonnet 4 costs approximately:
  - Input: $3 per million tokens
  - Output: $15 per million tokens
- Each pattern analysis uses roughly $0.01-0.03
- Your free credits cover ~150-500 analyses

**Note:** Color extraction and grid generation work WITHOUT the API key. AI analysis is optional!

---

## ▶️ Running the App

### Start the Application

In your terminal (make sure you're in the `carpet-pattern-analyzer` folder):

```bash
streamlit run app.py
```

**What happens:**
1. Streamlit server starts
2. Your default browser opens automatically
3. The app loads at `http://localhost:8501`

**If the browser doesn't open automatically:**
- Manually go to: `http://localhost:8501`

### Stop the Application

When you're done:
- Press `Ctrl + C` in the terminal
- Or just close the terminal window

---

## 📖 How to Use

### Basic Workflow

#### 1. Upload an Image
- Click **"Browse files"** button
- Select a carpet/rug image from your computer
- Supported formats: PNG, JPG, JPEG, WEBP
- The image appears on the left side

#### 2. Adjust Grid Settings (Left Sidebar)

**Grid Dimensions:**
- **Width**: Number of columns (2-100)
- **Depth**: Number of rows (2-100)
- Start with 10×10 for testing, increase for more detail

**Color Variation Slider:**
- **Low (3-5)**: Very simplified, just a few main colors
- **Medium (8-12)**: Balanced detail and simplicity
- **High (15-20)**: Maximum color detail

#### 3. View the Generated Grid

The pattern grid appears on the right side showing:
- Color-coded cells representing carpet sections
- Real-time updates as you adjust settings
- Grid dimensions and color count

#### 4. AI Analysis (Optional)

- Scroll down to **"AI Pattern Analysis"** section
- Click **"Analyze Pattern with Claude AI"** button
- Wait 3-5 seconds for analysis
- Read Claude's insights about:
  - Pattern style (Persian, Modern, Geometric, etc.)
  - Design elements and motifs
  - Color harmony analysis
  - Overall design impression

#### 5. View Color Palette

Scroll down to see:
- All distinct colors used in the grid
- Hex codes (e.g., `#8B4513`)
- RGB values (e.g., `RGB: 139, 69, 19`)
- Color swatches for visual reference

---

## 📥 Export Options

### PNG Export (High-Resolution Grid)

**Use for:**
- PowerPoint presentations
- Design portfolios
- Client proposals
- Documentation

**Features:**
- 300 DPI resolution
- Professional quality
- Transparent grid lines
- Ready to insert into documents

**How to:**
1. Generate your grid
2. Click **"Download Grid (PNG)"** button
3. Save the file
4. Insert into any document or presentation

---

### Excel Export (Interactive Spreadsheet)

**Use for:**
- Material specifications
- Color matching worksheets
- Editable documentation
- Budget calculations

**Features:**
- Each cell colored with actual pattern color
- Hex codes displayed in each cell
- Adjustable cell sizes
- Copy/paste colors to other tools

**Excel File Details:**
- Cell width: 15 units
- Cell height: 60 pixels
- Text color: Auto-adjusts (black on light, white on dark)
- Format: `.xlsx` (Excel 2007+)

**How to:**
1. Generate your grid
2. Click **"Download Grid (Excel)"** button
3. Open in Excel, Google Sheets, or LibreOffice
4. Edit, annotate, or share

---

### Text Export (Color Palette List)

**Use for:**
- Paint matching
- Color specifications
- Quick reference
- Simple documentation

**Format:**
```
CARPET PATTERN COLOR PALETTE
========================================

Color 1: #8B4513 | RGB(139, 69, 19)
Color 2: #2F4F4F | RGB(47, 79, 79)
Color 3: #F4A460 | RGB(244, 164, 96)
...
```

**How to:**
1. Scroll to Color Palette section
2. Click **"Download Color List"** button
3. Save as `.txt` file
4. Open with any text editor

---

## 🔧 Troubleshooting

### Common Issues and Solutions

#### "Module not found" Error

**Problem:** Python can't find installed packages

**Solution:**
```bash
pip install -r requirements.txt --upgrade
```

If that doesn't work, try:
```bash
python -m pip install -r requirements.txt
```

---

#### "API Key Error" When Using AI Analysis

**Problem:** API key not configured or invalid

**Solutions:**

1. **Check if secrets file exists:**
   - Look for `.streamlit/secrets.toml` in your project folder
   - If missing, create it (see Step 3 of installation)

2. **Verify API key format:**
   ```toml
   ANTHROPIC_API_KEY = "sk-ant-..."
   ```
   - Must start with `sk-ant-`
   - Must be in quotes
   - No spaces around `=`

3. **Restart Streamlit:**
   - Stop the app (`Ctrl + C`)
   - Run `streamlit run app.py` again

4. **Check API key validity:**
   - Go to [console.anthropic.com](https://console.anthropic.com/)
   - Verify your key is active
   - Check your credit balance

---

#### App Won't Start / Port Already in Use

**Problem:** Another app is using port 8501

**Solution:**
```bash
streamlit run app.py --server.port 8502
```

Or stop other Streamlit apps:
- Find them in your task manager
- Close terminal windows running Streamlit

---

#### Large Grids Take Too Long

**Problem:** 100×100 grids are slow to process

**Solutions:**
- Use smaller grids (20×20 to 50×50) for faster results
- Reduce color variation to 5-10
- Close other programs to free up memory
- Be patient - complex grids can take 10-30 seconds

---

#### Excel File Won't Open

**Problem:** Excel file appears corrupted

**Solutions:**
1. Make sure you have Excel 2007 or newer
2. Try opening with Google Sheets or LibreOffice
3. Re-generate and download the file
4. Check if file fully downloaded (should be several KB)

---

#### Colors Look Different Than Image

**Why:** Grid cells average all pixels in that cell

**Solutions:**
- Increase grid size for more detail
- Increase color variation slider
- Use higher resolution source image
- This is normal behavior - the grid simplifies the pattern

---

## 🎯 Use Cases

### Interior Design
- **Client Presentations**: Show color schemes extracted from inspiration images
- **Material Matching**: Get exact hex codes for paint, fabric, or tile matching
- **Mood Boards**: Generate simplified pattern grids for design concepts
- **Color Consulting**: Analyze existing carpets for renovation projects

### Architecture
- **Material Specifications**: Document exact colors for construction documents
- **Vendor Communication**: Share color palettes with carpet suppliers
- **Design Development**: Study pattern repetition and variations
- **FF&E Documentation**: Create detailed furnishing specifications

### E-commerce
- **Product Documentation**: Generate technical specs for carpet listings
- **Catalog Creation**: Standardized pattern visualization
- **Customer Service**: Help customers understand color variations
- **Marketing Materials**: Create attractive product showcases

### Academic Research
- **Textile Studies**: Analyze historical or cultural pattern characteristics
- **Color Theory**: Study color relationships in traditional designs
- **Design History**: Document and categorize pattern styles
- **Comparative Analysis**: Study patterns across cultures or time periods

### Personal Projects
- **Home Renovation**: Match existing carpets for repairs or additions
- **DIY Design**: Plan custom rug designs with specific color palettes
- **Art Projects**: Extract color schemes from traditional textiles
- **Collection Documentation**: Catalog personal rug collection

---

## 🧰 Technical Details

### Tech Stack

**Frontend:**
- Streamlit 1.28+ - Web application framework
- Custom CSS for enhanced UI/UX

**Image Processing:**
- Pillow (PIL) - Image loading and manipulation
- NumPy - Array operations for pixel data
- scikit-learn - K-means clustering for color quantization

**Visualization:**
- Matplotlib - Grid rendering and plot generation
- Custom styling for clean, professional output

**AI Integration:**
- Anthropic API - Claude Sonnet 4 for pattern analysis
- Vision API for image understanding
- Structured prompts for consistent analysis

**Export Functionality:**
- openpyxl - Excel file generation with formatting
- BytesIO - In-memory file handling
- Base64 encoding - Image data transmission

### Color Processing Algorithm

1. **Grid Division**: Image divided into user-specified grid dimensions
2. **Cell Extraction**: Each cell's pixels extracted as array
3. **Color Averaging**: Mean RGB values calculated per cell
4. **K-means Clustering**: Similar colors grouped based on slider setting
5. **Palette Generation**: Unique colors extracted from cluster centers

### Performance Considerations

**Grid Size Impact:**
- 10×10 grid (100 cells): ~1 second
- 50×50 grid (2,500 cells): ~5 seconds
- 100×100 grid (10,000 cells): ~15 seconds

**Memory Usage:**
- Base app: ~50 MB
- With large image: ~100-200 MB
- Grid processing: Additional 50-100 MB
- Excel export: ~1 MB per file

**API Costs:**
- Each analysis: $0.01-0.03
- Depends on image size and complexity
- No cost for grid generation without AI analysis

### File Structure

```
carpet-pattern-analyzer/
├── .streamlit/
│   └── secrets.toml          # Your API key (not in Git)
├── .gitignore                # Protects secrets
├── README.md                 # This file
├── app.py                    # Main application
└── requirements.txt          # Python dependencies
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Ways to Contribute

1. **Report Bugs**: Open an issue describing the problem
2. **Suggest Features**: Share ideas for new functionality
3. **Improve Documentation**: Fix typos or clarify instructions
4. **Submit Code**: Create pull requests with improvements

### Development Setup

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Test thoroughly
5. Commit: `git commit -m "Add feature description"`
6. Push: `git push origin feature-name`
7. Open a Pull Request

### Code Style

- Follow PEP 8 guidelines
- Add comments for complex logic
- Update README if adding features
- Test with various image types and sizes

---

## 📄 License

MIT License

Copyright (c) 2025 Amir

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## 👤 Author

**Amir**
- GitHub: [@azarrinr](https://github.com/azarrinr)
- Built with Claude AI

### Why I Built This

As an architecture student working with building materials and interior design, I needed a quick way to extract and document color palettes from carpet patterns. Existing tools were either too expensive, too complex, or didn't provide the export formats I needed. This tool solves that problem by combining simple image processing with AI-powered analysis.

---

## 🙏 Acknowledgments

- **Anthropic** - For Claude AI API and excellent documentation
- **Streamlit** - For making beautiful web apps accessible to Python developers
- **Open Source Community** - For the amazing libraries that power this tool

---

## 📞 Support & Contact

### Getting Help

1. **Check Troubleshooting Section**: Most common issues covered above
2. **GitHub Issues**: [Open an issue](https://github.com/azarrinr/carpet-pattern-analyzer/issues)
3. **Anthropic Documentation**: [docs.anthropic.com](https://docs.anthropic.com/)
4. **Streamlit Documentation**: [docs.streamlit.io](https://docs.streamlit.io/)

### Reporting Issues

When reporting bugs, please include:
- Python version (`python --version`)
- Operating system (Windows/Mac/Linux)
- Steps to reproduce
- Error messages (full text)
- Screenshots if applicable

---

## 🚀 What's Next?

### Potential Future Features

- [ ] Batch processing for multiple images
- [ ] Pattern comparison tool
- [ ] Historical pattern database
- [ ] Color palette suggestions
- [ ] PDF export with analysis report
- [ ] Mobile-responsive design
- [ ] Pattern similarity search
- [ ] Custom color matching tools

**Want to see a feature?** Open an issue and let me know!

---

## ⭐ Show Your Support

If you find this tool useful:
- ⭐ Star this repository
- 🐛 Report bugs and issues
- 💡 Suggest new features
- 📢 Share with others who might benefit

---

**Happy Pattern Analyzing!** 🎨✨

*Last updated: November 2025*
