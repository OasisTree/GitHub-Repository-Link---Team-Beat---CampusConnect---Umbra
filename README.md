# CampusConnect – Student Engagement Portal

A modern, feature-rich student engagement platform built with Python and Tkinter that enables seamless communication and collaboration between students, organizations, and administrators.

---

## 🎯 Overview

CampusConnect is a comprehensive desktop application designed to streamline campus life by providing a centralized hub for:
- **Event Management**: Create, view, and manage campus events
- **Student Engagement**: Connect students with campus organizations and activities
- **Group Coordination**: Organize teams and group activities
- **Direct Messaging**: Real-time communication between users
- **Attendance Tracking**: Monitor event attendance and participation
- **Form Management**: Collect feedback and form responses
- **Notifications**: Real-time alerts and updates
- **Role-Based Dashboards**: Customized interfaces for students, organizations, and administrators

---

## ✨ Key Features

### 🔐 Authentication & User Management
- Secure login and registration system
- Password hashing with SHA256
- Three user roles: Student, Organization, Administrator
- Unique user IDs and session management

### 📅 Event Management
- Create and publish campus events
- Event categorization (Academic, Environmental, Community, etc.)
- Event filtering and search
- Attendance tracking
- Event-specific forms and RSVPs

### 👥 Organization & Groups
- Create and manage student organizations
- Form interest groups and teams
- Member management
- Organization-specific dashboards

### 💬 Messaging System
- Direct messaging between users
- Message history
- Real-time notifications

### 📊 Dashboards
- **Student Dashboard**: View events, join groups, access personalized content
- **Organization Dashboard**: Manage events, forms, and members
- **Admin Dashboard**: System-wide management and oversight

### 🔔 Notification System
- Real-time notifications
- Multiple notification types (info, warning, success, error)
- Notification history
- Read/unread status tracking

### 📋 Forms & Responses
- Create custom forms
- Collect user responses
- Response analytics

---

## 🛠️ Technology Stack

| Technology | Purpose |
|-----------|---------|
| **Python 3.x** | Core application language |
| **Tkinter** | GUI framework (modern dark theme) |
| **JSON** | Data persistence |
| **SHA256** | Password encryption |
| **UUID** | Unique identifiers |

---

## 📂 Project Structure

```
CampusConnect/
├── app.py                    # Main application entry point
├── camp.py                   # Secondary app entry point
├── README.md                 # This file
│
├── core/                     # Core functionality modules
│   ├── __init__.py
│   ├── database.py          # JSON data persistence layer
│   ├── theme.py             # Color scheme and fonts
│   └── utils.py             # Utility functions
│
├── screens/                  # Application screens/pages
│   ├── __init__.py
│   ├── login.py             # Login screen
│   ├── register.py          # Registration screen
│   ├── dashboards.py        # Admin dashboard
│   └── dashboards_extended.py # Student & Organization dashboards
│
├── ui/                       # UI components
│   ├── __init__.py
│   ├── widgets.py           # Custom Tkinter widgets
│   └── windows.py           # Dialog windows and popups
│
└── data/                     # JSON data files
    ├── users.json           # User accounts
    ├── events.json          # Campus events
    ├── forms.json           # Form templates
    ├── groups.json          # Student groups
    ├── messages.json        # Message history
    ├── attendance.json      # Attendance records
    ├── notifications.json   # User notifications
    └── responses.json       # Form responses
```

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.7 or higher
- Tkinter (usually included with Python)

### Steps

1. **Clone or download the repository**
   ```bash
   git clone <repository-url>
   cd CampusConnect
   ```

2. **No external dependencies required!**
   The application uses only Python standard library modules.

3. **Run the application**
   ```bash
   python app.py
   ```
   Or alternatively:
   ```bash
   python camp.py
   ```

---

## 👤 User Roles & Access

### Student
- View available events and organizations
- Join events and groups
- Receive notifications
- Participate in groups
- Send/receive messages
- Fill out forms

### Organization
- Create and manage events
- Create forms for event registration
- View member list
- Send announcements
- Manage organization profile

### Administrator
- Full system access
- View all users, events, and groups
- Generate reports
- System configuration
- User management

---

## 🎨 Design Features

### Dark Theme
The application features a modern dark theme inspired by GitHub's interface:
- **Primary Background**: `#0D1117`
- **Surface**: `#161B22`
- **Accent (Blue)**: `#58A6FF`
- **Supporting Colors**: Green (#3FB950), Red (#F85149), Yellow (#D29922), Purple (#BC8CFF)

### Responsive Layout
- Minimum window size: 1100x700
- Default size: 1320x820
- Scalable components

---

## 💾 Data Management

### JSON Storage
All data is stored in JSON files in the `data/` directory:
- User accounts and profiles
- Event information
- Form definitions and responses
- Group memberships
- Message history
- Attendance records
- User notifications

### Database Functions
```python
jload(path)      # Load JSON data from file
jsave(path, data) # Save data as JSON
hash_pw(pw)       # Hash passwords with SHA256
now_str()         # Get current timestamp
today()           # Get today's date
push_notif()      # Create user notifications
```

---

## 🔄 Application Flow

1. **Startup**: `app.py` initializes the Tkinter application
2. **Database Seed**: Initial data is seeded into `data/` directory
3. **Login Screen**: User authenticates or registers
4. **Dashboard**: User is directed to role-specific dashboard
5. **Navigation**: Users navigate between screens via menu options
6. **State Management**: `current_user` tracks active session

---

## 🛠️ Core Modules

### `core/database.py`
Handles all data persistence operations:
- JSON file I/O
- User authentication
- Timestamp generation
- Notification management

### `core/theme.py`
Centralized styling:
- Color definitions
- Font configurations
- Category color mapping

### `core/utils.py`
Utility functions for common operations

### `screens/login.py`
Login and registration interface with validation

### `screens/dashboards.py`
Administrator dashboard with system overview

### `screens/dashboards_extended.py`
Student and Organization dashboards with role-specific features

### `ui/widgets.py`
Reusable custom Tkinter widgets

### `ui/windows.py`
Dialog windows and popup components

---

## 📋 API Overview

### App Class Methods
```python
app._show(ScreenClass)   # Navigate to a screen
app.go_login()           # Go to login screen
app.go_register()        # Go to registration screen
app.go_dashboard()       # Go to role-specific dashboard
```

### Database Functions
```python
push_notif(user_id, text, kind="info")  # Send notification
hash_pw(password)                        # Hash password
now_str()                                # Current timestamp
today()                                  # Today's date
jload(path)                              # Load JSON
jsave(path, data)                        # Save JSON
```

---

## 🔒 Security Considerations

- Passwords are hashed using SHA256
- Session-based authentication via `current_user`
- Role-based access control
- No sensitive data in plain text

---

## 📝 Development Notes

### Adding New Features
1. Create screen in `screens/` directory
2. Inherit from Tkinter Frame
3. Use theme constants from `core/theme.py`
4. Implement `_show()` navigation from main App
5. Use database functions for data persistence

### Styling Guidelines
- Use color constants from `COLORS` dict
- Use predefined fonts from `FONTS` dict
- Follow dark theme convention
- Maintain consistent spacing and padding

### Testing
All functionality has been integrated into the main application. Test by:
1. Running the application
2. Creating test accounts
3. Creating events and forms
4. Testing role-based access

---

## 📞 Support

For issues, feature requests, or contributions, please contact the development team.

---

## 📄 License

This project is proprietary software. All rights reserved.

---

**Version**: 1.0.0  
**Last Updated**: April 2026  
**Status**: Active Development

