#  AnnouncePro - Smart Announcement Scheduler

> An intelligent desktop application for scheduling and managing announcements with audio playback, built with Python and Tkinter.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/)
[![Status: Active](https://img.shields.io/badge/Status-Active-brightgreen)](https://github.com/amitkumar2308/announcepro)

---

##  Table of Contents

- [Overview](#overview)
- [Key Features](#-key-features)
- [Screenshots](#screenshots)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Key Components](#-key-components)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

##  Overview

**AnnouncePro** is a feature-rich desktop application designed for educational institutions, offices, and organizations to schedule and broadcast announcements efficiently. The application combines a robust backend scheduler with an intuitive GUI, allowing users to manage announcements with ease.

**Perfect for:**
-  Educational institutions
-  Corporate offices
-  Event management
-  Broadcasting announcements

---

##  Key Features

### Core Functionality
-  **Smart Scheduling**: Schedule announcements on specific dates and times
-  **Repeat Options**: Set announcements to run once or repeat daily
-  **Audio Playback**: Play MP3 and WAV audio files with announcement
-  **Volume Control**: Built-in system volume adjustment
-  **Playback Controls**: Play, pause, and stop functionality

### User Interface
-  **Modern GUI**: Clean, professional interface built with Tkinter
-  **Real-time Tables**: View current day and scheduled announcements at a glance
-  **Live Logs**: Monitor system activity with real-time log display
-  **File Browser**: Easy selection of audio files (MP3, WAV)

### Advanced Features
-  **Singleton Pattern Backend**: Efficient resource management
-  **Background Scheduling**: Uses APScheduler for reliable job scheduling
-  **Logging System**: Comprehensive logging for debugging and monitoring
-  **Professional Design**: Modern color scheme and responsive layout

---

##  Screenshots

The application features:
- **Main Dashboard** - Professional interface with multiple panels for easy management
- **Announcement Scheduler Panel** - Create announcements with date, time, and file selection
- **Control Panel** - Play, pause, and stop controls with volume adjustment
- **Announcement Tables** - View today''s and scheduled announcements
- **Live Activity Logs** - Real-time system monitoring

---

##  Tech Stack

| Category | Technology |
|----------|------------|
| **Language** | Python 3.6+ |
| **GUI Framework** | Tkinter |
| **Audio Processing** | Pygame mixer |
| **Task Scheduling** | APScheduler (BackgroundScheduler) |
| **Volume Control** | PyCaw (Python Core Audio Windows) |
| **Image Processing** | Pillow (PIL) |
| **Database** | MongoDB support (optional) |

---

##  Installation

### Prerequisites

``bash
# Python 3.6 or higher
python --version

# Windows, macOS, or Linux
# Git (for cloning the repository)
``

### Step 1: Clone the Repository

``bash
git clone https://github.com/amitkumar2308/announcepro.git
cd announcepro
``

### Step 2: Create Virtual Environment (Recommended)

``bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
``

### Step 3: Install Dependencies

``bash
pip install -r requirements.txt
``

**Required packages:**
- `pygame` - Audio playback
- `apscheduler` - Task scheduling
- `pycaw` - Windows audio control
- `pillow` - Image handling

### Step 4: Run the Application

``bash
python ui.py
``

---

##  Usage

### Creating an Announcement

1. **Enter Announcement Label**: Give your announcement a descriptive name
2. **Select Date**: Choose the date for the announcement (default: today)
3. **Select Time**: Set the time in HH:MM:SS format
4. **Choose Repeat Option**: Select "Once" for single occurrence or "Everyday" for daily repeat
5. **Browse Audio File**: Click "Browse" to select MP3 or WAV file
6. **Click "Add Schedule"**: Announcement is now scheduled!

### Managing Announcements

- **View Active**: Check "Current Day Announcements" table for today''s announcements
- **View All Scheduled**: See all upcoming announcements in "Scheduled Announcements" table
- **Update**: Select an announcement and click "Update" to modify details
- **Delete**: Remove announcements you no longer need
- **Monitor Logs**: View real-time system logs at the bottom of the screen

### Playback Controls

- **Play**: Test audio before scheduling
- **Pause**: Temporarily pause audio playback
- **Stop**: Stop the current playback
- **Volume**: Adjust system volume using the slider (0-100%)

---

##  Project Structure

``
announcepro/
 backend.py              # Core backend logic & scheduler
 ui.py                   # Main Tkinter GUI application
 announcepro.html        # HTML template for announcements
 index.html              # Download page website
 README.md               # Project documentation
 requirements.txt        # Python dependencies
 backend.log             # Application logs (generated at runtime)
 icons/                  # Application icons
     icons8-create-24.png
     icons8-calendar-24.png
     icons8-time-24.png
     icons8-repeat-24.png
     icons8-upload-file-24.png
``

---

##  Key Components

### `backend.py` - Backend Engine

**Features:**
- **Singleton Pattern**: Ensures only one instance of backend
- **Pygame Integration**: Handles audio file playback
- **APScheduler Integration**: Manages job scheduling
- **Logging**: Tracks all scheduled announcements
- **Error Handling**: Gracefully handles missing files and errors

**Key Methods:**
``python
- add_schedule(announcement, date, time, repeat, file_path)
   Schedules an announcement for specified date/time
  
- schedule_job(announcement, repeat, file_path)
   Executes scheduled announcement
  
- play_sound(file_path)
   Plays audio file using Pygame
``

### `ui.py` - User Interface

**Features:**
- **Modern Tkinter GUI**: Professional appearance with custom colors
- **Multiple Panels**: Organized layout for different functions
- **Real-time Tables**: Display announcements using Treeview widgets
- **Live Logs**: Monitor system activity in real-time
- **File Management**: Browse and select audio files easily

**Key Sections:**
- Title Bar with Logo
- Left Panel: Announcement creation
- Middle Panel: Playback controls & file selection
- Right Top: Current day announcements table
- Right Bottom: All scheduled announcements table
- Bottom: Action buttons (Update, Delete, Reset, Exit)
- Details: Live system logs

---

##  How It Works

### Scheduling Flow

``
User Input (Date/Time/Audio)
         
      Backend.add_schedule()
         
    APScheduler.add_job()
         
   Wait for scheduled time
         
schedule_job() Triggered
         
  Play audio file
         
   Log activity
``

### Real-time Monitoring

``
Scheduler runs in background
         
   Job executes at scheduled time
         
  Logs written to backend.log
         
UI monitors log file changes
         
Display updates automatically
``

---

##  Advanced Features

### Singleton Pattern
Ensures only one Backend instance exists throughout the application lifecycle, preventing resource conflicts.

### Background Scheduling
The APScheduler runs announcements without blocking the UI, allowing smooth user interaction.

### Dynamic Logging
Real-time log monitoring with automatic UI updates when new logs are generated.

### System Volume Control
Integrates with Windows audio system for precise volume management via PyCaw.

---

##  Contributing

Contributions are welcome! Help improve AnnouncePro:

### Steps to Contribute

1. **Fork the Repository**
   ``bash
   Click "Fork" on GitHub
   ``

2. **Clone Your Fork**
   ``bash
   git clone https://github.com/YOUR_USERNAME/announcepro.git
   cd announcepro
   ``

3. **Create Feature Branch**
   ``bash
   git checkout -b feature/AmazingFeature
   ``

4. **Make Changes**
   ``bash
   # Edit files and improve code
   ``

5. **Commit Changes**
   ``bash
   git commit -m "Add AmazingFeature: description"
   ``

6. **Push to Branch**
   ``bash
   git push origin feature/AmazingFeature
   ``

7. **Open Pull Request**
   - Go to GitHub and create a pull request
   - Describe your changes in detail
   - Wait for review and approval

### Development Guidelines
- Follow PEP 8 style guide
- Add comments for complex logic
- Test thoroughly before submitting PR
- Update documentation as needed

---

##  Future Enhancements

- [ ] Cross-platform support (Linux, macOS optimization)
- [ ] Database integration (MongoDB, SQLite)
- [ ] Email notification support
- [ ] SMS notifications
- [ ] Advanced scheduling (weekly, monthly patterns)
- [ ] Announcement templates
- [ ] User authentication
- [ ] Multi-user support
- [ ] API endpoint
- [ ] Mobile app companion

---

##  License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

``
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, and sublicense...
``

---

##  Contact & Support

**Developer:** Amit Kumar  
**GitHub:** [@amitkumar2308](https://github.com/amitkumar2308)  
**Email:** Open an issue on GitHub

### Get Help

-  **Report Bugs**: [Create an Issue](https://github.com/amitkumar2308/announcepro/issues)
-  **Ask Questions**: [GitHub Discussions](https://github.com/amitkumar2308/announcepro/discussions)
-  **Suggest Features**: [Feature Requests](https://github.com/amitkumar2308/announcepro/issues)

---

##  Acknowledgments

- **Tkinter** - Python GUI framework
- **Pygame** - Audio playback library
- **APScheduler** - Task scheduling library
- **PyCaw** - Windows audio control
- **Pillow** - Image processing

---

##  Project Statistics

- **Language**: Python
- **Framework**: Tkinter
- **Lines of Code**: 800+
- **Features**: 15+
- **License**: MIT

---

** If you find this project useful, please consider giving it a star on GitHub!**

---

*Last Updated: November 2025*
