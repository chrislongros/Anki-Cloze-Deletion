# Cloze-ChatGPT Anki Note Type

A modern, dark-themed Anki note type designed for medical students, featuring expandable resource hints and mobile-optimized display.

## Features

- 🌙 **Dark Theme** - Easy on the eyes during long study sessions
- 📚 **Expandable Resource Hints** - Quick access to UWorld, AMBOSS, First Aid, and more
- 📱 **Mobile Optimized** - Responsive design for AnkiDroid and AnkiMobile
- ⌨️ **Keyboard Shortcuts** - Fast navigation with hotkeys
- 🎨 **Color-Coded Resources** - Each resource type has its own color
- ✨ **Smooth Animations** - Polished hint expand/collapse animations

## Screenshots

*Add your screenshots here*

## Installation

### Method 1: Import .apkg file
1. Download the `.apkg` file from releases
2. Open Anki and go to File → Import
3. Select the downloaded file

### Method 2: Manual Installation
1. In Anki, go to Tools → Manage Note Types
2. Click "Add" and choose "Clone: Cloze"
3. Name it "Cloze-ChatGPT"
4. Click "Cards..." to open the card editor
5. Replace the Front Template with contents of `FRONT-TEMPLATE.html`
6. Replace the Back Template with contents of `BACK-TEMPLATE.html`
7. Replace the Styling with contents of `STYLING.css`

## Fields

This note type uses the following fields:

| Field | Description |
|-------|-------------|
| `Text` | Main cloze text content |
| `Extra` | Additional notes, explanations, mnemonics |
| `UWorld_3` | UWorld Step 3 explanations |
| `UWorld_2CK` | UWorld Step 2 CK explanations |
| `NEJM` | NEJM references |
| `AMBOSS` | AMBOSS content |
| `First_Aid` | First Aid references |
| `Kaplan` | Kaplan content |
| `Pathoma` | Pathoma explanations |
| `UpToDate` | UpToDate references |
| `NBME` | NBME content |
| `Additional_Resources` | Any other resources |

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `H` | Open next hint |
| `Shift + H` | Open all hints |
| `Ctrl/Cmd + H` | Close all hints |

## Customization

### Changing Colors

The cloze answer color can be changed in the CSS:
```css
.cloze { 
  color: #4caf50;  /* Change this hex code */
}
```

### Adding New Resource Types

1. Add a new field in Anki's note type editor
2. Add button in Back Template:
```html
{{#YourField}}<span class="pill yourclass" data-field="YourField"><a class="hint" href="javascript:void(0)">YourField</a></span>{{/YourField}}
```
3. Add template in Back Template:
```html
{{#YourField}}<template data-field="YourField">{{YourField}}</template>{{/YourField}}
```
4. Add color in CSS:
```css
.pill.yourclass a.hint { color: #yourcolor !important; }
.pill.yourclass a.hint.activeHint { background: rgba(r,g,b,.35) !important; }
```

## Compatibility

- ✅ Anki Desktop (Windows, macOS, Linux)
- ✅ AnkiDroid (Android)
- ✅ AnkiMobile (iOS)
- ✅ AnkiWeb

## Known Issues

- On some older AnkiDroid versions, text may wrap incorrectly. The included CSS fix addresses this for most cases.

## License

MIT License - feel free to modify and share!

## Contributing

Pull requests are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit improvements

## Acknowledgments

- Inspired by various medical Anki decks
- Built for the medical student community
