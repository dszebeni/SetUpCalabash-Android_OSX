# SetUpCalabash-Android_OSX

Here I can show You, how to set up an enviroment to test Android apps on OSX with Calabash.sh

## Requirements

To use the Calabash, you will need some things

###1. Ruby 2.0 or higher

>You can check the version with command line:
>```
>$ ruby -v
>ruby 2.0.0p648 (2015-12-16 revision 53162) [universal.x86_64-darwin16]
>```

###2.Calabash sandbox

The Calabash Sandbox is the best way for a novice to get started with Calabash. This is a Bash script that will establish a pre-configured Ruby environment with everything necessarily to creating and running tests.

Use command line to install:

```
curl -sSL https://raw.githubusercontent.com/calabash/install/master/install-osx.sh | bash
```

>Do not use sudo to install the Calabash Sandbox.

###3. Android SDK

Download and install from

```
https://developer.android.com/studio/index.html
```

After installation, configure the `ANDROID_HOME` environment variable based on the location of the Android SDK.

```
export ANDROID_HOME=/<your path>
export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```

##Usage

Open a terminal window and make a `calabash-sandbox` session

```
$ calabash-sandbox
```
> You can close the session with `exit`

First, You have to generate a feature folder with:

```
$ calabash-android gen
```

Now you can write Tests and run with:

```
$ calabash-android run <apk path>
```

>After every APK build, you have to resign the APK:
>```
>$ calabash-android resign <apk path>
>```


##Console

You can use 'calabash-android console' to write queries and find the app elements

```
$ calabash-android console <apk path>
```
```
start_test_server_in_background
```
Query to list everything:

```
query ("*")
```

