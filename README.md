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

## PROGRAM CODE
``` activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="24dp"
    android:gravity="center">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Addition of Two Numbers"
        android:textSize="22sp"
        android:textStyle="bold"
        android:layout_marginBottom="30dp"/>

    <EditText
        android:id="@+id/etNum1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter First Number"
        android:inputType="numberDecimal"
        android:layout_marginBottom="16dp"/>

    <EditText
        android:id="@+id/etNum2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Second Number"
        android:inputType="numberDecimal"
        android:layout_marginBottom="20dp"/>

    <Button
        android:id="@+id/btnAdd"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Add"
        android:layout_marginBottom="20dp"/>

    <EditText
        android:id="@+id/etResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Result"
        android:enabled="false"
        android:textSize="18sp"
        android:textStyle="bold"/>

</LinearLayout>
```
```MainActivity.java
package com.example.additionapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText etNum1, etNum2, etResult;
    Button btnAdd;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Link UI components with Java objects
        etNum1   = findViewById(R.id.etNum1);
        etNum2   = findViewById(R.id.etNum2);
        etResult = findViewById(R.id.etResult);
        btnAdd   = findViewById(R.id.btnAdd);

        // Set click listener on the button
        btnAdd.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String s1 = etNum1.getText().toString().trim();
                String s2 = etNum2.getText().toString().trim();

                // Validate input
                if (s1.isEmpty() || s2.isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Please enter both numbers", Toast.LENGTH_SHORT).show();
                    return;
                }

                // Parse and calculate
                double num1 = Double.parseDouble(s1);
                double num2 = Double.parseDouble(s2);
                double sum  = num1 + num2;

                // Display the result
                etResult.setText(String.valueOf(sum));
            }
        });
    }
}
```

