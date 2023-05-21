# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

```
Step 1: Open Android Studio and then click on File -> New -> New project.
Step 2: Then type the Application name and click Next. 
Step 3: Then select the Minimum SDK as shown below and click Next.
Step 4: Then select the Empty Activity and click Next. Finally click Finish.
Step 5: Design layout in activity_main.xml
Step 6: Display message give in MainActivity file.
Step 7: Save and run the application.

```

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: SMRITI.B
Registeration Number : 212221040156
*/
```
## activity_main.xml:

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity"
android:orientation="vertical"
android:padding="20dp">
<EditText android:id="@+id/etNumber"
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:hint="@string/enter_the_number"
android:inputType="number"
android:layout_marginTop="50dp"
android:importantForAutofill="no" />
<Button
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:text="@string/factorial"
android:onClick="displayFactorial"/>
</LinearLayout>
```
## MainActivity.java:

```
package com.example.explicit_fact;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    EditText etNumber;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
      etNumber=findViewById(R.id.etNumber);
    }
    public void displayFactorial(View view){
     Intent i=new Intent(MainActivity.this,MainActivity2.class);
        i.putExtra("number",etNumber.getText().toString());
       startActivity(i);
   }
}
```

## activity_main2.xml:

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2"
    android:padding="20dp">
    <TextView android:id="@+id/tv"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:text="@string/factorial_of_number_is"
        style="@style/TextAppearance.AppCompat.Large"/>

</RelativeLayout>

```

## MainActivity2.java:

```
package com.example.explicit_fact;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity {
    TextView tv;
    @SuppressLint("SetTextI18n")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        Bundle b=getIntent().getExtras();
        int no=Integer.parseInt(b.getString("number"));
        long f=1;
        for(int i=no;i>0;i--)
        {
            f=f*i;
        }
        tv=findViewById(R.id.tv);
        tv.setText("Factorial of "+no+" is "+f);
    }
}
```

## OUTPUT

![activity1 output](https://github.com/smriti1910/EXPLICITINTENT_FACT/assets/133334803/42d766de-4837-4c0a-a7ad-299afa6f0855)
![activity2 output](https://github.com/smriti1910/EXPLICITINTENT_FACT/assets/133334803/d9b8aedb-bea8-4dd2-84fb-59598a0f3273)
![OUTPUT](https://github.com/smriti1910/EXPLICITINTENT_FACT/assets/133334803/e4fb5a46-b3f3-4afe-b1e4-565b7097498c)



## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

