# Install Flutter Without Android Studio on Windows 11

## 1. Create File Structure

```bash
mkdir C:\tools
mkdir C:\tools\Android
mkdir C:\tools\Java
mkdir C:\tools\Android\Sdk
mkdir C:\tools\Android\Sdk\cmdline-tools
mkdir C:\tools\Android\Sdk\cmdline-tools\latest
```

## 2. Download & Extract Tools

- Download **cmdline-tools** → [Android Command Line Tools](https://developer.android.com/studio#command-line-tools-only)
  - Open `cmdline-tools-latest.zip` → go inside `cmdline-tools` folder
  - Copy all contents (`bin`, `lib`, `NOTICE.txt`, `source.properties`) into `C:\tools\Android\Sdk\cmdline-tools\latest`

- Download **Flutter SDK** → [Flutter Manual Install](https://docs.flutter.dev/install/manual#install-flutter)
  - Extract the zip so the result is `C:\tools\flutter`

- Download **JDK 17** → [Oracle JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) or [Adoptium](https://adoptium.net/temurin/releases/?version=17)
  - Extract/install so the result is `C:\tools\Java\jdk-17.0.x`

## 3. Final Folder Structure

```
C:\tools\
├── Android\
│   └── Sdk\
│       ├── cmdline-tools\
│       │   └── latest\
│       │       ├── bin\
│       │       ├── lib\
│       │       ├── NOTICE.txt
│       │       └── source.properties
│       └── platform-tools\        ← created after sdkmanager step
├── flutter\
│   └── bin\
└── Java\
    └── jdk-17.0.x\
        └── bin\
```

## 4. Set Environment Variables

Add these **System Environment Variables**:

| Variable | Value |
|---|---|
| `ANDROID_HOME` | `C:\tools\Android\Sdk` |
| `JAVA_HOME` | `C:\tools\Java\jdk-17.0.x` |

## 5. Add to PATH

Add all of these to your system **PATH**:

```
C:\tools\Android\Sdk\cmdline-tools\latest\bin
C:\tools\Android\Sdk\platform-tools
C:\tools\flutter\bin
C:\tools\Java\jdk-17.0.x\bin
```

## 6. Install Android SDK & Accept Licenses

Open a **new terminal** (so PATH changes take effect), then run:

```bash
sdkmanager --install "platform-tools" "platforms;android-36" "build-tools;36.0.0"
sdkmanager --licenses
```

## 7. Verify Setup

```bash
flutter doctor
```

All checkmarks should pass except Android Studio (which is expected — you didn't install it).
