# install_flutter_without_android_studio_in_windows_11


- create file structure
```bash
cd /
mkdir -p tools
cd tools
mkdir Android
mkdir Android\Sdk
mkdir Android\Sdk\cmdline-tools
mkdir Android\Sdk\cmdline-tools\latest
```

- download cmdline-tools  [from this link](https://developer.android.com/studio#command-line-tools-only)
- extract cmdline-tools-latest.zip > cmdline-tools > bin and all content in and extract in c:\tools\Android\Sdk\cmdline-tools\latest



- download latest flutter zip and extract in /tools [from this link](https://docs.flutter.dev/install/manual#install-flutter)



- install sdk 17
create a Java folder in /tools
and put in Java dir in /tools



- set env variable 
```plaintext
ANDROID_HOME= c:\tools\Android\Sdk
JAVA_HOME=c:\tools\Java\jdk-17.x.x (replace)
```


- add path into env
```plaintext
c:\tools\Android\Sdk\cmdline-tools\latest\bin
c:\tools\Android\Sdk\platform-tools
c:\tools\flutter\bin
C:\tools\Java\jdk-17.x.x\bin (replace)
```

- install android sdk and accept license

```bash
sdkmanager --install "platform-tools" "platforms;android-36" "build-tools;36.0.0"
sdkmanager --licenses
```

- boom you're good to go.






