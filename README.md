# Five Element Acupuncture Practice Manager

## Overview

**Five Element Acupuncture Practice Manager** is a single-page web application for tracking Five Element acupuncture sessions. The application follows the Worsley-style Five Element acupuncture tradition, combining clinical documentation with spiritual resonance tracking.

**Current Status**: This is a functional prototype with complete assessment tracking and basic treatment planning capabilities. The application runs entirely in the browser with no server dependencies.

## Current Features

### Complete Patient Assessment Module
- Session date/time tracking
- Constitutional type identification (Wood, Fire, Earth, Metal, Water)
- Symptom categorization with elemental associations
- Comprehensive tongue diagnosis:
  - Body color, coating, texture, movement
  - Location-specific observations (tip, sides)
  - Additional notes field
- Three-level pulse diagnosis:
  - Superficial, middle, deep positions for all 12 pulse positions
  - Traditional pulse qualities (Floating, Deep, Slow, Rapid, etc.)
  - Organized by left/right hand and Cun/Guan/Chi positions

### Basic Treatment Planning
- Causative Factor selection
- Treatment strategy options
- Acupuncture point search and selection from a curated Five Element point database
- Point database includes:
  - Standard codes (LU9, LI4, etc.)
  - Pinyin names
  - English translations
  - **Spiritual names** (e.g., "Gate of Hope" for ST25, "Great Eliminator" for LI4)
  - Elemental associations
  - Point types (Source, Horary, Command points)
  - Spiritual resonance descriptions

### Session Management
- In-browser session storage
- CSV export functionality
- Session history viewing
- Form clearing and reset capabilities

### User Interface
- Professional styling with gold/blue color scheme
- Responsive design using CSS Grid and Flexbox
- Step-based workflow navigation
- Cinzel and Crimson Text fonts for elegant typography

## Technical Implementation

### Architecture
- **Single HTML file** containing all HTML, CSS, and JavaScript
- **No external dependencies** - runs in any modern browser
- **Client-side storage** using localStorage API
- **Pure JavaScript** - no frameworks or libraries

### Data Structure
The application maintains:
- `savedSessions[]`: Array of completed assessment sessions
- `fiveElementPoints[]`: Database of 14 core Five Element acupuncture points
- `selectedPoints[]`: Currently selected points for treatment planning
- `currentTreatmentPlan`: Current treatment plan being developed

### Point Database (Current)
The application includes 14 essential Five Element points with spiritual attributes:
- LU9 (Taiyuan) - "Supreme Source" - Metal element
- LI4 (Hegu) - "Great Eliminator" - Metal element  
- ST25 (Tianshu) - "Gate of Hope" - Earth element
- SP3 (Taibai) - "Great Clarity" - Earth element
- HT7 (Shenmen) - "Gate of the Shen" - Fire element
- SI3 (Houxi) - "Rear Ravine" - Fire element
- BL67 (Zhiyin) - "Ultimate Yin" - Water element
- KI3 (Taixi) - "Supreme Ravine" - Water element
- PC6 (Neiguan) - "Inner Frontier Gate" - Fire element
- TE5 (Waiguan) - "Outer Frontier Gate" - Fire element
- GB34 (Yanglingquan) - "Sunlit Plateau Spring" - Wood element
- LV3 (Taichong) - "Supreme Rushing" - Wood element
- GV20 (Baihui) - "Meeting of Heaven" - Governing Vessel
- CV17 (Shanzhong) - "Sea of Tranquility" - Conception Vessel

## Limitations and Known Issues

### Not Yet Implemented (Per README Claims)
- **Live Treatment Tracking**: The "Live Treatment" step exists but only contains placeholder content
- **Session Review**: The "Session Review" step exists but is not functional
- **Complete Treatment Workflow**: Only Assessment → Planning steps are fully implemented
- **Point-by-point needle details**: Treatment logging interface is not functional
- **Patient portal view**: No separate patient interface exists
- **PDF export**: Only CSV export is available
- **Multi-user support**: No authentication or user management

### Technical Limitations
- **No data persistence across browsers/devices**: Data stored only in current browser's localStorage
- **No backend/database**: All data lives in browser memory
- **No offline capability**: While it runs in browser, there's no service worker for true offline use
- **No data validation**: Minimal input validation implemented
- **No error handling**: Basic implementation without robust error recovery

## Getting Started

### Immediate Use
1. Download `index.html`
2. Open in Chrome, Firefox, Safari, or Edge
3. Begin entering assessment data
4. Data automatically saves to your browser's localStorage

### Development
1. Clone or download the HTML file
2. Open in code editor
3. Modify as needed - all code is in a single file
4. Test in browser

## Project Structure

Truly, the structure is a mess. Someday it will reflect:

Single File: index.html
├── HTML Structure
│ ├── Header and navigation
│ ├── Four workflow steps (Assessment, Planning, Treatment, Review)
│ └── Saved sessions display
├── CSS Styles
│ ├── Layout and responsive design
│ ├── Color scheme and typography
│ └── Form element styling
└── JavaScript
├── Initialization and setup
├── Five Element points database
├── Workflow navigation functions
├── Assessment data handling
├── Treatment planning functions
└── Session storage/export


## Roadmap (Accurate)

### Phase 1: Current Implementation ✓
- Complete assessment data collection
- Basic treatment planning with point selection
- In-browser session storage
- CSV export functionality

### Phase 2: Needed for Basic Clinical Use
1. **Complete treatment workflow** - Implement "Live Treatment" and "Session Review" steps
2. **Expand point database** - Add 50+ more Five Element points
3. **Data persistence** - Implement proper save/load functionality
4. **Basic validation** - Ensure required fields are completed
5. **Print/PDF functionality** - Generate session reports

### Phase 3: Production Readiness
1. **Backend integration** - Server storage for multi-device access
2. **Patient management** - Multiple patient profiles
3. **Advanced analytics** - Treatment pattern recognition
4. **Mobile optimization** - Touch-friendly interface
5. **Data security** - Patient data protection

## Clinical Use Considerations

### Appropriate Use
- **Supplemental tool** for session documentation
- **Training aid** for Five Element students
- **Patient education** tool to explain treatments
- **Practice management** for tracking session patterns

### Limitations for Clinical Use
- **Not HIPAA compliant** in current form
- **No patient data encryption**
- **Limited data backup** (browser storage only)
- **No audit trail** for data changes

## Development Notes

### Code Organization
The application is currently a single HTML file with inline CSS and JavaScript. For maintainability, consider separating into:
- `index.html` - Structure
- `style.css` - Styling  
- `app.js` - Application logic
- `points.js` - Acupuncture point database

## License and Usage
This software is provided as-is for educational and personal use. Clinical application requires appropriate verification and modification by a qualified and licensed acupuncturist.

## Support

For issues or questions:

- Review the JavaScript console for errors
- Clear browser localStorage if data becomes corrupted
- Ensure modern browser is being used

## Note: This README accurately reflects the current implementation as of the last code review. Features described in "Future Phases" are not yet implemented.
 
### Data Model Expansion
To add more points, expand the `fiveElementPoints` array with objects containing:
```javascript
{
    id: "POINT_CODE",
    code: "MERIDIAN_CODE",
    pinyin: "PINYIN_NAME",
    englishName: "ENGLISH_TRANSLATION",
    spiritualName: "SPIRITUAL_NAME",
    meridian: "MERIDIAN_NAME",
    element: "ELEMENT",
    pointType: "POINT_TYPE_DESCRIPTION",
    resonance: "SPIRITUAL_DESCRIPTION",
    commonUse: "CLINICAL_APPLICATION"
}

