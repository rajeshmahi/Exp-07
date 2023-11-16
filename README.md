# Ex.No:7 Develop an android application to display the place name with image using list view in android studio.
## AIM:
To develop an android application to display the place name with image using list view in android studio.
## EQUIPMENTS REQUIRED:
Latest Version Android Studio
## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “listview″ and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.
## PROGRAM
Name:Rajesh K

Reg No:212221220041
### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    tools:ignore="ExtraText">

    <ListView
        android:id="@+id/simpleListView"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:divider="@color/material_blue_grey_800"
        android:dividerHeight="1dp"
        android:footerDividersEnabled="false"
        tools:ignore="MissingConstraints" />
    />
</androidx.constraintlayout.widget.ConstraintLayout>
```
### activity_list.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="67dp"
        android:text="TextView"
        android:textAlignment="center"
        android:textSize="30sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.423"
        app:layout_constraintStart_toEndOf="@+id/icon"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.543" />

    <ImageView
        android:id="@+id/icon"
        android:layout_width="116dp"
        android:layout_height="93dp"
        android:layout_marginStart="16dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:srcCompat="@tools:sample/avatars" />
</androidx.constraintlayout.widget.ConstraintLayout>

```
### MainActivity.java
```
package com.example.hiba;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListAdapter;
import android.widget.ListView;

public class MainActivity extends AppCompatActivity {

    ListView simpleList;
    String[] countryList = {"India", "China", "australia", "Portugle", "America", "NewZealand","Sri Lanka","Korea","Japan","Bangladesh","Canada","Ukraine"};
    int flags[] = {R.drawable.india, R.drawable.china, R.drawable.australia, R.drawable.portugal,
            R.drawable.america, R.drawable.new_zealand,R.drawable.srilanka,R.drawable.korea,R.drawable.japan,R.drawable.bangladesh,R.drawable.canada,R.drawable.ukraine};

    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleList = (ListView)findViewById(R.id.simpleListView);
        CustomAdapter customAdapter = new CustomAdapter(getApplicationContext(), countryList, flags);
        simpleList.setAdapter((ListAdapter) customAdapter);
    }
}
```
### CustomAadapter.java
```
package com.example.hiba;


import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.TextView;

public class CustomAdapter extends BaseAdapter {
    Context context;
    String countryList[];
    int flags[];
    LayoutInflater inflter;

    public CustomAdapter(Context applicationContext, String[] countryList, int[] flags) {
        this.context = context;
        this.countryList = countryList;
        this.flags = flags;
        inflter = (LayoutInflater.from(applicationContext));
    }

    @Override
    public int getCount() {
        return countryList.length;
    }

    @Override
    public Object getItem(int i) {
        return null;
    }

    @Override
    public long getItemId(int i) {
        return 0;
    }

    @Override
    public View getView(int i, View view, ViewGroup viewGroup) {
        view = inflter.inflate(R.layout.activity_list, null);
        TextView country = (TextView) view.findViewById(R.id.textView);
        ImageView icon = (ImageView) view.findViewById(R.id.icon);
        country.setText(countryList[i]);
        icon.setImageResource(flags[i]);
        return view;
    }
}

```
## OUTPUT:
![image](https://github.com/HibaRajarajeswari/List-View/assets/129970809/d9b5bb41-cb13-4750-8d50-5f60d50e3ed0)
![image](https://github.com/HibaRajarajeswari/List-View/assets/129970809/26011a48-2cc4-498f-9e3d-90b1f452c17c)
![WhatsApp Image 2023-09-20 at 08 19 52](https://github.com/HibaRajarajeswari/List-View/assets/129970809/e0829906-f4df-4462-ae0f-6efe39f2a170)
![WhatsApp Image 2023-09-20 at 08 18 25](https://github.com/HibaRajarajeswari/List-View/assets/129970809/f7376910-47c5-46a9-90e4-304ccd67e4f6)



## RESULT:
Thus a Simple Android Application to create and develop the application using list view in android studio is developed and executed successfully.**
