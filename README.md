# Install Flutter Without Android Studio on Windows

---

## 1. Create Folder Structure

> 💡 Open **PowerShell as Administrator** and run:

```powershell
New-Item -ItemType Directory -Force -Path C:\tools\Android\Sdk\cmdline-tools\latest, C:\tools\flutter, C:\tools\Java
```

This creates all required folders at once. `-Force` skips errors if folders already exist.

---

## 2. Download & Extract Tools

### Android Command Line Tools
- Download from → [Android Command Line Tools](https://developer.android.com/studio#command-line-tools-only)
- Open the zip → go inside the `cmdline-tools` folder
- Copy all contents (`bin`, `lib`, `NOTICE.txt`, `source.properties`) into:
  ```
  C:\tools\Android\Sdk\cmdline-tools\latest
  ```

### Flutter SDK
- Download from → [Flutter Manual Install](https://docs.flutter.dev/install/manual#install-flutter)
- Open the zip → copy the `flutter` folder contents into:
  ```
  C:\tools\flutter
  ```

### JDK 17
- Download from → [Adoptium JDK 17](https://adoptium.net/temurin/releases/?version=17)
- Extract the zip → copy the `jdk-17.x.x` folder into:
  ```
  C:\tools\Java\
  ```
  Result should look like `C:\tools\Java\jdk-17.0.15` (version number may differ)

---

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
│       └── platform-tools\        ← created automatically later
├── flutter\
│   └── bin\
└── Java\
    └── jdk-17.0.15\               ← your version number may differ
        └── bin\
```

---

## 4. Set Environment Variables

> 💡 How to open Environment Variables:
> 1. Press `Win + S` → search **"Environment Variables"**
> 2. Click **"Edit the system environment variables"**
> 3. Click **"Environment Variables..."** button at the bottom
> 4. Under **"System variables"** click **"New"**

Add these two variables:

| Variable | Value |
|---|---|
| `ANDROID_HOME` | `C:\tools\Android\Sdk` |
| `JAVA_HOME` | `C:\tools\Java\jdk-17.0.15` ← replace with your exact folder name |

---

## 5. Add to PATH

> 💡 How to add to PATH:
> 1. In the same **Environment Variables** window
> 2. Under **"System variables"** find and select **"Path"** → click **"Edit"**
> 3. Click **"New"** and add each line below one by one

```
C:\tools\Android\Sdk\cmdline-tools\latest\bin
C:\tools\Android\Sdk\platform-tools
C:\tools\flutter\bin
C:\tools\Java\jdk-17.0.15\bin    ← replace with your exact folder name
```

---

## 6. Install Android SDK & Accept Licenses

> 💡 Close and reopen your terminal so the PATH changes take effect, then run:

```bash
sdkmanager --install "platform-tools" "platforms;android-36" "build-tools;36.0.0"
sdkmanager --licenses
```

> When prompted with `Accept? (y/N)` → type `y` and press Enter for each one.

---

## 7. Verify Setup

```bash
flutter doctor
```

> ✅ Everything should pass except **Android Studio** — that's expected since we didn't install it.

---

Done! 🎉
