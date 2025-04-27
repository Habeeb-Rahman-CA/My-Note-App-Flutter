# mynotes

This project is a journey of Learning flutter through building a simple project but include all the important topic from flutter. I will markdown all the thing in the readme file, it will be very helpful to re-check what are the process im done in the project. 

# 📱 Installation and Setting up a Flutter project

## 1. Install Flutter SDK

```bash
sudo apt update
sudo apt install git curl unzip xz-utils
curl -O https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_latest-stable.tar.xz
tar xf flutter_linux_latest-stable.tar.xz
sudo mv flutter /opt/
```

➔ Add Flutter to PATH:

```bash
echo 'export PATH="$PATH:/opt/flutter/bin"' >> ~/.bashrc
source ~/.bashrc
```

## 2. Check Flutter Installation

```bash
flutter doctor
```
➔ Follow any missing setup instructions (like Android SDK, etc.)

## 3. Create a New Flutter Project

```bash
flutter create my_app
cd my_app
```

## 4. Run the Flutter App

```bash
flutter run
```

> Make sure an emulator or physical device is connected.

## 5. Common Useful Commands

- Upgrade Flutter:

```bash
flutter upgrade
```

- Get dependencies:

```bash
flutter pub get
```

- Clean build:

```bash
flutter clean
```

---

# 📱 Firebase Configuration

## 1. Install Firebase CLI

```bash
sudo apt update
sudo apt install npm
sudo npm install -g firebase-tools
```

## 2. Install FlutterFire CLI

```bash
dart pub global activate flutterfire_cli
```

➔ Add to PATH if needed:

```bash
echo 'export PATH="$PATH:$HOME/.pub-cache/bin"' >> ~/.bashrc
source ~/.bashrc
```

## 3. Login to Firebase

```bash
firebase login
```

## 4. Create Firebase Project
- Go to [Firebase Console](https://console.firebase.google.com/).
- Click "**Add Project**" ➔ Create new project.

## 5. Configure Flutter App with Firebase

```bash
flutterfire configure
```

➔ This generates `firebase_options.dart`.

## 6. Add Firebase Core to Flutter

In `pubspec.yaml`:

```yaml
dependencies:
  firebase_core: ^latest_version
```

Then:

```bash
flutter pub get
```

## 7. Initialize Firebase in Flutter

In `main.dart`:

```dart
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';
import 'firebase_options.dart';

void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );
  runApp(const MyApp());
}
```

