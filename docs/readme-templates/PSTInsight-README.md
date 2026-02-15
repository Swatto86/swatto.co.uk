# PSTInsight

A desktop application for viewing and exporting emails from Outlook PST (Personal Storage Table) files without requiring Microsoft Outlook to be installed.

![Platform](https://img.shields.io/badge/platform-Windows-blue)
![Language](https://img.shields.io/badge/language-C%23-239120)
![Framework](https://img.shields.io/badge/framework-WPF-512BD4)
![License](https://img.shields.io/badge/license-MIT-green)

## Overview

PSTInsight is a standalone PST file viewer that allows you to browse and export emails from Outlook PST files. Built with C# and WPF, it provides a modern dark-themed interface with folder tree navigation and email preview functionality.

## Features

- **No Outlook Required** - View PST files without installing Microsoft Outlook
- **Folder Tree Navigation** - Browse the folder hierarchy of your PST file
- **Email Preview** - View email content, subject, sender, recipients, and date
- **Email Export** - Export individual emails or entire folders
- **Dark Theme** - Modern, eye-friendly dark interface
- **Attachment Support** - View and save email attachments
- **Search Functionality** - Find emails by subject, sender, or content
- **Fast Loading** - Efficient PST file parsing and display
- **Portable** - Single executable, no installation required

## Requirements

- Windows 10 or later
- .NET Framework 4.7.2 or later (pre-installed on Windows 10+)

## Installation

### Download

Download the latest release from the [Releases](https://github.com/Swatto86/PSTInsight/releases) page.

### Build from Source

```bash
git clone https://github.com/Swatto86/PSTInsight.git
cd PSTInsight

# Open in Visual Studio
start PSTInsight.sln

# Or build from command line
msbuild PSTInsight.sln /p:Configuration=Release
```

## Usage

### Opening a PST File

1. Launch PSTInsight
2. Click "Open PST File" or drag and drop a .pst file onto the window
3. Wait for the file to load (progress is shown in the status bar)
4. Browse folders in the tree view on the left

### Viewing Emails

1. Navigate to a folder in the tree view
2. Click on a folder to see its emails in the list
3. Click on an email to view its content in the preview pane
4. Attachments are listed at the bottom of the preview

### Exporting Emails

**Export Single Email:**
1. Select an email in the list
2. Click "Export Email"
3. Choose format (MSG, EML, or TXT)
4. Select save location

**Export Folder:**
1. Right-click a folder in the tree view
2. Select "Export Folder"
3. Choose format and destination
4. All emails in the folder will be exported

### Working with Attachments

1. View attachments in the preview pane
2. Click on an attachment to:
   - Open in default application
   - Save to disk
   - View properties (name, size, type)

## Use Cases

- **Email Archiving** - Browse old PST archives without Outlook
- **Email Recovery** - Access emails from backups or old systems
- **Email Migration** - Export emails for migration to other systems
- **Legal Discovery** - Review email archives for compliance or litigation
- **Mailbox Analysis** - Examine PST file contents and structure
- **Email Forensics** - Investigate email files in a standalone environment
- **Offline Access** - View emails without connecting to Exchange/Office 365

## Features in Detail

### Dark Theme UI

PSTInsight features a carefully designed dark theme that:
- Reduces eye strain during extended use
- Provides clear contrast for readability
- Uses modern WPF styling and animations
- Supports high-DPI displays

### Folder Tree Navigation

The folder tree displays:
- All folders in hierarchical structure
- Folder icons indicating type (Inbox, Sent Items, etc.)
- Email count per folder
- Expandable/collapsible nodes
- Right-click context menus

### Email List View

The email list shows:
- Subject line
- Sender name and email
- Date and time
- Read/unread status
- Attachment indicator
- Sortable columns
- Quick search filtering

### Email Preview

The preview pane displays:
- Full email headers (From, To, CC, BCC, Date, Subject)
- Email body (HTML or plain text)
- Attachment list with file sizes
- Properly rendered HTML emails
- Inline images (when present)

## Technical Details

### Built With

- **C# 8.0** - Modern C# language features
- **WPF** - Windows Presentation Foundation for rich UI
- **MAPI** - Messaging API for PST file access
- **.NET Framework 4.7.2** - Target framework

### PST File Format Support

PSTInsight supports:
- **PST File Types**: ANSI PST (older format), Unicode PST (newer format)
- **Outlook Versions**: Compatible with PST files from Outlook 97 through latest
- **File Size**: Handles large PST files (up to 50GB)
- **Encoding**: UTF-8, Unicode, and legacy encodings

### Architecture

```
┌─────────────────┐
│   WPF UI Layer  │ ◄── User Interface (XAML + Code-behind)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Business Logic │ ◄── Email parsing, searching, exporting
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  PST Reader     │ ◄── MAPI-based PST file access
└─────────────────┘
```

### Dependencies

PSTInsight uses minimal external dependencies:
- **Microsoft.Office.Interop.Outlook** (optional) - For enhanced PST reading
- Native MAPI implementation for core functionality
- .NET Framework standard libraries

## Performance

- **Fast Loading**: Lazy-loads folder contents for quick startup
- **Efficient Memory**: Streams large emails rather than loading entirely
- **Responsive UI**: Asynchronous operations keep the UI responsive
- **Smart Caching**: Caches frequently accessed folders

## Limitations

- **Windows Only**: Uses Windows-specific APIs (WPF, MAPI)
- **Read-Only**: Does not support modifying PST files
- **Email Formats**: Exports to MSG, EML, or TXT (not back to PST)
- **Large Files**: Very large PST files (>50GB) may be slow to load

## Troubleshooting

### Cannot Open PST File

If you receive an error opening a PST file:
- Ensure the PST file is not corrupted (use Outlook's scanpst.exe if needed)
- Check that the file is not locked by another application
- Verify you have read permissions for the file
- Ensure the file path contains no special characters

### Slow Performance

For large PST files:
- Be patient during initial loading
- Use search to find specific emails rather than browsing
- Close other applications to free up memory
- Consider splitting very large PST files

### Missing Emails

If emails appear to be missing:
- Check folder filters or search criteria
- Verify the PST file isn't corrupted
- Ensure the folder contains items (check folder count)
- Try refreshing the folder view

## Privacy & Security

- **Local Processing**: All PST reading is done locally - no cloud uploads
- **No Telemetry**: PSTInsight does not collect or transmit user data
- **Read-Only**: Cannot modify PST files, ensuring data integrity
- **Secure**: No network access required or used

## Development

### Prerequisites

- Visual Studio 2019 or later
- .NET Framework 4.7.2 SDK
- Windows 10 SDK

### Building

```bash
# Restore NuGet packages
nuget restore PSTInsight.sln

# Build debug
msbuild PSTInsight.sln /p:Configuration=Debug

# Build release
msbuild PSTInsight.sln /p:Configuration=Release
```

### Project Structure

```
PSTInsight/
├── PSTInsight/
│   ├── Views/              # WPF windows and user controls
│   ├── ViewModels/         # MVVM view models
│   ├── Models/             # Data models (Email, Folder, etc.)
│   ├── Services/           # PST reading, export services
│   ├── Converters/         # XAML value converters
│   ├── Resources/          # Images, icons, styles
│   └── App.xaml            # Application entry point
├── PSTInsight.Tests/       # Unit tests
└── README.md
```

### Testing

```bash
# Run unit tests
dotnet test

# Run with coverage
dotnet test /p:CollectCoverage=true
```

## Roadmap

Future enhancements planned:

- [ ] Advanced search with filters (date range, sender, etc.)
- [ ] Bulk export with progress tracking
- [ ] Email statistics and analytics
- [ ] Calendar and contact support
- [ ] PST file comparison tool
- [ ] Duplicate email detection
- [ ] Email threading view
- [ ] Export to MBOX format
- [ ] Light theme option

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Write or update tests
5. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Swatto** - [GitHub](https://github.com/Swatto86) | [Website](https://swatto.co.uk)

## Acknowledgments

- Thanks to the open-source PST libraries community
- WPF community for UI/UX best practices
- Users who provided feedback and feature requests

## Support

- **Issues**: Report bugs via [GitHub Issues](https://github.com/Swatto86/PSTInsight/issues)
- **Questions**: Check existing issues or create a new discussion
- **Website**: Visit [swatto.co.uk](https://swatto.co.uk) for more tools

---

*Part of the [Swatto Tools](https://swatto.co.uk) collection - Desktop tools that get things done*
