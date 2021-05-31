Hello Toast Activity_main.xml CODE:

<Button
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_weight="0.5"
    android:id="@+id/toast"
    android:text="Toast"/>

<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:id="@+id/tv"
    android:text="0"
    android:textSize="150sp"
    android:layout_weight="9"
    android:gravity="center"/>

<Button
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:id="@+id/count"
    android:text="Count"
    android:layout_weight="0.5"/>
MainActivity.java

CODE:

package com.example.hellotoast;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle; import android.view.View; import android.widget.Button; import android.widget.TextView; import android.widget.Toast;

public class MainActivity extends AppCompatActivity { //Declare the views here Button toast,count; TextView tv; int i = 0;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    //Intialise the views here
    toast = findViewById(R.id.toast);
    count = findViewById(R.id.count);
    tv = findViewById(R.id.tv);
     count.setOnClickListener(new View.OnClickListener() {
         @Override
         public void onClick(View v) {
             i++;
             tv.setText(""+i);
             //tv.setText(String.valueof(i));
         }
     });
     toast.setOnClickListener(new View.OnClickListener() {
         @Override
         public void onClick(View v) {
             Toast.makeText(MainActivity.this,
                     "Welcome to Android.Your count is"+i,
                     Toast.LENGTH_SHORT).show();
         }
     });
}
}

