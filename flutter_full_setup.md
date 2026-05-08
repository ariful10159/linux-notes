
# 🚀 Flutter Setup on Linux (Ubuntu) – Complete Guide

---

## 📌 1. Flutter SDK Install (From Browser)

**Why:** Flutter framework অফিসিয়াল website থেকে download করে Linux এ install করার জন্য।

👉 Download from browser:

[Flutter Linux Install Guide](https://docs.flutter.dev/get-started/install/linux?utm_source=chatgpt.com)



---

## 📌 2. Environment PATH Setup

**Why:** Terminal থেকে `flutter` command globally use করার জন্য।

```bash id="f2b8m1"
nano ~/.bashrc
```

Add this line:

```bash id="f3c7n0"
export PATH="$PATH:$HOME/flutter/bin"
```

Apply:

```bash id="f4d6p9"
source ~/.bashrc
```

---

## 📌 3. Flutter Verify

**Why:** Installation successful কিনা check করার জন্য।

```bash id="f5e5r8"
flutter --version
```

---

## 📌 4. Git Install

**Why:** Flutter internally Git ব্যবহার করে SDK manage করার জন্য।

```bash id="f6t4y7"
sudo apt update
sudo apt install git -y
```

---

## 📌 5. Android SDK Setup (Manual)

**Why:** Android app build & run করার জন্য required system tools।

```bash id="f7u3z6"
wget https://dl.google.com/android/repository/commandlinetools-linux-*.zip
mkdir -p ~/Android/Sdk/cmdline-tools
unzip commandlinetools-linux-*.zip -d ~/Android/Sdk/cmdline-tools
mv ~/Android/Sdk/cmdline-tools/cmdline-tools ~/Android/Sdk/cmdline-tools/latest
```

---

## 📌 6. Android Environment Variables

**Why:** SDK system-wide access enable করার জন্য।

```bash id="f8v2a5"
nano ~/.bashrc
```

Add:

```bash id="f9w1b4"
export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

Apply:

```bash id="g1x0c3"
source ~/.bashrc
```

---

## 📌 7. Install Android SDK Packages

**Why:** APK build, emulator, and device connection support এর জন্য।

```bash id="g2y9d2"
sdkmanager "platform-tools" "platforms;android-36" "build-tools;36.0.0"
```

---

## 📌 8. Accept Android Licenses

**Why:** Android SDK legal permissions accept করার জন্য।

```bash id="g3z8e1"
flutter doctor --android-licenses
```

---

## 📌 9. Chrome / Chromium Setup

**Why:** Flutter Web app run করার জন্য browser support দরকার।

```bash id="g4a7f0"
sudo apt install chromium-browser -y
```

Set executable:

```bash id="g5b6g9"
export CHROME_EXECUTABLE=/usr/bin/chromium-browser
```

---

## 📌 10. Flutter Doctor Check

**Why:** Full system verification করার জন্য।

```bash id="g6c5h8"
flutter doctor
```

---

## 📌 11. Connect Android Device

**Why:** Real phone এ app run করার জন্য।

* Developer Mode ON
* USB Debugging ON

Check:

```bash id="g7d4i7"
flutter devices
```

---

## 📌 12. Run First App

**Why:** Flutter project test করার জন্য।

```bash id="g8e3j6"
flutter create myapp
cd myapp
flutter run
```

---

# 🎯 Final Status

✔ Flutter installed from browser (Linux stable version)
✔ Android SDK ready
✔ Git configured
✔ Phone ready for testing
✔ Web support enabled

---
