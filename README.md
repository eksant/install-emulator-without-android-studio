## Install Emulator Without Android Studio

### first install 
```bash
sudo apt-get install lib32z1 lib32ncurses5 libbz2-1.0:i386 libstdc++6:i386
```

### install java8
```bash
sudo add-apt-repository ppa:webupd8team/java

sudo apt update

sudo apt install oracle-java8-installer
```

### export environment
```bash
sudo nano .bashrc
```

### then paste at last
```bash
export JAVA_HOME=$(update-alternatives --query javac | sed -n -e 's/Best: *\(.*\)\/bin\/javac/\1/p')
```

### make dir 
```bash
mkdir android/sdk
```
then download android sdk command line tools only  
extract and copy tools in android/sdk folder

### export environment
```bash
nano .bashrc
```

### then paste at last
```bash
export ANDROID_HOME=$HOME/android/sdk
```

### then file
```bash
touch ~/.android/repositories.cfg
```

### then hit this command and keep typing y and press ENTER
```bash
$ANDROID_HOME/tools/bin/sdkmanager --licenses
```

### then install android sdk
```bash
$ANDROID_HOME/tools/bin/sdkmanager "tools" "platform-tools" "platforms;android-25" "build-tools;27.0.3" "extras;android;m2repository" "extras;google;m2repository"
```

### then install emulator
```bash
$ANDROID_HOME/tools/bin/sdkmanager "system-images;android-25;google_apis;x86" "emulator"
```

### check list emulator
```bash
$ANDROID_HOME/tools/bin/avdmanager list

result: ...
---------
id: 11 or "Nexus 6P"
    Name: Nexus 6P
    OEM : Google
---------
```

### then create emulator with skin Nexus 6P
```bash
$ANDROID_HOME/tools/bin/avdmanager create avd -n android-25 -k "system-images;android-25;google_apis;x86" -d 11
```

### how to check avd after create emulator
```bash
$ANDROID_HOME/tools/android list avd
```

### open emulator
```bash
sudo $ANDROID_HOME/tools/emulator @android-25
```
