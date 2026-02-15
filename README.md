# swatto.co.uk

Landing page for my utilities — Desktop tools that get things done.

**Live site:** [swatto.co.uk](https://swatto.co.uk)

## Overview

This is a static GitHub Pages site showcasing my collection of open-source desktop tools and utilities. The site features modern desktop applications built with Rust, Tauri, C#, and other technologies, primarily targeting Windows system administrators and power users.

## About This Repository

This repository contains the source code for the [swatto.co.uk](https://swatto.co.uk) landing page, which serves as a portfolio and download hub for various desktop utilities.

### Technology Stack

- **Static Site**: HTML5, CSS3, JavaScript
- **Hosting**: GitHub Pages
- **Deployment**: Automatic (push to main branch)
- **Custom Domain**: swatto.co.uk

## Featured Projects

The website showcases the following categories of tools:

### Server Management
- **QuickProbe** - Windows/Linux server monitoring with RDP integration
- **QuickConnect** - RDP connection manager with AD integration

### Analysis Tools
- **EventSleuth** - Modern Windows Event Log viewer
- **DiskSleuth** - Visual disk space analyzer with treemap visualization

### Security & Privacy
- **BitBurn** - Secure file wiping utility
- **ChecksumCheck** - File checksum calculator and verifier
- **SwatCrypt** - XChaCha20-Poly1305 file encryption

### System Utilities
- **HandleHunter** - File lock viewer and manager
- **LockSmith** - File lock management with egui
- **Tea** - System sleep prevention utility
- **QuickRun** - Windows Run-style launcher

### Productivity
- **SwatNotes** - Rich text notes with encrypted backups
- **PSTInsight** - Outlook PST file viewer

### Developer Tools
- **ps-launcher** - Silent PowerShell script launcher

For detailed information about each tool, visit the [live site](https://swatto.co.uk).

## Repository Status

| Repository | README | Status |
|------------|--------|--------|
| QuickProbe | ✅ | Complete |
| QuickConnect | ✅ | Complete |
| EventSleuth | ⚠️ | Missing README |
| DiskSleuth | ✅ | Complete |
| BitBurn | ✅ | Complete |
| ChecksumCheck | ✅ | Complete |
| SwatNotes | ✅ | Complete |
| Tea | ✅ | Complete |
| QuickRun | ✅ | Complete |
| HandleHunter | ✅ | Complete |
| LockSmith | ✅ | Complete |
| PSTInsight | ⚠️ | Missing README |
| SwatCrypt | ✅ | Complete |
| ps-launcher | ✅ | Complete |

**Note**: EventSleuth and PSTInsight repositories require README files to be added.

## Local Development

To work on the site locally:

```bash
# Clone the repository
git clone https://github.com/Swatto86/swatto.co.uk.git
cd swatto.co.uk

# Open index.html in a browser
# Or use a local server:
python -m http.server 8000
# Then navigate to http://localhost:8000
```

## Deployment

Changes pushed to the main branch are automatically deployed to [swatto.co.uk](https://swatto.co.uk) via GitHub Pages.

```bash
git add .
git commit -m "Update content"
git push origin main
```

## File Structure

```
swatto.co.uk/
├── index.html              # Main landing page
├── README.md               # This file
├── LICENSE                 # MIT License
├── CNAME                   # Custom domain configuration
├── _config.yml             # Jekyll configuration
├── favicon.ico             # Site favicon
├── favicon.svg             # SVG favicon
├── favicon-32x32.png       # 32x32 favicon
├── icon.png                # Apple touch icon
├── icon.svg                # SVG icon
├── robots.txt              # Search engine directives
├── sitemap.xml             # Site map for SEO
├── FSAnalyser-Overview.html           # Project overview pages
├── FSAnalyser-ReportExample.html
└── SharedScope-Overview.html
```

## Contributing

This is a personal portfolio site, but suggestions and bug reports are welcome via issues.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Swatto** - [GitHub](https://github.com/Swatto86)

---

*Built with ❤️ for system administrators and power users*
