# ✅ Day 1 — Android Hello World (Notes)

## 📘 1. What is Android?

Android is an **open-source mobile operating system** developed by **Google**.  
It is used to build applications for:

- Smartphones  
- Tablets  
- Smart TVs  
- Wearables  

---

## 📱 2. What is an Android App?

An Android app is a packaged software file (APK) that runs on Android devices.  
It consists of:

- **Java/Kotlin code** → application logic  
- **XML** → user interface design  
- **Resources** → images, colors, strings  

---

## 🚀How to create project in Android

### Step 1: Create New Project
1. Open Android Studio
2. Click "New Project"
3. Select "Empty Views Activity"
4. Configure:
   - Name: MyFirstApp
   - Package name: com.example.myfirstapp
   - Language: Java
   - Minimum SDK: API 24

### Step 2: Run Your App
1. Click the Run button (▶️)
2. Choose emulator or physical device
3. See "Hello World!" on screen


## 🧱 3. What is an Activity?

An **Activity** represents **one screen** in an Android application.

Examples:
- Login Screen  
- Home Screen  
- Profile Screen  

Mainactivity is your **first Activity** ✅

---

## 🎨 4. What is XML Layout?

The user interface of an Android app is designed using **XML files**.

This file controls:
- What is shown on the screen  
- How it is positioned  
- How it looks  

---

## 🔗 5. Connection Between Java & XML

This line connects your Java file with the UI:

```java
setContentView(R.layout.activity_main);
```
Meaning:
"Show activity_main.xml on this screen."

## 📄 6. What is AndroidManifest.xml?

This file defines:

- The main launcher activity  
- App permissions  
- App name  
- App icon

### ✅ Launcher Activity Declaration

```xml
<intent-filter>
    <action android:name="android.intent.action.MAIN" />
    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
```

## 7. values Folder (Resources)

**Path:** `app/src/main/res/values/`

### Important Files:

| File Name | Purpose |
|-----------|---------|
| `colors.xml` | Stores all app colors |
| `strings.xml` | Stores all text |
| `themes.xml` | App theme & styling |

### Example: `strings.xml`
```xml
<string name="app_name">Learn Android With Java</string>
```
✅ Benefits:
- Easy to change text in one place
- Supports multiple languages
- Clean architecture

# 8. mipmap Folder (App Launcher Icon)

**Path:** `app/src/main/res/mipmap-*/`

✅ **Stores app icons for different screen sizes:**
- `mdpi` (Medium density ~160dpi)
- `hdpi` (High density ~240dpi)
- `xhdpi` (Extra high density ~320dpi)
- `xxhdpi` (Extra-extra high density ~480dpi)
- `xxxhdpi` (Extra-extra-extra high density ~640dpi)

**Usage in Manifest:**
```xml
android:icon="@mipmap/ic_launcher"
```

Key Features:
- Android automatically selects the correct resolution based on device screen density
- Ensures crisp, clear app icons on all devices
- Provides better visual quality than using drawable for app icons

# Android Project Configuration Files

## ✅ 9. Gradle Files (Very Important)

### ✅ a) Project-level `build.gradle(.kts)`
**Location:** `ProjectRoot/build.gradle.kts`
**Purpose:** Controls Gradle version, plugin versions, and common configurations

**Example Content:**
```kotlin
plugins {
    id("com.android.application") version "8.4.0" apply false
    id("org.jetbrains.kotlin.android") version "1.9.0" apply false
}

// Top-level build file where you can add configuration options common to all sub-projects/modules
```
## ✅ b) App-level build.gradle(.kts)

**Location:** `app/build.gradle.kts`

**Purpose:** Controls app-specific build configurations, SDK versions, and dependencies

### **Controls:**
- `compileSdk` - Version of Android SDK to compile with
- `minSdk` - Minimum Android version your app supports
- `targetSdk` - Android version your app is optimized for
- Dependencies (libraries) - External libraries your app uses

### **Example:**
```kotlin
android {
    compileSdk = 35  // Compile with Android 14 (API 35)
    minSdk = 24      // Supports Android 7.0 (API 24) and above
    targetSdk = 35   // Optimized for Android 14 (API 35)
}
```

## ✅ c) settings.gradle(.kts)

**Location:** `settings.gradle.kts` (root project folder)

**Purpose:** Registers and configures the modules included in your Android project

### **Registers modules:**
```kotlin
include(":app")
```

## ✅ 10. gradle.properties File

**Location:** `gradle.properties` (root project folder)

**Purpose:** This file is used for configuring Gradle build environment, performance settings, JVM memory allocation, and feature flags

