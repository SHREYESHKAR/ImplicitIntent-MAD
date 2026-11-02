# EXPERIMENT :2A  Develop program to create a text field and a button “Navigate”. When you enter www.gmail.com and press navigate button it should open google page using Implicit Intents.
## NAME : SHREYESHKAR SEKAR
## REGISTEERATION NUMBER : 212224220099

## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step 1: Initialize the Activity

Step 2 :Start the onCreate() method Create references for EditText and Button UI components Load the activity_main.xml layout using setContentView() Step 2: Get UI Components

Step 3: Find the EditText widget (id: editText) using findViewById() Find the Button widget (id: btn) using findViewById() Step 3: Set Button Click Listener

Step 4 :Attach an OnClickListener to the button Prepare to execute code when the button is clicked Step 4: Handle Button Click Event

Step 5: Retrieve the text entered in the EditText using getText().toString() Store the URL in a String variable Step 5: Create Implicit Intent

Step 6:Create a new Intent object with action Intent.ACTION_VIEW Parse the URL string using Uri.parse() Pass the parsed URI as data to the Intent Step 6: Start Activity with Intent

Step 7:Call startActivity() with the created Intent The system will find and launch the appropriate application (browser) to handle the URL Step 7: End

Step 8:The browser opens and displays the requested URL



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:  SHREYESHKAR SEKAR
Registeration Number :  212224220099
*/
```

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/urlInput"
        android:hint="Enter website (e.g. www.gmail.com)"
        android:inputType="textUri"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/navigateBtn"
        android:text="Navigate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"/>
</LinearLayout>
```
Mainactivity.java
```
package com.example.implicit;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import com.example.implicit.R;

public class MainActivity extends AppCompatActivity {

    EditText urlInput;
    Button navigateBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        urlInput = findViewById(R.id.urlInput);
        navigateBtn = findViewById(R.id.navigateBtn);

        navigateBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = urlInput.getText().toString().trim();

                if (url.isEmpty()) {
                    Toast.makeText(MainActivity.this, "Please enter a URL", Toast.LENGTH_SHORT).show();
                } else {
                    // Add http if missing
                    if (!url.startsWith("http://") && !url.startsWith("https://")) {
                        url = "http://" + url;
                    }

                    // Create implicit intent
                    Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));

                    // Start browser
                    try {
                        startActivity(intent);
                    } catch (Exception e) {
                        Toast.makeText(MainActivity.this, "No app found to handle this request", Toast.LENGTH_SHORT).show();
                    }
                }
            }
        });
    }
}
```


## OUTPUT

<img width="1917" height="1198" alt="Screenshot 2026-11-02 082514" src="https://github.com/user-attachments/assets/3d0cf35d-48bf-4a72-a343-0034c649e127" />

<img width="1917" height="1118" alt="Screenshot 2026-11-02 084159" src="https://github.com/user-attachments/assets/a5296364-8d16-40e7-b4dc-792a8833ab02" />

<img width="1600" height="953" alt="WhatsApp Image 2026-11-02 at 9 39 46 AM" src="https://github.com/user-attachments/assets/ee8a6163-6fcc-470f-b79c-96c15c414b21" />

<img width="1600" height="953" alt="WhatsApp Image 2026-11-02 at 9 39 20 AM" src="https://github.com/user-attachments/assets/3d350d31-35a6-49e5-82c7-d14ab68d6c64" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.
