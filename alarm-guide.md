# Alarm Clock App - User Guide & Technical Documentation

## Table of Contents
1. Introduction
2. Getting Started
3. Features Overview
4. How to Use
5. Technical Details
6. Troubleshooting
7. Design Principles

---

## 1. Introduction

The Alarm Clock App is a modern, feature-rich web application designed to help you manage multiple alarms efficiently. Built with responsive design principles, it works seamlessly on desktop, tablet, and mobile devices. The app provides an intuitive interface for setting, managing, and controlling alarms with various customization options.

### Key Features:
- **Multiple Alarms**: Set and manage unlimited alarms
- **Custom Labels**: Give each alarm a meaningful name
- **Alarm Tones**: Choose from 6 different alarm sounds
- **Repeat Options**: Schedule recurring alarms for specific days
- **Easy Management**: Toggle alarms on/off, edit, or delete with one click
- **Snooze Function**: Delay alarms by 5 minutes when they ring
- **Modern UI**: Clean, visually appealing interface with smooth animations

---

## 2. Getting Started

### Launching the App
Simply open the alarm clock app in your web browser. The app will display the current time and date immediately upon loading.

### Initial State
The app comes with 3 sample alarms pre-configured:
- **7:30 AM** - Wake Up (Mon-Fri) - Active
- **12:00 PM** - Lunch Reminder (Daily) - Active
- **6:00 PM** - Workout Time (Wed, Fri, Sat) - Inactive

Feel free to delete these and create your own alarms.

---

## 3. Features Overview

### Home Screen
The home screen displays:
- **Current Time**: Updated every second in HH:MM:SS format
- **Current Date**: Shows day of week and full date
- **Set New Alarm Button**: Prominent button to create a new alarm
- **Alarms List**: All your alarms displayed as cards or list items
- **Quick Actions**: Edit, delete, and toggle each alarm

### Alarm List Display
Each alarm card shows:
- **Time**: Alarm time in large, clear format
- **Label**: Custom name for the alarm
- **Repeat Pattern**: Shows which days it repeats (or "Once" for one-time alarms)
- **Toggle Switch**: Quickly enable/disable the alarm
- **Edit Button**: Modify alarm settings
- **Delete Button**: Remove the alarm

### Setting an Alarm
Navigate to the "Set New Alarm" view to:
1. **Select Time**: Use the time picker to set hours and minutes
2. **Choose Tone**: Select from 6 different alarm sounds
3. **Preview Sound**: Test the alarm tone before saving
4. **Add Label**: Name your alarm for easy identification
5. **Enable Repeat** (Optional): Set the alarm to repeat on specific days
6. **Save**: Click "Set Alarm" to add it to your list

### Managing Alarms
From the home screen, you can:
- **Toggle On/Off**: Use the switch to enable or disable alarms temporarily
- **Edit**: Click the edit button to modify time, tone, label, or repeat settings
- **Delete**: Remove alarms you no longer need
- **View Status**: See at a glance which alarms are active

### Alarm Notification
When an alarm reaches its scheduled time:
1. The app displays a full-screen alarm notification
2. The alarm sound plays and loops continuously
3. The alarm name and time are displayed prominently
4. Two action buttons appear:
   - **Snooze**: Delays the alarm for 5 minutes
   - **Dismiss**: Stops the alarm immediately

### Snooze Function
When you click "Snooze":
- The alarm sound stops immediately
- The alarm reschedules for 5 minutes later
- The app returns to the home screen
- A notification appears showing the new alarm time
- You can snooze multiple times if needed

---

## 4. How to Use - Step by Step

### Setting Your First Alarm

**Step 1: Click "Set New Alarm"**
- From the home screen, click the prominent "Set New Alarm" button

**Step 2: Select Time**
- Use the time picker to set your desired alarm time
- Input the hours and minutes
- Current selection is displayed as you adjust

**Step 3: Choose Alarm Tone**
- Click the dropdown menu to view available alarm sounds:
  - Classic Bell (traditional alarm sound)
  - Digital Beep (modern, short beeps)
  - Gentle Chime (soft, pleasant sound)
  - Rooster (morning rooster crow)
  - Nature Sounds (birds chirping)
  - Wake Up Music (gentle musical tones)

