# calculation
## AIM
To develop an Android application that accepts two numbers from the user and displays their sum using Android Studio.

## APPARATUS / SOFTWARE REQUIRED
Android Studio (Electric Eel / Flamingo / latest version)

Java JDK 8 or above

Android SDK (API Level 21 or above)

Android Emulator (Pixel 6 – API 33) OR physical Android device

Gradle Build System (bundled with Android Studio)

## THEORY
Android is an open-source mobile operating system developed by Google, based on the Linux kernel. Applications for Android are typically written in Java or Kotlin using the Android SDK.

An Android application is composed of four main components:

Activities – Represents a single screen with a user interface.

Services – Runs in the background without a UI.

Broadcast Receivers – Responds to system-wide broadcast announcements.

Content Providers – Manages shared app data.

The UI (User Interface) of an Activity is defined in an XML layout file located under res/layout/. Each UI widget is given an id using the android:id attribute, which is then referenced in the Java/Kotlin code using findViewById().

In this experiment, we use the following widgets:

Widget	Purpose
EditText	To accept numeric input from the user
Button	To trigger the addition operation
TextView / EditText	To display the result
LinearLayout	To arrange widgets vertically
The Button's click event is handled using setOnClickListener(), where the values from the EditTexts are read using getText().toString(), parsed using Double.parseDouble(), added, and displayed.

## PROCEDURE
Launch Android Studio → New Project → Empty Views Activity.

Enter project name: AdditionApp, package: com.example.additionapp, Language: Java, Minimum SDK: API 21.

Wait for Gradle sync to complete.

Open res/layout/activity_main.xml and paste the layout code (see Appendix).

Open MainActivity.java and paste the Java code (see Appendix).

Connect an emulator or physical device.

Click the Run ▶ button (Shift + F10).

In the running app:

Enter the first number in the first field.

Enter the second number in the second field.

Tap the Add button.

Observe the result displayed in the Result field.

Take a screenshot of the output for the record.

PROGRAM CODE
(a) activity_main.xml
(paste the XML layout from earlier message)

(b) MainActivity.java
(paste the Java code from earlier message)

OUTPUT
