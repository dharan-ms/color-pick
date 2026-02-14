# Color Picker App

A simple, elegant React color picker application that allows users to select colors and copy their HEX and RGB values to the clipboard.

## Features

- **Color Selection**: Interactive color picker using native HTML5 `<input type="color">`
- **Value Display**: Shows both HEX and RGB formats of the selected color
- **Color Preview**: Real-time visual preview box that updates with the selected color
- **Copy to Clipboard**: 
  - Copy HEX values (e.g., `#FF5733`)
  - Copy RGB values (e.g., `rgb(255, 87, 51)`)
  - Modern Clipboard API with fallback for older browsers
- **Input Validation**: Automatically validates HEX format and disables RGB copy for invalid values
- **Success Feedback**: Toast notification appears when values are copied successfully
- **Responsive Design**: Optimized for both desktop and mobile devices
- **Clean UI**: Centered card layout with modern design tokens

## Technical Details

### Built With
- **React 18** - Functional components and hooks
- **Vite** - Fast build tool and development server
- **Vanilla CSS** - Custom CSS with CSS variables for design tokens
- **No external libraries** - Pure React implementation

### React Features Used
- `useState` - For managing color and toast message state
- `useMemo` - For optimized HEX to RGB conversion

### Browser Compatibility
- Uses modern Clipboard API where available
- Includes fallback mechanism for older browsers
- Works in both secure (HTTPS) and non-secure contexts

## Getting Started

### Prerequisites
- Node.js version 20.19+ or 22.12+
- npm (Node Package Manager)

### Installation

1. Clone or download this repository

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to the URL shown in the terminal (typically `http://localhost:5173`)

### Build for Production

To create a production build:
```bash
npm run build
```

The optimized files will be in the `dist` folder.

To preview the production build:
```bash
npm run preview
```

## Usage

1. **Select a Color**: Click on the color picker input to choose your desired color
2. **View Values**: The HEX and RGB values will update automatically
3. **Copy Values**: Click "Copy HEX" or "Copy RGB" to copy the respective value to your clipboard
4. **Success Message**: A toast notification will confirm when the value is copied

## Project Structure

```
color-picker-app/
├── src/
│   ├── App.jsx          # Main application component
│   ├── App.css          # Component-specific styles
│   ├── index.css        # Global styles and design tokens
│   └── main.jsx         # Application entry point
├── index.html           # HTML template
├── package.json         # Project dependencies
├── vite.config.js       # Vite configuration
└── README.md           # This file
```

## Design Tokens

The app uses CSS custom properties for consistent theming:
- Colors (primary, success, error, backgrounds, text, borders)
- Spacing (xs, sm, md, lg, xl)
- Border radius (sm, md, lg)
- Shadows (sm, md, lg)
- Transitions (fast, normal)

These can be easily customized in `src/index.css`.

## Deployment to GitHub Pages

### Option 1: Using GitHub Actions (Recommended)

The project includes a GitHub Actions workflow that automatically deploys to GitHub Pages when you push to the `main` branch.

**Setup Steps:**

1. **Create a GitHub repository** and push your code:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/color-picker-app.git
git push -u origin main
```

2. **Enable GitHub Pages** in your repository:
   - Go to **Settings** → **Pages**
   - Under **Source**, select **GitHub Actions**

3. **Update the base path** in `vite.config.js`:
   - Change `/color-picker-app/` to match your repository name
   - If your repo is named differently, update line 7 in `vite.config.js`:
     ```js
     base: process.env.NODE_ENV === 'production' ? '/YOUR_REPO_NAME/' : '/',
     ```

4. **Push changes** and the workflow will automatically deploy your app!

Your app will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### Option 2: Manual Deployment with gh-pages

If you prefer manual deployment:

1. **Install gh-pages** (already in devDependencies):
```bash
npm install
```

2. **Update base path** in `vite.config.js` to match your repo name (as shown above)

3. **Deploy manually**:
```bash
npm run deploy
```

This will build your app and push it to the `gh-pages` branch.

4. **Enable GitHub Pages**:
   - Go to **Settings** → **Pages**
   - Under **Source**, select **Deploy from a branch**
   - Select the **gh-pages** branch and **/ (root)** folder
   - Click **Save**

Your app will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

### Important Notes

- Replace `YOUR_USERNAME` with your GitHub username
- Replace `YOUR_REPO_NAME` with your actual repository name
- The base path in `vite.config.js` must match your repository name exactly
- For custom domains, you can configure them in GitHub Pages settings

## License

This project is open source and available for educational and commercial use.