**Step 4: Test the Sound (Optional)**
- Click "Test Sound" to preview the alarm tone
- Adjust your selection if needed

**Step 5: Add a Label (Optional)**
- Enter a meaningful name like "Gym", "Doctor Appointment", "Coffee Break"
- If left blank, the alarm time will be used as the label

**Step 6: Set Repeat (Optional)**
- Toggle the "Repeat" switch to enable recurring alarms
- Checkboxes appear for each day of the week
- Select the days you want the alarm to repeat

**Step 7: Save**
- Click "Set Alarm" to add it to your list
- You'll return to the home screen and see your new alarm listed

### Editing an Alarm

**Method 1: Full Edit**
1. Find the alarm you want to modify
2. Click the pencil/edit icon on the alarm card
3. The alarm form opens with current settings pre-filled
4. Make your changes
5. Click "Update Alarm" to save changes

**Method 2: Quick Toggle**
1. To temporarily disable an alarm without deleting it, click the toggle switch
2. The alarm will remain in your list but won't ring until re-enabled

### Deleting an Alarm

1. Find the alarm you want to remove
2. Click the trash/delete icon
3. The alarm is immediately removed from your list

### Handling a Ringing Alarm

**When an alarm rings:**
1. The app shows a prominent alarm notification screen
2. The alarm sound plays continuously
3. The alarm name and time are displayed

**Your options:**
- **Snooze**: Click this to delay the alarm by 5 minutes. The app returns to the home screen and the alarm will ring again in 5 minutes.
- **Dismiss**: Click this to stop the alarm immediately. If it's a one-time alarm, it will be removed. If it's recurring, it will reschedule for the next occurrence.

---

## 5. Technical Details

### How Alarms Work

**Time Checking**
- The app checks the current time every second
- It compares the HH:MM (hours and minutes) of the current time with all enabled alarms
- When times match, the alarm triggers

**For One-Time Alarms**
- When the scheduled time is reached and an enabled alarm matches, it triggers
- After being dismissed, it's removed from the list

**For Repeating Alarms**
- The app checks if today's day of the week is in the repeat days list
- If yes, and the time matches, the alarm triggers
- After being dismissed, it reschedules for the next occurrence

**Snooze Mechanism**
- When snoozed, the current alarm time is calculated as: Current Time + 5 minutes
- A new temporary alarm is created with this updated time
- The snooze alarm will trigger in 5 minutes with the same settings

### Audio Implementation

**Sound Playback**
- The app uses the Web Audio API or HTML5 Audio elements
- Different alarm tones are generated or pre-loaded
- When an alarm rings, the sound loops continuously
- Audio plays at consistent volume level

**Browser Requirements**
- Modern browser with HTML5 support
- JavaScript enabled
- Audio playback permissions granted if prompted

### Data Storage

**Session-Based Storage**
- All alarms are stored in memory during your session
- Data persists as long as you keep the app open in the browser
- Refreshing the page will reset alarms to default state
- **Note**: For production use, consider adding localStorage or database integration

### Device Compatibility

- **Desktop**: Full functionality on Windows, Mac, and Linux
- **Tablet**: Optimized interface for iPad and Android tablets
- **Mobile**: Responsive design adapts to smartphones
- **Browser Support**: Chrome, Firefox, Safari, Edge (modern versions)

---

## 6. Troubleshooting

### Alarm Not Ringing

**Problem**: Scheduled alarm time passed but no alarm sounded

**Solutions**:
1. Check that the alarm is **enabled** (toggle switch is ON)
2. Verify the alarm time is correctly set
3. For repeating alarms, confirm today's day is selected
4. Ensure browser tab is active or has notification permissions
5. Check browser volume and system volume settings

### Sound Not Playing

**Problem**: Alarm notification appears but no sound

**Solutions**:
1. Verify system volume is not muted
2. Check browser sound/audio permissions in browser settings
3. Try a different alarm tone - might have audio issues
4. Click "Test Sound" in alarm settings to verify audio works
5. Refresh the page and try again

