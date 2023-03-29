# Silent SMS detector

Android application for detecting (and sending) silent SMS messages that does not require rooted device.

## What is silent SMS?

A silent SMS (*Short Message Service*) is a type of text message that is sent to a mobile phone without the knowledge or consent of the phone's user. Unlike regular SMS messages, silent SMS messages are invisible and do not trigger any notification or sound on the target phone.

This functionality is not some secret hack, but actually a part of the two mobile telecommunications standards, namely [3GPP 23.040 (originally GSM 03.40)](https://en.wikipedia.org/wiki/GSM_03.40) and [3GPP 23.038 (originally GSM 03.38)](https://en.wikipedia.org/wiki/GSM_03.38).

By sending silent SMS on a target phone, a sender can detect whether mobile phone is online or offline. Or more specifically - **a sender can detect if target SIM card is connected to the network or not**. That allows attackers to determine whether a specific mobile number is being active or not.

However, silent SMS **could also be used to determine the location of the target mobile device**. When a silent SMS is sent to the target device, it forces it to reveal its location, because it makes a connection to the nearest (available) serving base station in cellular network. In that case silent SMS messages could be used by law enforcement agencies for surveillance and tracking purposes, because they allow them to locate the position of a mobile phone without alerting the user. It is known that in the past, [German police has been using silent SMSes to track the suspects](https://edri.org/our-work/edrigramnumber10-2silent-sms-tracking-suspects/).

## What is this application doing (and *what not*)?

This application, which is a fork of [Android Silent SMS Ping](https://github.com/itds-consulting/android-silent-ping-sms), can send silent SMS messages to determine if a target SIM card (phone number) is active or not. It can also detect received silent SMS messages and alert user that he has received silent SMS.

The application is running on new Android devices and does not require rooted device.

<img src="notification1.jpg" alt="Silent SMS notification" width="300"/>

It is important to understand, that receiving silent SMS **does not necessary mean you are being targeted by some malicious actor**. Silent SMS messages could be used for various technical reasons and receiving a silent SMS is not a good indicator of being targeted by your cell carrier, government or hackers.

On the other side, there are several other possibilities of tracking, so **the fact that you did not receive silent SMS does not means you are not being tracked**. If you want to avoid tracking, you should turn on the airplane mode (or switch your mobile phone off).

<img src="notification2.jpg" alt="Silent SMS detector" width="80"/>

**So notification that you received silent SMS message does not necessarily means something bad is happening, and absence of this notification does not means that you are safe.**

However, if you want to have greater transparency of what is happening "behind the scenes", *Silent SMS detector* could be interesting application. Because silent SMSes are meant to stay hidden from you, and with this application you can detect them. *Isn't that cool?*

### History

The original application, called [Android Silent SMS Ping](https://github.com/itds-consulting/android-silent-ping-sms) has been first developed in 2016. Unfortunately, it has not been maintained for several years and the original author archived it's Github repository in 2020.

In 2023 appication has been still accessible through F-Droid, but the Virustotal analysis has shown that APK has been infected.

In the beginning of 2023 we started a new development. In the first stage we have updated SDK (to version 33) and Java (to version 11). We have set up application permissions compatible with modern Android systems and improved notifications. We also designed new application icon.

Currently application is fully working (you can install it from APK below or compile it with Android Studio by yourself), but it still looks like the old one.

So in the second stage we plan to implement new design of the application. Later some new functionalities will be added. Specifically, we would like to implement data collection for threat analytics in order to collect the data about silent SMS messages and get some data which could help us estimate the scope of the problem. Stay tuned and check out the issues!

Application is now being developed by [Jure Poljšak](https://github.com/barracuda-fsh) (programming), [Matej Kovačič](https://github.com/MatejKovacic) (architecture) and Vesna Trenchovska (design).

### License

The project is licensed under the [GNU General Public License version 3 (or newer)](https://github.com/MatejKovacic/silent-sms-ping/blob/master/LICENSE).

### APK download (for testing)

Since this application is under heavy development, you can not install this application from Play store yet.

But you can download [testing APK from 28-03-2023](https://github.com/MatejKovacic/silent-sms-ping/blob/master/silent-sms-app-debug_28-03-2023.apk) and install it on your device. Click download button to get it on your device and then you can install APK directly. Please note that on your Android device you should allow installing unknown apps in that case, because APK is not digitally signed.

Another option is to clone this repository on your computer, install *Android Studio*, compile an app by yourself, and install it directly to your Android device.

You are of course always welcome to inspect the source code of the application in order to check that it does not contain some malicious code. And you can also contribute your code or ideas to the project.