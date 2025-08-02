# Client Avatar Discovery Tool - Simple Version

A minimal, single-file Client Avatar Discovery tool for interior designers.

## Features

✅ **Single HTML File** - No frameworks, no build process
✅ **Claude API Integration** - Real AI-powered conversations  
✅ **6-Phase Discovery Process** - Complete client avatar methodology
✅ **Local Storage** - Progress automatically saved
✅ **Payment Gating** - Access control via URL parameter
✅ **PDF Generation** - Professional reports using jsPDF
✅ **Star Rating System** - User feedback collection
✅ **Google Analytics** - Usage tracking

## Setup Instructions

### 1. Configure Claude API Key
Replace `'your-claude-api-key-here'` in the file with your actual Claude API key:
```javascript
const CLAUDE_API_KEY = 'sk-ant-api03-your-actual-key-here';
```

### 2. Configure Google Analytics (Optional)
Replace `GA_MEASUREMENT_ID` with your Google Analytics measurement ID:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
```

### 3. Update Payment Link
The Gumroad payment link is currently set to:
```
https://interiordesignher.gumroad.com/l/client-avatar-discovery
```
Update this URL in the `showPaymentRequired()` function if needed.

## Usage

### Free Access
- Users can send up to 3 messages for free
- After 3 messages, payment is required to continue

### Paid Access
- Access with URL parameter: `?access=paid`
- Example: `https://yoursite.com/client-avatar-discovery.html?access=paid`
- Full access to all 6 phases and PDF generation

### Phases
1. **Business Foundation** - Current business situation and goals
2. **Profitable Project Analysis** - Most successful project types
3. **Market Intelligence** - Target market and positioning
4. **Financial Profile** - Budget ranges and payment behavior
5. **Communication & Management** - Client interaction preferences
6. **Business Development Strategy** - Lead generation and conversion

## Deployment

### Option 1: GitHub Pages
1. Create a new GitHub repository
2. Upload the HTML file as `index.html`
3. Enable GitHub Pages in repository settings
4. Access via `https://yourusername.github.io/repository-name/`

### Option 2: Custom Domain
1. Deploy to GitHub Pages first
2. Add CNAME file with your custom domain
3. Configure DNS settings to point to GitHub Pages
4. Example: `tools.interiordesignher.com`

## File Structure
```
client-avatar-discovery-simple.html  # Complete standalone application
├── HTML structure
├── CSS styling
├── JavaScript logic
├── Claude API integration
├── PDF generation
├── Analytics tracking
└── Payment gating
```

## Browser Compatibility
- Chrome 70+
- Firefox 65+
- Safari 12+
- Edge 79+

## Security Notes
- Claude API key is exposed in client-side code
- For production, consider using a proxy server to hide the API key
- CORS restrictions may apply for Claude API calls

## Customization
- Modify phase prompts in the `phases` object
- Adjust payment threshold in `sendMessage()` function
- Customize PDF layout in `generatePDF()` function
- Update styling in the `<style>` section

## Support
For issues or questions, contact: support@interiordesignher.com