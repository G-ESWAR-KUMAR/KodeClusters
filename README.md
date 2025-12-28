# KodeCluster - Shared Resources Setup

## Project Structure

```
KodeCluster/
├── styles.css              # Shared CSS (theme, animations, glass effects)
├── script.js               # Shared JavaScript (particles, theme toggle, popups)
├── index.html              # Login page with 3D prism
├── login.html              # Alternative login page
├── dashboard.html          # Dashboard page
├── demo.html               # Demo page
├── demo1.html              # Demo 1 page
└── PPT/
    └── KodeClustersPitch/
        └── index.html
```

## Shared Files

### 1. **styles.css** - Common Styling
Contains all shared CSS including:
- **Theme Variables**: `--primary`, `--secondary`, `--bg-deep`, `--glass`
- **Canvas Background**: Particle constellation background
- **Theme Orb**: Floating theme switcher button
- **Animations**: float, slideUp, bounce, progress
- **Glass Effects**: Glassmorphism panels and effects
- **Popup Modal Styles**: Reusable popup styling

### 2. **script.js** - Common JavaScript
Contains all shared JavaScript including:
- **Theme Management**: 3 theme options with dynamic switching
- **Particle System**: Interactive particle animation with mouse tracking
- **Canvas Animation**: Constellation background animation
- **Popup Functions**: `showSuccessPopup()`, `redirectToDashboard()`
- **Auto-initialization**: Runs on DOMContentLoaded

## How to Use in New Pages

### Step 1: Add CSS & JS Links in `<head>`
```html
<link rel="stylesheet" href="styles.css">
```

### Step 2: Add Canvas & Theme Orb in `<body>`
```html
<!-- Canvas Background -->
<canvas id="constellation"></canvas>

<!-- Theme Orb -->
<div id="themeOrb" onclick="changeTheme()" title="Change Atmosphere"></div>
```

### Step 3: Include Common Script Before Closing `</body>`
```html
<script src="script.js"></script>
<script>
    // Your page-specific code here
</script>
```

## Theme System

The theme system includes 3 pre-configured themes:

1. **Theme 1 (Default)**: Green `#00ff88` & Cyan `#00ccff`
2. **Theme 2**: Red `#ff0055` & Yellow `#ffcc00`
3. **Theme 3**: Purple `#cc00ff` & Cyan `#00ffee`

Click the theme orb to toggle between themes.

## Popup Usage Example

```javascript
// Show success popup (auto-redirects after 3 seconds)
function myLoginHandler() {
    // ... validation code ...
    showSuccessPopup();
}

// Custom redirect (if needed)
function redirectToDashboard() {
    window.location.href = 'dashboard.html'; // Change destination
}
```

## Page-Specific Customizations

Each page can have its own page-specific code while using shared resources:

**index.html**: 
- 3D Prism flip animation
- Eye-tracking mascot

**login.html**: 
- Role switching (Student/Instructor)
- Form validation

**dashboard.html**: 
- Dashboard cards with stats
- User profile info
- Action buttons

## CSS Variables Reference

```css
:root {
    --primary: #00ff88;        /* Main accent color */
    --secondary: #00ccff;      /* Secondary accent color */
    --bg-deep: #050510;        /* Dark background */
    --glass: rgba(255,255,255,0.05);  /* Glass effect */
}
```

To override in a specific page:
```html
<style>
    :root {
        --primary: #your-color;
    }
</style>
```

## Browser Compatibility

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Supports GPU acceleration for particles
- Responsive design (mobile-friendly)
- Dark theme optimized

## Performance Notes

- Particle count adjusts based on screen size: `(width * height) / 9000`
- Mouse tracking is optimized with distance checks
- Canvas rendering uses requestAnimationFrame
- CSS animations use GPU acceleration

## Future Enhancements

- [ ] Add more theme options
- [ ] Implement theme persistence (localStorage)
- [ ] Add sound effects
- [ ] Mobile gesture support
- [ ] Dark mode toggle (separate from themes)

## Support

For issues or questions, review the common code in `styles.css` and `script.js`.
