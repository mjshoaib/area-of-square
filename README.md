# area-of-square
xml file-
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/lengthEditText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter length" />

    <Button
        android:id="@+id/calculateButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/lengthEditText"
        android:layout_marginTop="16dp"
        android:text="Calculate" />

    <TextView
        android:id="@+id/resultTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/calculateButton"
        android:layout_marginTop="16dp"
        android:textSize="18sp"
        android:text="The area of the square will be displayed here." />

</RelativeLayout>



 java file-
 package com.example.areaofsquare;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private EditText lengthEditText;
    private Button calculateButton;
    private TextView resultTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        lengthEditText = findViewById(R.id.lengthEditText);
        calculateButton = findViewById(R.id.calculateButton);
        resultTextView = findViewById(R.id.resultTextView);

        calculateButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String lengthString = lengthEditText.getText().toString();

                if (lengthString.isEmpty()) {
                    resultTextView.setText("Please enter the length.");
                    return;
                }

                int length = Integer.parseInt(lengthString);

                int area = length * length;

                resultTextView.setText("The area of the square is: " + area);
            }
        });
    }
}
 
