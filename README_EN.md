# 📅 Course Schedule Manager

A comprehensive, ready-to-use course schedule management tool. Fully standalone, no server required - just double-click to use.

## 🎯 Introduction

This is a course schedule management system designed specifically for students to easily manage course schedules, assignment deadlines, exam times, and personal activities. The system supports bilingual interfaces (Chinese/English), provides multiple view modes, and supports importing course information from syllabi with one-click export to calendar applications.

**Tech Stack:** Alpine.js + Tailwind CSS + Pure JavaScript (no build tools)

**Data Storage:** Browser localStorage (all data stored locally)

**Compatibility:** Modern browsers (Chrome, Firefox, Safari, Edge)

---

## 🚀 Quick Start

### Installation & Running

1. **Download Files**
   - Extract the `package` folder
   - Locate the `standalone.html` file

2. **Launch Application**
   - **Method 1:** Double-click the `standalone.html` file
   - **Method 2:** Right-click the file → "Open with" → Select browser
   - **Method 3:** Open browser → File → Open File → Select `standalone.html`

3. **First Use**
   - The application will automatically show a loading screen on first open
   - After loading, it will automatically enter the Dashboard view
   - It's recommended to set up term information first (Settings → Term Settings)

### System Requirements

- **Operating System:** Windows, macOS, Linux (any system with a browser)
- **Browser:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Internet Connection:** Required for first load (to load CDN resources), can use offline for most features afterward

---

## ✨ Core Features

### 1. 📊 Dashboard

The Dashboard is the home page, providing a one-stop overview.

**Features:**

- **Today's Important Events**
  - Automatically displays all important events for today (exams, assignment deadlines, etc.)
  - Highlighted in red to prevent missing important items

- **This Week Schedule**
  - Shows all course schedules for the current week
  - Includes course name, time, location, delivery method (online/in-person)
  - Automatically filtered by current date

- **Upcoming Events (Next 14 Days)**
  - Displays all important events in the next 14 days
  - Includes exams, assignment deadlines, personal activities, academic calendar events
  - Sorted chronologically with important events prioritized

### 2. 📚 Course Management

#### Add Course

1. Click the **"+ Add Course"** button in the navigation bar
2. Fill in course information:
   - **Course Name:** e.g., "ITC 535"
   - **Course Number:** e.g., "001"
   - **Section:** e.g., "001"
   - **Instructor:** Optional
   - **Location:** e.g., "Glass Hall 467"
   - **Online:** Check if it's an online course
   - **Meeting Times:** Click "+ Add Meeting" to add class times
     - Day: Select Monday through Sunday
     - Start Time: e.g., "09:30"
     - End Time: e.g., "10:45"
   - **Office Hours:** Optional, click "+ Add Office Hour" to add
3. Click **"Save Course"** to save

#### Edit Course

1. Find the course you want to edit in the Schedule view
2. Click the **"Edit"** button
3. Make changes and click **"Save Course"**

#### Delete Course

1. Find the course you want to delete in the Schedule view
2. Click the **"Delete"** button
3. Confirm deletion (Note: Deleting a course will also delete all events associated with that course)

### 3. 📅 Schedule

The Schedule view provides two viewing modes:

#### Table View

- Displays detailed information for all courses
- Columns include: Course Name, Section, Location, Days of Week, Time, Instructor
- Supports online/in-person indicators
- Can edit and delete courses directly from the table

#### Calendar View

- Shows course schedules by week
- Intuitive display of daily class times
- Different courses are color-coded
- Supports left/right navigation to view different weeks

### 4. 🗓️ Calendar

A complete calendar view displaying all events.

**Features:**

- **Monthly View:** Shows all events for the entire month
- **Event Types:**
  - Classes (Blue)
  - Exams (Red)
  - Assignment Deadlines (Blue)
  - Personal Activities (Green)
  - Academic Calendar Events (Orange)
  - Holidays (Orange)
- **Navigation:** Supports forward/backward month navigation
- **Filtering:** Can filter by different event types

### 5. 📋 All Events (Comprehensive Events View)

Displays a complete list of all events.

**Event Types:**

- **CLASS:** Regular course schedules
- **EXAM:** Exam schedules
- **QUIZ:** Quiz schedules
- **ASSIGNMENT:** Assignment deadlines
- **PROJECT:** Project deadlines
- **PRESENTATION:** Presentation times
- **LAB:** Lab sessions
- **INFO:** General information
- **HOLIDAY:** Holidays
- **DEADLINE:** Other deadlines

**Operations:**

- **Edit Event:** Click an event to edit
- **Delete Event:** Click "Delete" to remove
- **Filtering:** Can filter by type, course, date range

