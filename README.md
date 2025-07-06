#🧓 SilverTouch

>“An app for the elderly, touched by the elderly.”
>A mobile service designed to support independent seniors by confirming their safety and alleviating social isolation.


## 🧭 Overview

SilverTouch is a mobile health and community app for elderly individuals living alone.
As the population ages rapidly, the number of seniors living alone continues to increase.
However, many still suffer from physical inactivity, lack of information access, and social isolation.
To address these issues through technology, SilverTouch was designed with four key pillars: Walking, Gathering, Notification, and Information Access.

## 🎯 Background and Direction

Survival Check: Detect abnormal behavior using step count and location data, and send alerts to guardians.
Social Connection: Encourage local interaction and participation through walking meetups.
Information Accessibility: Provide easy access to government welfare and health policies within the app.
User-Friendly UI/UX: Simple navigation structure and visually emphasized design tailored to senior users.
This app goes beyond simple feature implementation — it is designed to genuinely support seniors in their daily lives.

## ⚙️ Key Features

### 1. Login & Signup
-Email-based account creation and login
-Emergency contact registration available


<img width="1162" height="657" alt="Image" src="https://github.com/user-attachments/assets/ede29455-6447-47aa-bd2f-2a664905ec62" />
<img width="1134" height="637" alt="Image" src="https://github.com/user-attachments/assets/9bdb27de-9a0a-4df0-b92b-3f0bb741b3b3" />
---

### 2. Main Page
The main screen serves as the hub of the app, connecting to the following features:

-Today’s step count display
-Step count ranking
-Walking meetup schedules
-Voice recording and alert settings
-Edit user profile
-Direct links to policy information pages


<img width="1165" height="608" alt="Image" src="https://github.com/user-attachments/assets/ced1b578-7d22-43a1-bfdf-12219c7abdac" />

---

### 3. Step Counting & Ranking
-Real-time step tracking using smartphone sensors
-Ranks users by step count (to be improved)




### 4. Walking Meetup
-Provides walk schedules based on the user’s location
-“Join” button to indicate participation
-View current number of participants



### 5. Voice Recording & Sound Detection Alert
-Record and save voice clips directly
-When a clap sound is detected, the recorded message is played as an alert


<img width="1161" height="607" alt="Image" src="https://github.com/user-attachments/assets/d17ceb5c-d456-41ea-97fb-2f26617b4be0" />


---

### 6. Policy Info Website Links
-Categorized welfare, health, and support policy info
-External sites viewable within the app via webview

<img width="1174" height="623" alt="Image" src="https://github.com/user-attachments/assets/869206c8-3a18-4dec-bedb-a8d6af283fd3" />



🔧 Technologies & Implementation

This app was developed using the Flutter framework, with the following technologies:

Technology	Description
Flutter / Dart	Overall UI and logic development
Firebase	App initialization and user authentication (firebase_core)
flutter_sound	Voice recording and saving functionality
pedometer	Step detection via smartphone sensors
flutter_local_notifications	Local alert triggered by clap sound detection
webview_flutter	Display external policy info within the app
shared_preferences	Save login state and user settings
permission_handler	Handle permission requests (e.g., location, microphone)
🔄 Planned Features

Emergency SMS Alerts
If step count is low by 6 PM, or if the user is outside after 10 PM →
Send an automatic SMS to registered guardian.
Find My Phone Feature
When a sound above a certain decibel is detected (e.g., clapping) →
Play a recorded voice and send an alert from the device.
Step Ranking Algorithm Improvement
Currently based on simple comparison →
Will apply normalization algorithm based on distance/time.
🔍 Sample Code Snippets
// Firebase Initialization
await Firebase.initializeApp(
  options: DefaultFirebaseOptions.currentPlatform,
);

// Step count stream listener
_pedometer.pedometerStream.listen((event) {
  setState(() {
    _steps = event.steps;
  });
});

// Start recording
await _recorder.startRecorder(toFile: 'audio.aac');

// Show alert on sound detection
await flutterLocalNotificationsPlugin.show(
  0,
  'Alert',
  'Sound detected!',
  platformChannelSpecifics,
);