### Can't Set Alarm

**Problem**: Unable to save new alarm

**Solutions**:
1. Ensure time is selected in the time picker
2. Verify all required fields are filled
3. Try selecting a different time first, then adjusting
4. Clear browser cache and refresh
5. Try using a different browser

### Snooze Not Working

**Problem**: Clicking snooze doesn't delay the alarm

**Solutions**:
1. Ensure app is actively running in browser
2. Try clicking snooze immediately when alarm triggers
3. Verify browser hasn't throttled background timers
4. Manually dismiss and set another alarm as workaround

### Alarms Disappeared

**Problem**: Previously set alarms are no longer showing

**Solutions**:
1. Check if page was refreshed (data is session-based)
2. Ensure you're on the correct browser/device
3. Check if alarms were accidentally deleted
4. Restart the app by refreshing the page

---

## 7. Design Principles

### User Experience

The alarm clock app follows modern UX best practices:

**Clarity**
- Large, readable time display
- Clear visual distinction between active and inactive alarms
- Obvious action buttons with intuitive labels
- Descriptive labels for all controls

**Simplicity**
- Streamlined interface avoiding unnecessary elements
- Logical flow from setting alarm to managing it
- Consistent patterns across all screens
- Minimal learning curve for new users

**Accessibility**
- High contrast colors for readability
- Large touch targets for buttons and controls
- Clear visual feedback for all interactions
- Keyboard navigation support

**Responsiveness**
- Adapts beautifully to any screen size
- Touch-friendly on mobile devices
- Desktop-optimized layout
- Smooth animations and transitions

### Visual Design

**Color Scheme**
- **Primary**: Soft blues and purples (calming, suitable for alarm context)
- **Active**: Vibrant accent colors (indicate enabled alarms)
- **Alert**: Bold reds and oranges (alarm ringing state)
- **Neutral**: Grays and whites (background and secondary elements)

**Typography**
- **Large Display**: Time shown in 48-72pt font for visibility
- **Labels**: 16-18pt for alarm names and descriptions
- **Body Text**: 14pt for form fields and descriptions
- **Font Family**: Modern sans-serif for clean appearance

**Spacing and Layout**
- Generous padding around elements (8-16px)
- Clear visual hierarchy with size and spacing
- Mobile-first responsive design
- Organized sections with visual separation

### Interactive Elements

**Buttons**
- Clear, labeled action buttons
- Visual feedback on hover and click
- Consistent sizing and spacing
- Color coding: Primary action in accent color, secondary in neutral

**Toggles**
- Large, easy-to-click switches
- Color change indicates state (green for ON, gray for OFF)
- Smooth animation when toggling
- Immediate visual feedback

**Forms**
- Clean input layouts
- Clear labeling of all fields
- Helpful placeholder text
- Error messages if validation needed

### Feedback and Notifications

- **Toast Notifications**: Brief messages for successful actions
- **Visual State Changes**: Immediate UI updates after actions
- **Audio Feedback**: Alarm sound for alarms and test tone feedback
- **Loading States**: Clear indication when processing

---

## Best Practices for Using Your Alarm Clock

1. **Label Your Alarms Meaningfully**: Use descriptive names to identify alarms at a glance
2. **Use Repeat for Regular Events**: Schedule recurring alarms for daily routines
3. **Test Before Bedtime**: If using for wake-up alarms, test the sound at loud volume beforehand
4. **Manage Multiple Alarms**: Set backup alarms 5-10 minutes after important ones
5. **Disable Unnecessary Alarms**: Turn off old alarms you don't need to keep your list clean
6. **Keep Browser Open**: Keep the browser tab active for alarms to function reliably
7. **Check Permissions**: Allow notification permissions if prompted by browser

---

## Conclusion

The Alarm Clock App provides a modern, user-friendly solution for alarm management. Its intuitive interface, combined with powerful features like repeat scheduling and snooze functionality, makes it perfect for daily use. Whether you need wake-up alarms, meeting reminders, or medication timers, this app has you covered.

For support or feature suggestions, please refresh the page or consult the troubleshooting section above.