### 6. 📤 Syllabus Planner

This is one of the core features of the system. It can intelligently parse syllabus text and automatically extract course events.

#### Usage Steps

1. **Prepare Syllabus Text**
   - Copy syllabus content from Canvas, Blackboard, or other LMS systems
   - Or copy text from PDF documents
   - Ensure dates and times are included

2. **Paste and Parse**
   - Click the **"Course Schedule Planner"** button in the navigation bar
   - Paste the syllabus text into the text box
   - Click the **"Parse Text"** button to start parsing

3. **Review and Confirm**
   - The system will display parsing results (Candidates)
   - Each candidate event shows:
     - **Title:** Extracted event name
     - **Date & Time:** Extracted date and time
     - **Type:** Automatically identified type (EXAM, ASSIGNMENT, etc.)
     - **Confidence:** Reliability of parsing (0-1)
     - **Needs Review:** Flagged events that require manual confirmation
     - **Original Snippet:** Original text from which it was extracted
   - Review each event, you can edit date, time, title
   - Check the events you want to save
   - Click **"Confirm Selected"** to save

4. **Advanced Features**
   - **Select Course:** Can associate events with specific courses
   - **Batch Edit:** Supports batch modification of event types
   - **Preview:** Can preview all events before saving

#### Parsing Capabilities

The system supports recognizing the following date and time formats:

**Date Formats:**
- "February 15, 2026"
- "Feb 15, 2026"
- "2/15/2026" or "02/15/2026"
- "15 Feb 2026"
- Date ranges: "March 9-17, 2026"

**Time Formats:**
- "11:59 PM" or "11:59PM"
- "23:59" (24-hour format)
- "5pm" or "5 pm"
- "8:00 AM" or "8:00AM"
- "noon" (12:00 PM)
- "midnight" (00:00 AM)
- "by 11:59 PM" (deadline time)

**Special Keywords:**
- "Due", "Deadline", "Submit by" → Recognized as deadlines
- "Exam", "Midterm", "Final", "Test" → Recognized as exams
- "Quiz" → Recognized as quizzes
- "Spring Break", "No Class" → Recognized as holidays/non-class days

#### Templates and Guidelines

The system provides syllabus templates (click "Guide/Template" button). Recommended format:

```
ASSIGNMENT DUE: Chapter 11 (February 15, 11:59 PM)
Quiz 1 (Feb 3, 8:00 AM)
Midterm Exam (March 7, noon)
Project due (April 1, midnight)
Spring Break (March 9–17) – No Class
Final Exam Period (May 4–9)
```

**Recommendations:**
- Include dates for each important event
- If time exists, include it in the same line in parentheses: `(February 15, 11:59 PM)`
- Avoid using UTC/Z/timezone suffixes
- Use standard date formats (Month/Day/Year or Month Day, Year)

### 7. 📝 Personal Activities

Manage personal schedules and activities.

#### Add Personal Activity

1. **Method 1: Quick Add**
   - In Dashboard or All Events view
   - Use the quick add text box
   - Enter simple text, e.g., "Team meeting tomorrow 3pm"
   - The system will attempt to parse date and time

2. **Method 2: Full Form**
   - Click **"+ Add Personal Activity"** button
   - Fill in complete information:
     - Title
     - Date & Time
     - All Day
     - Category
     - Description

3. **Use Templates**
   - System provides common activity templates
   - Examples: "Study Group", "Office Hours", "Project Meeting"
   - Click template to quickly create similar activity

#### Edit and Delete

- Find personal activities in All Events view
- Click event to edit
- Click "Delete" to remove

### 8. ⚙️ Settings

#### Term Settings

**Importance:** Must set term information correctly. The system automatically processes events based on term dates.

1. **Term Name:** e.g., "Spring 2026"
2. **Start Date:** Term start date
3. **End Date:** Term end date
4. **Timezone:** Default "America/Chicago" (US Central Time)

**Note:**
- Term dates are used for:
  - Automatically filtering events within the term
  - Inferring year during syllabus parsing
  - Displaying academic calendar events
- If term is not set, some features may not work properly

#### Theme

The system provides two themes:

- **Marble:** Elegant gradient background with glass morphism effects
- **Default:** Clean white background

Click theme button to switch.

#### Language

Supports Chinese/English switching:

- **中文 (Chinese):** Complete Chinese interface
- **English:** Complete English interface

Click language button to switch. Changes take effect immediately.

### 9. 📥 Export Calendar

Export course schedules and events as ICS format, can be imported into Google Calendar, Apple Calendar, Outlook, and other calendar applications.

