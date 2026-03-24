# install_flutter_without_android_studio
this_is_how_you_install_flutter_without_android_studio



```bash
cd /
mdkir -p tools
cd tools
mkdir Android
mdkir Android/Sdk
mdkir Android/Sdk/cmdline-tools
mdkir Android/Sdk/cmdline-tools/latest
```
install sdk 17
and put in Java dir in /tools



set env variable 
```plaintext
ANDROID_HOME= c:/tools/Android/Sdk
JAVA_HOME=c:/tools/Java/jdk-17.x.x (replace)
```


add path into env
```plaintext
c:/tools/Android/Sdk/cmdline-tools/latest/bin
c:/tools/Android/Sdk/platform-tools
```




