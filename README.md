# Setup-Jenkins-agent-for-android-build-and-release
# 1.Download SDK Tools
create directory /data/installations/android-sdk 
# Download commandline tools
wget https://dl.google.com/android/repository/commandlinetools-linux-11076708_latest.zip
# Download Platform tools
wget https://dl.google.com/android/repository/platform-tools-latest-linux.zip

# Directory Structure should look like:-
/data/installations/android-sdk/
└── cmdline-tools/
    └── latest/
        └── bin/
            ├── sdkmanager
            └── ...
# 2.Configure Environment Variables:-
sudo nano ~/.bashrc
export ANDROID_HOME=/data/installations/android-sdk
export PATH=/data/installations/android-sdk/platform-tools:/data/installations/android-sdk/cmdline-tools/tools:/data/installations/android-sdk/cmdline-tools/tools/bin:${PATH}
# Save .bashrc
# Reload Bash
source ~/.bashrc
# 3.Test the Android SDK installed using the environment variables:-
# Check adb version
adb --version
# Check sdkmanager version
sdkmanager --version
# List
sdkmanager --list
# Start downloading the most recent package
sdkmanager "platforms;android-30"

# 4.Install flutter globally
wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_3.19.6-stable.tar.xz
extract
export $PATH=(flutter)/bin
# 5.Check installations and flutter configuration:-
flutter doctor 
OUTPUT:-
![Screenshot from 2024-04-26 13-07-48](https://github.com/mohak72/Setup-Jenkins-agent-for-android-build-and-release/assets/39758636/bf9da007-9852-44b2-9373-964f0e4cc8bc)


