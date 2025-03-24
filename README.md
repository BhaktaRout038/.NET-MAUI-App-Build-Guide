# .NET MAUI App Build Guide

This guide provides instructions on how to build and generate APK (Android), IPA (iOS), and EXE/MSIX (Windows) files for your .NET MAUI application.

## Prerequisites

Before building your .NET MAUI application, ensure you have the following installed:

### 1️⃣ Install .NET 9 SDK
Download and install the latest .NET 9 SDK from the official website:
- [Download .NET 9 SDK](https://dotnet.microsoft.com/download/dotnet/9.0)

### 2️⃣ Install .NET MAUI Workload
Run the following command to install .NET MAUI:
```sh
 dotnet workload install maui
```
To verify the installation, use:
```sh
 dotnet workload list
```

### 3️⃣ Install Platform Dependencies
- **Android**: Install the Android SDK via Visual Studio Installer.
- **iOS**: Requires a Mac with Xcode installed.
- **Windows**: Requires the Windows SDK (included with Visual Studio).

## Building Your .NET MAUI App

### 📌 1. Build APK for Android

#### 🔹 Step 1: Set Release Mode
Run the following command:
```sh
 dotnet publish -f net9.0-android -c Release
```

#### 🔹 Step 2: Locate APK
The generated APK will be found in:
```bash
 ./bin/Release/net9.0-android/publish/*.apk
```

#### 🔹 Step 3: Generate Signed APK (Optional)
To generate a signed AAB (required for Google Play Store):
```sh
 dotnet publish -f net9.0-android -c Release -p:AndroidPackageFormat=aab
```

---

### 📌 2. Build IPA for iOS

#### 🔹 Step 1: Build IPA
Run the following command on a Mac with Xcode installed:
```sh
 dotnet publish -f net9.0-ios -c Release
```

#### 🔹 Step 2: Locate IPA
Find the IPA file in:
```bash
 ./bin/Release/net9.0-ios/publish/*.ipa
```
**Note:** An Apple Developer Account is required for signing.

---

### 📌 3. Build EXE/MSIX for Windows

#### 🔹 Step 1: Build Windows App
Run:
```sh
 dotnet publish -f net9.0-windows -c Release
```

#### 🔹 Step 2: Locate Executable
The EXE/MSIX file will be in:
```bash
 ./bin/Release/net9.0-windows/publish/
```
For Windows Store submission, generate an MSIX package:
```sh
 dotnet publish -p:WindowsPackageType=msix
```

## 📌 Summary of Build Commands

| Platform  | Build Command | Output Path |
|-----------|--------------|-------------|
| **Android (APK)** | `dotnet publish -f net9.0-android -c Release` | `bin/Release/net9.0-android/publish/*.apk` |
| **Android (AAB)** | `dotnet publish -f net9.0-android -c Release -p:AndroidPackageFormat=aab` | `bin/Release/net9.0-android/publish/*.aab` |
| **iOS (IPA)** | `dotnet publish -f net9.0-ios -c Release` | `bin/Release/net9.0-ios/publish/*.ipa` |
| **Windows (EXE/MSIX)** | `dotnet publish -f net9.0-windows -c Release` | `bin/Release/net9.0-windows/publish/` |

---

## 🚀 Need Help with Signing APK or IPA for Store Submission?
Check the official documentation for signing and distribution guidelines:
- [Android App Signing](https://developer.android.com/studio/publish/app-signing)
- [iOS Code Signing](https://developer.apple.com/forums/thread/707080)
- [Windows App Packaging](https://learn.microsoft.com/en-us/windows/msix/)

---

Author: [Bhakta Charan Rout](https://github.com/BhaktaRout038)