#### Usage Steps

1. Click the **"Export Calendar"** button in the navigation bar
2. System will automatically generate ICS file
3. Download the file (usually named `course_schedule.ics`)
4. Import into calendar application:
   - **Google Calendar:** Create new calendar → Import → Select ICS file
   - **Apple Calendar:** File → Import → Select ICS file
   - **Outlook:** File → Open and Export → Import/Export → Import from file

#### Export Contents

- ✅ All course schedules (Course Meetings)
- ✅ All assignment deadlines (Assignment Deadlines)
- ✅ All exam times (Exam Times)
- ✅ All personal activities (Personal Activities)
- ✅ Academic calendar events (Academic Calendar Events)
- ✅ Timezone information (America/Chicago)

#### Notes

- Exported times use local timezone (America/Chicago)
- All-day events are correctly marked
- Recurring events (like weekly classes) are exported as separate events

### 10. 🏫 Academic Calendar

The system integrates MSU (Missouri State University) academic calendar, automatically displaying:

- **Important Term Dates:**
  - Term start/end dates
  - Registration dates
  - Drop deadline dates
  - Midterm exam week
  - Final exam week
  - Spring/Fall breaks
  - Holidays

- **Final Exam Schedule:**
  - Automatically calculates final exam times based on course meeting times and days
  - Supports special course final exam rules (e.g., math courses)
  - Automatically displayed in Dashboard and Calendar views

**Note:** Academic calendar data is built into the system and requires no additional configuration.

---

## 🎨 Interface Features

### Navigation Bar

Top navigation bar includes:

- **Logo and Title:** Displays application name in current language
- **Language Toggle:** 中文 / English
- **Main Navigation Menu:**
  - Home: Return to Dashboard
  - Schedule: View term schedule
  - Calendar: View calendar
  - All Events: View all events list
  - Settings: Open settings page
- **Action Buttons:**
  - + Add Course
  - Course Schedule Planner
  - Export Calendar

### Event Color Coding

Different event types are color-coded:

- **EXAM:** Red border, red background
- **QUIZ:** Amber border, amber background
- **ASSIGNMENT:** Blue border, blue background
- **PROJECT:** Purple border, purple background
- **PRESENTATION:** Indigo border, indigo background
- **LAB:** Green border, green background
- **CLASS:** Blue border, blue background
- **INFO:** Sky blue border, sky blue background
- **HOLIDAY:** Orange border, orange background
- **DEADLINE:** Rose border, rose background

### Responsive Design

- **Desktop:** Full features, multi-column layout
- **Tablet:** Adaptive layout
- **Mobile:** Responsive design, core features available

---

## 💾 Data Management

### Data Storage

- **Storage Location:** Browser localStorage (local storage)
- **Stored Content:**
  - Course information (Courses)
  - Event information (Events)
  - Personal activities (Personal Activities)
  - Term settings (Term Settings)
  - Theme preference (Theme Preference)
  - Language preference (Language Preference)

### Data Backup

**Important:** localStorage data may be lost due to:

- Clearing browser cache
- Using browser's "Clear Data" function
- Using privacy/incognito mode (data cleared after closing)
- Browser crash or reinstall

**Recommendations:**

1. **Regular Export Backups:**
   - Use "Export Calendar" feature regularly to export ICS files
   - Save to cloud or local backup

2. **Export Settings:**
   - Screenshot term settings
   - Manually record important course details

3. **Multi-Browser Sync:**
   - Use same export files across different browsers
   - Or use browser sync feature (if localStorage sync is supported)

### Data Import

Currently, direct data import is not supported, but you can restore via:

1. **Re-add Courses:** Manually re-add course information
2. **Re-parse Syllabus:** If you have syllabus text, you can re-parse
3. **From Exported ICS File:** Can view ICS file content as reference

---

## 🔧 Troubleshooting

### Common Issues

#### 1. Blank Page or Continuous Loading

**Possible Causes:**
- Network connection issues (first load requires network)
- Browser cache issues
- JavaScript disabled

**Solutions:**
- Check network connection
- Clear browser cache and reload
- Check browser settings, ensure JavaScript is enabled
- Try using a different browser

#### 2. Language Switch Not Working

**Possible Causes:**
- Browser doesn't support localStorage
- Language button not triggering correctly

**Solutions:**
- Refresh the page
- Check browser console for errors
- Try manually entering in browser console: `localStorage.setItem('lang', 'zh')` or `localStorage.setItem('lang', 'en')`

#### 3. Syllabus Parsing Inaccurate

**Possible Causes:**
- Syllabus text format is non-standard
- Date/time format is non-standard
- Text contains too much irrelevant information

