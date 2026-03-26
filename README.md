# Accountability Chart

A simple, no-build web app for managing organizational structure. Editable company name, customizable role types, and clean visual hierarchy.

![Screenshot](screenshot.png)

## Features

- **Save/Load to File** — Export your chart as JSON, share it, load it anywhere
- **Editable Company Name** — Click the header title to change it
- **Custom Role Types** — Add, edit, remove role types with custom colors
- **Visual Org Chart** — Tree diagram with proper connecting lines
- **Add/Edit People** — Form for managing names, roles, domains, reporting
- **Local Storage** — Auto-saves to your browser
- **No Server Required** — Just open the HTML file

## Quick Start

1. Download `index.html`
2. Double-click to open in any browser
3. Click the company name to rename
4. Start adding your team!

## How to Use

### Chart View
- See the full organizational hierarchy
- Click any person to edit them
- Colors are based on role type (customizable)

### Edit People
- **Add Person**: Fill the form and click "Save Person"
- **Edit**: Click a person in the list or chart
- **Delete**: Click the ✕ button (children become top-level)
- **Change Reporting**: Edit "Reports To" dropdown

### Customize Role Types
In the Edit People view, scroll down to "Role Types":
- Click the color square to change color
- Edit the text to rename
- ✕ to delete a type
- "+ Add Role Type" to create new ones

**Note**: Deleting a role type will move all people with that type to the first remaining type.

## Data Storage

### File Save/Load (Recommended)
Use the **"Save to File"** and **"Load from File"** buttons in the header:
- Saves everything (company name, role types, people) to a JSON file
- Filename includes company name and date
- Share the file with others
- Load it on any computer/browser

### Browser Storage
Data also auto-saves to your browser's localStorage. This means:
- If you close and reopen the page, data is still there
- Data is tied to this browser on this device
- Clearing browser data will erase it

### Manual Backup (Advanced)
```javascript
// In browser console, run:
copy(localStorage.getItem('org_chart_people'))
```

To restore:
```javascript
localStorage.setItem('org_chart_people', 'PASTE_JSON_HERE')
location.reload()
```
```javascript
const data = JSON.parse('PASTE_BACKUP_HERE');
localStorage.setItem('org_chart_company_name', data.company);
localStorage.setItem('org_chart_role_types', data.types);
localStorage.setItem('org_chart_people', data.people);
location.reload();
```

## Deploy to GitHub Pages

1. Fork or create a new GitHub repo
2. Push this code:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOURNAME/accountability-chart.git
   git push -u origin main
   ```
3. Go to Settings → Pages → Source: Deploy from branch → main
4. Your site will be at `https://YOURNAME.github.io/accountability-chart/`

## Tech Stack

- Vanilla HTML5
- CSS3 with CSS variables for dynamic colors
- Vanilla JavaScript (no frameworks)
- LocalStorage API
- No build step, no dependencies

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge).
