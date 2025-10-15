# Study Planner App

A comprehensive Flutter application for managing study tasks with calendar view, reminder system, and local data persistence.

## 📱 Features

### Core Functionality
- **Task Management**: Create, edit, and delete study tasks with title, description, due date, and optional reminders
- **Calendar View**: Monthly calendar with visual highlighting of dates containing tasks
- **Reminder System**: Popup alerts for upcoming and overdue tasks
- **Local Storage**: Data persistence using SharedPreferences with JSON serialization
- **Material Design**: Clean, consistent UI following Material Design principles

### Navigation
- **Bottom Navigation Bar** with three main screens:
  - **Today**: Displays tasks due today
  - **Calendar**: Monthly calendar view with task management
  - **Settings**: App preferences and storage information

### Task Features
- ✅ Required fields: Title and due date
- 📝 Optional fields: Description and reminder time
- ✏️ Edit existing tasks
- 🗑️ Delete tasks with confirmation
- ✅ Mark tasks as completed
- 🔔 Reminder notifications with popup dialogs

## 🏗️ Architecture

### Project Structure
```
lib/
├── main.dart                 # App entry point and main navigation
├── models/
│   └── task.dart            # Task data model with JSON serialization
├── services/
│   ├── storage_service.dart # Local storage management
│   └── task_service.dart    # Business logic for task operations
└── screens/
    ├── today_screen.dart    # Today's tasks display
    ├── calendar_screen.dart # Calendar view and date selection
    ├── settings_screen.dart # App settings and preferences
    └── add_edit_task_screen.dart # Task creation/editing form
```

### Key Components

#### Models
- **Task**: Data model with JSON serialization for local storage
  - Fields: id, title, description, dueDate, reminderTime, isCompleted
  - Helper methods: isDueToday, isOverdue, copyWith

#### Services
- **StorageService**: Handles all local storage operations using SharedPreferences
  - Save/load tasks as JSON
  - Manage notification settings
  - Store storage method information
- **TaskService**: Business logic layer for task operations
  - CRUD operations for tasks
  - Filter tasks by date
  - Manage notification settings
  - Check for overdue and upcoming tasks

#### Screens
- **TodayScreen**: Lists tasks due today with completion toggle and edit/delete options
- **CalendarScreen**: Monthly calendar grid with date highlighting and task selection
- **SettingsScreen**: App preferences, storage info, and statistics
- **AddEditTaskScreen**: Form for creating and editing tasks with date/time pickers

## 🚀 Setup Instructions

### Prerequisites
- Flutter SDK (>=3.0.0)
- Dart SDK
- Android Studio / VS Code with Flutter extensions
- Android emulator or physical device

### Installation
1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd muvunyi_individualassignment1
   ```

2. **Install dependencies**:
   ```bash
   flutter pub get
   ```

3. **Run the app**:
   ```bash
   flutter run
   ```

### Dependencies
The app uses the following key packages:
- `shared_preferences: ^2.2.2` - Local storage
- `intl: ^0.19.0` - Date formatting
- `cupertino_icons: ^1.0.2` - iOS-style icons

## 📱 Usage Guide

### Creating Tasks
1. Navigate to any screen and tap the **+** floating action button
2. Fill in the required title and due date
3. Optionally add a description and reminder time
4. Tap **Save** to create the task

### Managing Tasks
- **View Today's Tasks**: Use the Today tab to see all tasks due today
- **Calendar View**: Use the Calendar tab to see monthly overview and select specific dates
- **Edit Tasks**: Tap on any task to edit its details
- **Complete Tasks**: Use the checkbox to mark tasks as completed
- **Delete Tasks**: Use the menu button (⋮) to delete tasks

### Settings
- **Notifications**: Toggle reminder notifications on/off
- **Storage Info**: View current storage method and statistics
- **Data Management**: Refresh data or clear all stored information

## 🔧 Technical Implementation

### Data Persistence
- **Storage Method**: SharedPreferences with JSON serialization
- **Data Format**: Tasks stored as JSON array in local device storage
- **Persistence**: Data survives app restarts and device reboots

### Reminder System
- **Implementation**: Popup dialogs triggered when app starts
- **Checks**: Upcoming reminders (within 1 hour) and overdue tasks
- **Settings**: Can be disabled in Settings screen

### Material Design Implementation
- **Theme**: Amber color scheme with Material 3 design system
- **Components**: Scaffold, AppBar, ListTile, Card, BottomNavigationBar
- **Navigation**: Bottom navigation with proper state management
- **Responsive**: Works in both portrait and landscape orientations

## 🧪 Testing

### Manual Testing Checklist
1. **Task Creation**: Create tasks with various combinations of fields
2. **Data Persistence**: Close and reopen app to verify data is saved
3. **Calendar Navigation**: Navigate between months and select dates
4. **Task Management**: Edit, complete, and delete tasks
5. **Reminder System**: Create tasks with reminders and test popup alerts
6. **Settings**: Toggle notifications and view storage information

### Test Scenarios
- Create task without reminder → Verify no popup appears
- Create task with past due date → Verify overdue alert appears
- Disable notifications → Verify no reminder popups appear
- Clear all data → Verify all tasks are removed

## 📊 Features Implementation Status

### ✅ Completed Features
- [x] Task Management (CRUD operations)
- [x] Calendar View with date highlighting
- [x] Reminder System with popup alerts
- [x] Local Storage using SharedPreferences
- [x] Bottom Navigation with 3 screens
- [x] Settings with notification toggle
- [x] Material Design implementation
- [x] Data persistence across app restarts

### 🎯 Assignment Requirements Met
1. **Task Management**: ✅ Create tasks with title, description, due date, reminder
2. **Calendar View**: ✅ Monthly calendar with task highlighting and date selection
3. **Reminder System**: ✅ Popup alerts for reminders and overdue tasks
4. **Local Storage**: ✅ SharedPreferences with JSON serialization
5. **Navigation**: ✅ BottomNavigationBar with Today, Calendar, Settings
6. **Settings**: ✅ Notification toggle and storage information
7. **Material Design**: ✅ Clean UI with proper widgets and theming

## 🎥 Demo Video Content

The demo video should cover:
1. **App Overview**: Show the three main screens and navigation
2. **Task Creation**: Demonstrate creating tasks with all field types
3. **Calendar Usage**: Show calendar navigation and date selection
4. **Task Management**: Edit, complete, and delete tasks
5. **Reminder System**: Show reminder popups and settings
6. **Data Persistence**: Close/reopen app to show data is saved
7. **Settings**: Demonstrate notification toggle and storage info
8. **Code Walkthrough**: Explain key widgets and implementation details

## 📝 Code Quality Features

### Documentation
- Comprehensive code comments explaining functionality
- Clear method and class documentation
- README with setup and usage instructions

### Code Organization
- Modular structure with separate folders for models, services, screens
- Separation of concerns (UI, business logic, data persistence)
- Consistent naming conventions and formatting

### Error Handling
- Try-catch blocks for storage operations
- User feedback with SnackBar messages
- Graceful handling of edge cases

## 🔮 Future Enhancements

### Potential Improvements
- Background notifications using flutter_local_notifications
- SQLite database for more complex queries
- Task categories and tags
- Export/import functionality
- Dark theme support
- Widget tests and integration tests

---

**Developer**: Tony Lee Muvunyi  
**Assignment**: Individual Assignment 1 - Study Planner App  
**Framework**: Flutter with Material Design  
**Storage**: SharedPreferences (JSON)