**Solutions:**
- Use system-provided template format
- Clean syllabus text, remove irrelevant content
- Ensure date and time formats are standard (see format instructions above)
- Manually edit inaccurate items in parsing results

#### 4. Exported Calendar Times Incorrect

**Possible Causes:**
- Term timezone setting is incorrect
- System timezone doesn't match term timezone

**Solutions:**
- Check timezone setting in Settings (default should be America/Chicago)
- Ensure correct timezone is selected when importing into calendar application
- Check timezone information in exported ICS file

#### 5. Data Loss

**Possible Causes:**
- Cleared browser cache
- Used privacy mode
- Browser update or reinstall

**Solutions:**
- Regularly use "Export Calendar" feature for backup
- Avoid using in privacy mode
- Use browser sync feature (if supported)

#### 6. Some Features Not Working

**Possible Causes:**
- Term information not set
- Browser doesn't support certain APIs
- JavaScript errors

**Solutions:**
- First check if term settings in Settings are correct
- Check browser console for error messages
- Try refreshing the page
- Use modern browser (Chrome, Firefox, Safari, Edge)

### Browser Compatibility

**Recommended Browsers:**
- ✅ Chrome 90+ (best compatibility)
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

**Not Recommended:**
- ⚠️ Internet Explorer (no longer supported)
- ⚠️ Older browsers (may not support some features)

### Performance Optimization Tips

1. **Reduce Event Count:** If there are too many events (>1000), it may affect performance
2. **Regular Cleanup:** Delete expired events and courses
3. **Use Filtering:** Use filter feature to view specific events instead of showing all events

---

## 📚 Tips & Best Practices

### 1. Pre-Term Preparation

- ✅ Set term information (start date, end date)
- ✅ Import all courses (manually add or import from syllabus)
- ✅ Set course meeting times and locations
- ✅ Import syllabus and parse all important events

### 2. Daily Use

- ✅ Check Dashboard every morning to see today's important events
- ✅ Regularly check Upcoming Events to prepare in advance
- ✅ Promptly add new personal activities and deadlines
- ✅ Use filter feature to quickly find specific courses or events

### 3. Syllabus Parsing Best Practices

- ✅ Use system-provided template format when writing syllabus
- ✅ Ensure each important event includes clear date and time
- ✅ Carefully review all results after parsing, especially events marked "Needs Review"
- ✅ For inaccurate events, manually edit before saving

### 4. Data Management

- ✅ Regularly export backups (recommended weekly)
- ✅ Export complete data as record after term ends
- ✅ Manually record important events elsewhere (paper or cloud notes)

### 5. Multi-Device Use

- ✅ Use same browser on different devices
- ✅ Regularly sync data (via export/import)
- ✅ Or use browser sync feature (if localStorage sync is supported)

---

## 🔒 Privacy & Security

### Data Privacy

- ✅ **Local Storage:** All data is stored only in your browser locally, never uploaded to any server
- ✅ **No Login Required:** System doesn't require any account or login information
- ✅ **No Tracking:** System contains no tracking code or analytics tools (except necessary CDN resources)

### Security Recommendations

- ⚠️ **Don't Use on Public Computers:** If using public computers, clear browser data after use
- ⚠️ **Protect Your Data:** Regularly backup important data
- ⚠️ **Share Cautiously:** If you export ICS files to share with others, ensure no sensitive information is included

---

## 🆘 Getting Help

### Having Issues?

1. **Check This Document:** First check the troubleshooting section of this document
2. **Check Browser Console:** Press F12 to open developer tools, check Console tab for error messages
3. **Contact Developer:** If you find issues or have feature suggestions, contact the developer

### Feature Requests

If you have feature improvement suggestions, feedback is welcome:
- New feature requests
- Interface improvement suggestions
- Bug reports
- Usage experience feedback

---

## 📝 Changelog

### Current Version

- ✅ Complete course management functionality
- ✅ Intelligent syllabus parsing
- ✅ Bilingual support (Chinese/English)
- ✅ Theme switching
- ✅ ICS calendar export
- ✅ MSU academic calendar integration
- ✅ Automatic final exam calculation
- ✅ Multiple view modes (Dashboard, Schedule, Calendar, All Events)
- ✅ Personal activity management
- ✅ Responsive design

---

## 🙏 Acknowledgments

Thank you for using this Course Schedule Management System!

This system is designed specifically for students to help you better manage your studies and life.

**Good luck with your studies!** 🎓

---

**Version:** 1.0  
**Last Updated:** January 2026  
**License:** For personal and educational use only

Made with ❤️ for Students
