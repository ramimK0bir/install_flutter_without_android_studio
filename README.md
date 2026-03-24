# install_flutter_without_android_studio
this_is_how_you_install_flutter_without_android_studio


- create file structure
```bash
cd /
mdkir -p tools
cd tools
mkdir Android
mdkir Android\Sdk
mdkir Android\Sdk\cmdline-tools
mdkir Android\Sdk\cmdline-tools\latest
```

- download cmdline-tools and extract in c:\tools\Android\Sdk\cmdline-tools\latest
[from this link](https://developer.android.com/studio#command-line-tools-only)



- download latest flutter zip and extract in /tools



- install sdk 17
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






