
# Instruction

1. Open your new project on Android Studio
2. Create the following files
   
a. Create an XML file and name it **layout.XML** and use this code:
   <?xml version="1.0" encoding="utf-8"?>
   <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       android:gravity="center"
       android:background="#DBD1D4">
   
       <LinearLayout
           android:layout_width="match_parent"
           android:layout_height="wrap_content"
           android:orientation="vertical">
   
           <TextView
               android:layout_width="wrap_content"
               android:layout_height="wrap_content"
               android:layout_gravity="center"
               android:text="Welcome to Android Studio"
               android:textSize="50dp"
               android:textStyle="bold"
               android:layout_marginTop="20dp"/>
   
           <EditText
               android:id="@+id/username_text"
               android:layout_width="match_parent"
               android:layout_height="wrap_content"
               android:layout_marginTop="20dp"
               android:background="@drawable/border_edittext"
               android:hint="Username"
               android:inputType="text"
               android:padding="20dp">
   
           </EditText>
   
           <EditText
               android:id="@+id/password_text"
               android:layout_width="match_parent"
               android:layout_height="wrap_content"
               android:layout_marginTop="20dp"
               android:background="@drawable/border_edittext"
               android:hint="Password"
               android:inputType="textPassword"
               android:padding="20dp"></EditText>
   
           <Button
               android:id="@+id/login_btn"
               android:layout_width="match_parent"
               android:layout_height="wrap_content"
               android:layout_marginTop="20dp"
               android:padding="20dp"
               android:text="Login"
               android:background="@drawable/border_button">
           </Button>
       </LinearLayout>
   </RelativeLayout>

b. Create another XML file, name it **border_edittext.xml**, put it under the drawable folder and use this code
   <shape
       xmlns:android="http://schemas.android.com/apk/res/android"
       android:shape="rectangle">
       <solid
           android:color="@android:color/transparent"/>
   
       <corners
           android:bottomRightRadius="12dp"
           android:bottomLeftRadius="12dp"
           android:topLeftRadius="12dp"
           android:topRightRadius="12dp"
          />
       <stroke
           android:color="#8dbab3"
           android:width="2dp"/>
   </shape>

c. Create the last XML file, name it **border_button.xml**, put it under the drawable folder and use this code

   <?xml version="1.0" encoding="utf-8"?>
   <selector xmlns:android="http://schemas.android.com/apk/res/android" >
       <item >
           <shape android:shape="rectangle"  >
               <corners android:radius="3dp" />
               <stroke android:width="1dip" android:color="#5e7974" />
               <gradient android:angle="-90" android:startColor="#8dbab3" android:endColor="#58857e" />
           </shape>
       </item>
   </selector>

d. Under the **MainActivity.kt** make sure all Compose codes are removed. Use the following code inside the main class as shown below:

   package com.example.intent_application
   
   import android.os.Bundle
   import android.widget.Button
   import android.widget.EditText
   import androidx.activity.ComponentActivity
   import android.util.Log
   import android.widget.Toast
   
   class MainActivity : ComponentActivity() {
   
       lateinit var username : EditText
       lateinit var password : EditText
       lateinit var login : Button
   
   
       override fun onCreate(savedInstanceState: Bundle?) {
           super.onCreate(savedInstanceState)
           setContentView(R.layout.layout)
   
           username = findViewById(R.id.username_text)
           password = findViewById(R.id.password_text)
           login = findViewById(R.id.login_btn)
   
           login.setOnClickListener{
               val username_in = username.text.toString()
               val password_in = password.text.toString()
               Log.i("test", "Username: $username_in and Password: $password_in")
               Toast.makeText(this@MainActivity, "Username: $username_in and Password: $password_in", Toast.LENGTH_LONG).show()
           }
       }
   
   }
   
   
   
   