### **This file is used for:**
- Performance settings (caching, parallel execution)
- JVM memory configuration
- Feature flags (AndroidX, Jetifier)
- Global Gradle properties
- System-wide build configurations

 
## ✅11. Activity Lifecycle
The Activity Lifecycle is the set of callback methods that manage the state of an activity from creation to destruction.
Key methods called in order:
1. `onCreate()` - Activity is created
2. `onStart()` - Shown on screen
3. `onResume()` - Activity is in foreground and user can interact
4. `onPause()` - Activity loses focus (partially visible, NOT fully background yet)
5. `onStop()` - Activity no longer visible
6. `onDestroy()` - Activity is destroyed

### **Example:**
```properties
# Performance and memory settings
org.gradle.jvmargs=-Xmx2048m -Dfile.encoding=UTF-8
org.gradle.parallel=true
org.gradle.caching=true
org.gradle.daemon=true

# Android feature flags
android.useAndroidX=true
android.enableJetifier=true

# Kotlin configuration
kotlin.code.style=official



```
### Project Structure
```
MyAndroidApp/
├── app/
│ ├── build.gradle.kts # Module-level build configuration
│ ├── proguard-rules.pro # Code shrinking rules
│ ├── src/
│ │ ├── main/
│ │ │ ├── java/
│ │ │ │ └── com/example/myapp/
│ │ │ │ ├── MainActivity.java # Main activity class
│ │ │ │ ├── MyApplication.java # Application class
│ │ │ │ └── ... # Other activities/fragments
│ │ │ ├── res/
│ │ │ │ ├── layout/
│ │ │ │ │ ├── activity_main.xml # Main layout
│ │ │ │ │ ├── fragment_home.xml # Fragment layouts
│ │ │ │ │ └── ...
│ │ │ │ ├── values/
│ │ │ │ │ ├── colors.xml # Color resources
│ │ │ │ │ ├── strings.xml # String resources
│ │ │ │ │ ├── styles.xml # Style resources
│ │ │ │ │ ├── themes.xml # Theme definitions
│ │ │ │ │ └── dimens.xml # Dimension resources
│ │ │ │ ├── drawable/
│ │ │ │ │ ├── ic_background.xml # Vector drawables
│ │ │ │ │ ├── button_shape.xml # Shape drawables
│ │ │ │ │ └── my_image.png # Bitmap images
│ │ │ │ ├── mipmap-anydpi-v26/
│ │ │ │ │ ├── ic_launcher.xml # Adaptive icons (API 26+)
│ │ │ │ │ └── ic_launcher_round.xml
│ │ │ │ ├── mipmap-hdpi/
│ │ │ │ │ ├── ic_launcher.png # Launcher icons
│ │ │ │ │ └── ic_launcher_round.png
│ │ │ │ ├── mipmap-mdpi/
│ │ │ │ │ └── ...
│ │ │ │ ├── mipmap-xhdpi/
│ │ │ │ │ └── ...
│ │ │ │ ├── mipmap-xxhdpi/
│ │ │ │ │ └── ...
│ │ │ │ ├── mipmap-xxxhdpi/
│ │ │ │ │ └── ...
│ │ │ │ ├── xml/
│ │ │ │ │ ├── backup_rules.xml # Auto-backup rules
│ │ │ │ │ └── data_extraction_rules.xml
│ │ │ │ ├── anim/
│ │ │ │ │ └── fade_in.xml # Animation files
│ │ │ │ ├── menu/
│ │ │ │ │ └── main_menu.xml # Menu definitions
│ │ │ │ ├── navigation/
│ │ │ │ │ └── nav_graph.xml # Navigation graph
│ │ │ │ ├── raw/
│ │ │ │ │ └── sample_video.mp4 # Raw resource files
│ │ │ │ ├── font/
│ │ │ │ │ └── roboto_regular.ttf # Custom fonts
│ │ │ │ └── values-night/
│ │ │ │ └── themes.xml # Dark theme resources
│ │ │ ├── assets/
│ │ │ │ └── data.json # Asset files (not compiled)
│ │ │ └── AndroidManifest.xml # App manifest
│ │ ├── debug/
│ │ │ └── AndroidManifest.xml # Debug-specific manifest
│ │ └── test/
│ │ └── java/ # Unit tests
│ └── build/
│ └── ... # Build outputs
├── build.gradle.kts # Project-level build config
├── settings.gradle.kts # Project settings
├── gradle.properties # Gradle properties
├── gradle/
│ └── wrapper/
│ ├── gradle-wrapper.jar
│ └── gradle-wrapper.properties
├── gradlew # Gradle wrapper (Unix)
├── gradlew.bat # Gradle wrapper (Windows)
├── local.properties # Local environment properties
├── .gitignore # Git ignore rules
├── .gradle/
│ └── ... # Gradle cache
├── .idea/
│ └── ... # IDE settings (Android Studio)
├── app.iml # Module configuration
├── build/
│ └── ... # Project build outputs
└── README.md # Project documentation
```


