# ProjectIntent_Image

# PROJECT INTENT

Nama : Vivie Zuliani Erikasari

NIM : 312210475

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

## Tugas

Buatlah tampilan menu Versi 02 dari project-project yang sudah dibuat sebelumnya 

dengan tambahan memanggil method Maps

dengan tampilan sebagai berikut :

<img width="364" alt="Screenshot 2023-11-29 233050" src="https://github.com/VivieZuliani/ProjectIntent_Image/assets/130271255/32274b4c-eb4e-4805-be92-a4f70a2ecab4">


## Hasil Run
> Berikut merupakan hasil running dari aplikasi yang telah saya buat :


https://github.com/VivieZuliani/ProjectIntent_Image/assets/130271255/39875417-66a4-4240-9313-c7c512455a98


## Kode dan Keterangan
> Pertama, untuk kode sama seperti project sebelumnya namun ada tambahan `activity_map.xml` dan juga pada bagian java kita tambahkan `MapActivity.java` serta dilakukan perubahan pada tampilan halaman pertama yaitu menggunakan foto. jika sebelumnya menggunakan button, maka saat ini button tersebut di ubah menjadi image yang fungsinya sama seperti button pada tugas sebelumnya.

Berikut merupakan kode pada `activity_map.xml`:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall2"
    android:orientation="vertical"
    tools:context=".MapActivity">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Open google maps"
        android:layout_margin="20dp"
        android:textColor="@color/black"
        android:textStyle="bold"
        android:textSize="30dp"/>

    <androidx.cardview.widget.CardView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:cardCornerRadius="10dp"
        app:cardElevation="20dp"
        android:layout_margin="20dp" >

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:layout_margin="10dp">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="Lokasi awal anda"
                android:textStyle="bold"
                android:textColor="@color/black"
                android:textSize="16sp"/>

            <EditText
                android:id="@+id/etAwal"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Lokasi awal anda"
                android:minHeight="48dp" />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="Lokasi tujuan anda"
                android:textColor="@color/black"
                android:textSize="16sp"
                android:textStyle="bold" />

            <EditText
                android:id="@+id/etTujuan"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Lokasi tujuan anda"
                android:minHeight="48dp" />

            <ImageButton
                android:id="@+id/btnJalur"
                android:layout_width="48dp"
                android:layout_height="48dp"
                android:layout_marginLeft="145dp"
                android:background="@drawable/map" />

        </LinearLayout>

    </androidx.cardview.widget.CardView>

</LinearLayout>

```

Selanjutnya, ini merupakan kode `MapActivity.java` yang berguna untuk menjalankan `activity_map.xml`:
```
package com.example.mobile_icon;

import android.content.ActivityNotFoundException;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.EditText;
import android.widget.ImageButton;

import androidx.appcompat.app.AppCompatActivity;

public class MapActivity extends AppCompatActivity {

    private EditText etAwal, etTujuan;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_map);

        etAwal = findViewById(R.id.etAwal);
        etTujuan = findViewById(R.id.etTujuan);
        ImageButton btnJalur = findViewById(R.id.btnJalur);

        btnJalur.setOnClickListener(view -> {

            String asal = etAwal.getText().toString();
            String tujuan = etTujuan.getText().toString();

            DisplayJalur(asal, tujuan);
        });
    }

    private void DisplayJalur(String asal, String tujuan) {
        try {
            Uri uri = Uri.parse("https://www.google.co.in/maps/dir/" + asal + "/" + tujuan + "?entry=ttu");
            Intent intent = new Intent(Intent.ACTION_VIEW, uri);
            intent.setPackage("com.google.android.apps.maps");
            intent.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            startActivity(intent);
        }catch (ActivityNotFoundException e){
            Uri uri = Uri.parse("https://www.google.com/maps");
            Intent intent = new Intent(Intent.ACTION_VIEW, uri);
            intent.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            startActivity(intent);
        }

    }
}

```

> Tampilan halaman intent kali ini menggunakan image yang memiliki fungsi sama seperti button pada pertemuan sebelumnya.

Pada bagian `activity_home.xml`, kita ubah dari yang awalnya `<Button>` menjadi `<ImageButton>`, kemudian pada bagian java juga kita ubah agar `activity_home.xml` bisa berjalan sebagaimana semestinya, seperti berikut ini  :


- `activity_home.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/home"
    tools:context=".home">

    <TextView
        android:id="@+id/imageView"
        android:layout_width="422dp"
        android:layout_height="786dp"
        android:layout_marginTop="66dp"
        android:text="ALL PROJECT"
        android:textAlignment="center"
        android:textColor="@color/white"
        android:textSize="50dp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.545"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0" />

    <ImageButton
        android:id="@+id/button_move_hallo"
        android:layout_width="140dp"
        android:layout_height="100dp"
        android:background="@drawable/hai"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.059"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.323" />

    <ImageButton
        android:id="@+id/button_move_count"
        android:layout_width="140dp"
        android:layout_height="100dp"
        android:background="@drawable/calc"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.538"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.323" />

    <ImageButton
        android:id="@+id/button_move_to_other_scroll"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@drawable/news"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.919"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.323" />

    <ImageButton
        android:id="@+id/buttonMoveToOtherActivity"
        android:layout_width="140dp"
        android:layout_height="100dp"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:background="@drawable/send"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.059"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.524" />

    <ImageButton
        android:id="@+id/button_move_to_alarm"
        android:layout_width="130dp"
        android:layout_height="126dp"
        android:background="@drawable/jam"
        android:onClick="moveToAnotherActivity"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.555"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.527"
        tools:ignore="SpeakableTextPresentCheck" />

    <ImageButton
        android:id="@+id/button_map"
        android:layout_width="119dp"
        android:layout_height="123dp"
        android:background="@drawable/map"
        android:onClick="map"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.945"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.529"
        tools:ignore="SpeakableTextPresentCheck" />


</androidx.constraintlayout.widget.ConstraintLayout>

```


- Masukkan kode `home.java` agar `activity_home.xml` dapat digunakan.
```
package com.example.mobile_icon;

import android.content.Intent;
import android.os.Bundle;
import android.widget.ImageButton;

import androidx.appcompat.app.AppCompatActivity;

public class home extends AppCompatActivity {
    private ImageButton btnMove;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);

        btnMove = findViewById(R.id.button_move_count);

        btnMove.setOnClickListener(view -> {
            Intent i = new Intent(home.this, FiboActivity.class);
            startActivity(i);
        });

        ImageButton buttonMovehallo = findViewById(R.id.button_move_hallo);
        buttonMovehallo.setOnClickListener(v -> {
            Intent intent = new Intent(home.this, MainActivity.class);
            startActivity(intent);
        });

        ImageButton buttonMoveToScroll = findViewById(R.id.button_move_to_other_scroll);
        buttonMoveToScroll.setOnClickListener(v -> {
            Intent intent = new Intent(home.this, scrollActivity.class);
            startActivity(intent);
        });

        ImageButton buttonMoveToOtherActivity = findViewById(R.id.buttonMoveToOtherActivity);
        buttonMoveToOtherActivity.setOnClickListener(v -> {
            Intent intent = new Intent(home.this, KeduaActivity.class);
            startActivity(intent);
        });

        ImageButton buttonMoveToalarm = findViewById(R.id.button_move_to_alarm);
        buttonMoveToalarm.setOnClickListener(v -> {
            Intent intent = new Intent(home.this, SetAlarm.class);
            startActivity(intent);
        });

        ImageButton buttonMoveToMap = findViewById(R.id.button_map);
        buttonMoveToMap.setOnClickListener(v -> {
            Intent intent = new Intent(home.this,MapActivity.class);
            startActivity(intent);
        });
    }
}

```

- Selanjutnya, buka `AndroidManifest.xml`, kemudian tambahkan kode berikut ke dalam *activity* agar map dapat menampilkan halamannya :
```
<activity
            android:name=".MapActivity"
            android:exported="false"/>

```


> Selesai sudah kita membuat perintah tambahan untuk Maps,

Selanjutnya kita akan ke tahap berikutnya yaitu membuat menu untuk menampilkan semua project yang sudah dibuat pada sudah dibuat pada pertemuan sebelumnya.


## 2. Menu Utama

### .xml

> 'AndroidManifest.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
    <uses-permission android:name="android.permission.VIBRATE" />

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@drawable/duck"
        android:label="@string/app_name"
        android:roundIcon="@drawable/duck"
        android:supportsRtl="true"
        android:theme="@style/Base.Theme.Mobile_icon"
        tools:targetApi="31">
        <activity
            android:name=".home"
            android:exported="false" />
        <activity
            android:name=".MainActivity"
            android:exported="true" />
        <activity
            android:name=".SetAlarm"
            android:exported="true" />

        <receiver android:name=".AlarmReceiver" />

        <activity
            android:name=".activitySplash"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".FiboActivity" />
        <activity android:name=".scrollActivity" />
        <activity android:name=".pertamaActivity" />
        <activity android:name=".KeduaActivity" />
        <activity
            android:name=".MapActivity"
            android:exported="false"/>
    </application>

</manifest>

```


> 'activity_main.xml '
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/duck"
    tools:context="com.example.mobile_icon.MainActivity">

    <TextView
        android:id="@+id/text_header"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/Kabar"
        android:textColor="@color/white"
        android:textSize="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.493"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.198" />


</androidx.constraintlayout.widget.ConstraintLayout>

```


> 'activity_fibo.xml'
  ```
  <?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall"
    tools:context=".FiboActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="523dp"
        android:layout_height="100dp"
        android:onClick="setLimit"
        android:text="Masukan Angka Limit"
        android:textColor="@color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button2"
        android:layout_width="204dp"
        android:layout_height="90dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="Count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.99"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/Reset"
        android:layout_width="204dp"
        android:layout_height="90dp"
        android:background="@color/colorPrimary"
        android:onClick="Back"
        android:text="@string/Back"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore=",Rtlcompat" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="407dp"
        android:layout_height="626dp"
        android:gravity="center_vertical"
        android:text="0"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button2"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_toast"
        app:layout_constraintVertical_bias="0.571"
        tools:ignore=",Rtlcompat" />

</androidx.constraintlayout.widget.ConstraintLayout>

  ```


> 'activity_pertama.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall2"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    tools:context=".pertamaActivity">

    <TextView
        android:id="@+id/text_header_reply"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="25dp"
        android:layout_marginEnd="16dp"
        android:textColor="@color/black"
        android:textStyle="bold"
        android:text="@string/text_header_reply"
        android:textAppearance="@style/TextAppearance.AppCompat.Medium"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button_main"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="16dp"
        android:layout_marginEnd="16dp"
        android:onClick="launchSecondActivity"
        android:text="@string/button_main"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/text_message_reply" />

    <TextView
        android:id="@+id/text_message_reply"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:visibility="visible"
        android:textColor="@color/white"
        app:layout_constraintTop_toBottomOf="@+id/text_header_reply"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="16dp"
        android:layout_marginStart="16dp"
        android:layout_marginEnd="16dp"/>

    <EditText
        android:id="@+id/editText_main"
        android:layout_width="224dp"
        android:layout_height="66dp"
        android:layout_marginStart="16dp"
        android:layout_marginTop="60dp"
        android:layout_marginEnd="16dp"
        android:textColor="@color/white"
        android:ems="10"
        android:hint="@string/editText_main"
        android:inputType="textLongMessage"
        app:layout_constraintEnd_toEndOf="@id/button_main"
        app:layout_constraintStart_toStartOf="@id/button_main"
        app:layout_constraintTop_toTopOf="@id/button_main" />

</androidx.constraintlayout.widget.ConstraintLayout>

```


> 'activity_kedua.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall2"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".KeduaActivity">

    <TextView
        android:id="@+id/text_header"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/text_header"
        android:textColor="@color/black"
        android:textAppearance="@style/TextAppearance.AppCompat.Medium"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="20dp"
        android:layout_marginStart="16dp"
        android:layout_marginEnd="16dp"/>

    <EditText
        android:id="@+id/editText_second"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="15dp"
        android:layout_marginEnd="16dp"
        android:ems="10"
        android:textColor="@color/black"
        android:hint="@string/editText_second"
        android:inputType="textLongMessage"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/text_header" />

    <TextView
        android:id="@+id/text_message"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        app:layout_constraintTop_toBottomOf="@+id/editText_second"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginStart="16dp"
        android:layout_marginEnd="16dp"/>

    <Button
        android:id="@+id/button_second"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_second"
        android:onClick="returnReply"
        app:layout_constraintTop_toBottomOf="@+id/text_message"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="-30dp"
        android:layout_marginStart="16dp"
        android:layout_marginEnd="0dp"/>

</androidx.constraintlayout.widget.ConstraintLayout>

```


> 'activity_scroll.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall"
    >

    <TextView
        android:id="@+id/artikel_heading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/black"
        android:padding="@dimen/padding_regular"
        android:text="@string/articel_title"
        android:textAlignment="center"
        android:textAppearance="@android:style/TextAppearance.DeviceDefault.Large"
        android:textColor="@android:color/white"
        android:textStyle="bold" />

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@id/artikel_heading">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:id="@+id/arikel_subheading"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:padding="@dimen/padding_regular"
                android:text="@string/articel_subtitle"
                android:textAlignment="center"
                android:textColor="@color/red"
                android:textAppearance="@android:style/TextAppearance.DeviceDefault"/>

            <TextView
                android:id="@+id/artikel"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:autoLink="web"
                android:textColor="@color/black"
                android:lineSpacingExtra="@dimen/padding_regular"
                android:text="@string/articel_text" />
        </LinearLayout>
    </ScrollView>
</RelativeLayout>

```


> 'activity_set_alarm.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/wall2"
    tools:context=".SetAlarm">

    <TimePicker
        android:id="@+id/timePicker"
        android:layout_width="408dp"
        android:layout_height="609dp"
        android:layout_gravity="center"
        android:numbersTextColor="@color/black"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ToggleButton
        android:id="@+id/toggleButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_margin="20dp"
        android:layout_marginTop="8dp"
        android:checked="false"
        android:onClick="OnToggleClicked"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/timePicker" />

</androidx.constraintlayout.widget.ConstraintLayout>

```


> 'activity_splash.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    tools:context=".activitySplash">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center">

        <ImageView
            android:layout_width="450dp"
            android:layout_height="match_parent"
            android:background="@drawable/duck" />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="V.2.0"
            android:textSize="25dp"
            android:layout_marginTop="0dp"
            android:textStyle="italic"
            android:textColor="@color/red"/>
    </LinearLayout>

    <ProgressBar
        android:id="@+id/pb"
        style="@style/Widget.AppCompat.ProgressBar.Horizontal"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_alignParentBottom="true"
        android:outlineSpotShadowColor="@color/red"/>
</RelativeLayout>

```
  

### .java
> 'MainActivity.java'
```
package com.example.mobile_icon;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

```


> 'FiboActivity.java'
```
package com.example.mobile_icon;

import android.app.AlertDialog;
import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class FiboActivity extends AppCompatActivity {
    private TextView showCount;
    private int count = 1;
    private long fibNMinus1 = 1;
    private long fibNMinus2 = 1;
    private int limit = -1; // Inisialisasi limit dengan nilai default

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fibo);

        showCount = findViewById(R.id.show_count);
    }

    public void countUp(View view) {
        if (count == 0) {
            showCount.setText("0");
        } else if (count == 1) {
            showCount.setText("1");
        } else {
            if (limit != -1 && count > limit) {
                // Jika count melebihi limit, atur ulang perhitungan
                count = 0;
                fibNMinus1 = 1;
                fibNMinus2 = 0;
                showCount.setText(getString(R.string.count_initial_value));
            } else {
                long fibCurrent = fibNMinus1 + fibNMinus2;
                fibNMinus2 = fibNMinus1;
                fibNMinus1 = fibCurrent;

                // Mengubah warna teks menjadi warna RGB dengan warna yang berbeda setiap kali angka berubah
                int red = (int) (Math.random() * 256);
                int green = (int) (Math.random() * 256);
                int blue = (int) (Math.random() * 256);
                showCount.setTextColor(Color.rgb(red, green, blue));

                showCount.setText(String.valueOf(fibCurrent));
            }
        }

        count++;
    }

    public void Back(View view) {
        count = 1;
        fibNMinus1 = 1;
        fibNMinus2 = 0;
        showCount.setText(getString(R.string.count_initial_value));
    }

    public void setLimit(View view) {
        // Create and display a dialog to set the limit
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("Set Limit");

        final EditText input = new EditText(this);
        input.setInputType(android.text.InputType.TYPE_CLASS_NUMBER);
        builder.setView(input);

        builder.setPositiveButton("OK", (dialog, which) -> {
            // Get the limit from the input and set it for calculations
            String limitStr = input.getText().toString();
            limit = Integer.parseInt(limitStr);
        });

        builder.setNegativeButton("Cancel", (dialog, which) -> dialog.cancel());


        builder.show();
    }
}

```


> 'pertamaActivity.java'
```
package com.example.mobile_icon;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;

public class pertamaActivity extends AppCompatActivity {

    private static final String LOG_TAG = pertamaActivity.class.getCanonicalName();
    public static final String EXTRA_MESSAGE = "com.example.android.KeduaActivity.extra.MESSAGE";
    public static final int TEXT_REQUEST = 1;
    private EditText mMessageEditText;
    private TextView mReplyHeadTextView;
    private TextView mReplyTextView;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_pertama);

        mMessageEditText = findViewById(R.id.editText_main);
        mReplyHeadTextView = findViewById(R.id.text_header_reply);
        mReplyTextView = findViewById(R.id.text_message_reply);
    }

    public void launchSecondActivity(View view) {
        Intent intent = new Intent(this, KeduaActivity.class);
        startActivity(intent);
    }
}

```


> 'KeduaActivity.java'
```
package com.example.mobile_icon;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;

public class KeduaActivity extends AppCompatActivity {
    public static final String EXTRA_REPLY = "com.hello.extra.REPLY";
    Button button_second;
    private EditText mReply;

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_kedua);

        mReply = findViewById(R.id.editText_second);


        Intent intent = getIntent();
        String message = intent.getStringExtra(pertamaActivity.EXTRA_MESSAGE);

        TextView textView = findViewById(R.id.text_message);
        textView.setText(message);

        button_second = findViewById(R.id.button_second);
        button_second.setOnClickListener(v -> {
            Intent intent1 = new Intent(
                    KeduaActivity.this, pertamaActivity.class
            );
            startActivity(intent1);
        });


    }

    @Override
    public void onBackPressed() {
        Intent replyIntent = new Intent();
        String reply = mReply.getText().toString();
        replyIntent.putExtra(EXTRA_REPLY, reply);
        setResult(RESULT_OK, replyIntent);
        super.onBackPressed();
    }
}

```


> 'scrollActivity.java'
```
package com.example.mobile_icon;

import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

public class scrollActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_scroll);

    }
}

```


> 'SetAlarm.java'
```
package com.example.mobile_icon;

import android.app.AlarmManager;
import android.app.PendingIntent;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.TimePicker;
import android.widget.Toast;
import android.widget.ToggleButton;

import androidx.appcompat.app.AppCompatActivity;

import java.util.Calendar;

public class SetAlarm extends AppCompatActivity {
    TimePicker alarmTimePicker;
    PendingIntent pendingIntent;
    AlarmManager alarmManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_set_alarm);

        alarmTimePicker = findViewById(R.id.timePicker);
        alarmManager = (AlarmManager) getSystemService(ALARM_SERVICE);

    }

    public void OnToggleClicked(View view) {
        long time;
        if (((ToggleButton) view).isChecked()) {
            Toast.makeText(SetAlarm.this, "ALARM ON", Toast.LENGTH_SHORT).show();
            Calendar calendar = Calendar.getInstance();

            calendar.set(Calendar.HOUR_OF_DAY, alarmTimePicker.getHour());
            calendar.set(Calendar.MINUTE, alarmTimePicker.getMinute());

            Intent intent = new Intent(this, AlarmReceiver.class);

            pendingIntent = PendingIntent.getBroadcast(this, 0, intent, PendingIntent.FLAG_IMMUTABLE);

            time = (calendar.getTimeInMillis() - (calendar.getTimeInMillis() % 60000));
            if (System.currentTimeMillis() > time) {

                if (Calendar.AM_PM == 0)
                    time = time + (1000 * 60 * 60 * 12);
                else
                    time = time + (1000 * 60 * 60 * 24);
            }

            alarmManager.setRepeating(AlarmManager.RTC, time, 10000, pendingIntent);

        } else {
            alarmManager.cancel(pendingIntent);
            Toast.makeText(SetAlarm.this, "ALARM OFF", Toast.LENGTH_SHORT).show();
        }
    }
}

```


> 'activitySplash'
```
package com.example.mobile_icon;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;
import android.view.View;
import android.widget.ProgressBar;

import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.app.AppCompatDelegate;

import java.util.Timer;
import java.util.TimerTask;

public class activitySplash extends AppCompatActivity {
    private static final int SPLASH_TIME_OUT = 10000;
    ProgressBar pb;
    int counter = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);
        prog();

        AppCompatDelegate.setCompatVectorFromResourcesEnabled(true);
        final Handler handler = new Handler();
        handler.postDelayed(() -> {
            startActivity(new Intent(getApplicationContext(), home.class));
            finish();
        }, 10000);

        View decorView = getWindow().getDecorView();
        decorView.setSystemUiVisibility(View.SYSTEM_UI_FLAG_FULLSCREEN);
        if (getSupportActionBar() != null){
            getSupportActionBar().hide();
        }

        new Handler().postDelayed(() -> {
            Intent intent = new Intent(activitySplash.this, home.class);
            startActivity(intent);
            finish();
        }, SPLASH_TIME_OUT);

    }
    public void prog(){
        pb= findViewById(R.id.pb);
        final Timer t = new Timer();
        TimerTask tt=new TimerTask() {
            @Override
            public void run() {
                counter++;
                pb.setProgress(counter);

                if (counter == 100)
                    t.cancel();
            }
        };
        t.schedule(tt,0, 100);
    }
}

```


> 'AlarmReceiver'
```
package com.example.mobile_icon;

import android.content.BroadcastReceiver;
import android.content.ContentResolver;
import android.content.Context;
import android.content.Intent;
import android.media.Ringtone;
import android.media.RingtoneManager;
import android.net.Uri;
import android.os.Build;
import android.os.Vibrator;
import android.widget.Toast;

import androidx.annotation.RequiresApi;

public class AlarmReceiver extends BroadcastReceiver {
    @RequiresApi(api = Build.VERSION_CODES.Q)
    @Override
    public void onReceive(Context context, Intent intent) {
        Vibrator vibrator = (Vibrator) context.getSystemService(Context.VIBRATOR_SERVICE);
        if (vibrator != null) {
            vibrator.vibrate(1000);
        }

        Toast.makeText(context, "Alarm! Wake up! Wake up!", Toast.LENGTH_LONG).show();

        Uri alarmUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_ALARM);
        if (alarmUri == null) {
            alarmUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION);
        }
        Uri.parse(ContentResolver.SCHEME_ANDROID_RESOURCE + "://" + context.getPackageName() + "/" + R.raw.ringtone_pirates);


        Ringtone ringtone = RingtoneManager.getRingtone(context, alarmUri);
        if (ringtone != null) {

            ringtone.play();
        }
    }
}

```


### values
> 'colors.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="biru">#0000FF</color>
    <color name="pink">#FFC0CB</color>
    <color name="red">#FF0000</color>
    <color name="SkyBlue">#87CEEB</color>
    <color name="colorPrimary">#3F51B5</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
    <color name="Yellow">#FFEB3B</color>
    <color name="Biru">#3F51B5</color>
</resources>

```


> 'dimen.xml'
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <dimen name="padding_regular">10dp</dimen>
    <dimen name="line_spacing">5sp</dimen>
</resources>

```


> 'strings.xml'
```
<resources>
    <string name="app_name">Project Mobile</string>
    <string name="Kabar">Hello, Bagaimana Kabarmu Hari Ini?</string>

    <string name="Button_label_toast">Toast</string>
    <string name="Button_label_count">Hitung</string>
    <string name="count_initial_value">0</string>
    <string name="toast_message">Keren njirr</string>

    <string name="articel_title">Kasus Sianida</string>
    <string name="articel_subtitle">ICE COLD!</string>
    <string name="articel_text">In a vault deep inside Abbey Road Studios in London — protected by
        an unmarked,triple-locked, police-alarmed door — are something like 400 hours of unreleased
        Beatles recordings,starting from June 2, 1962 and ending with the very last tracks recorded
        for the Let It Be album.The best of the best were released by Apple Records in the form of
        the 3-volume Anthology series.For more information, see the Beatles Time Capsule at
        www.rockument.com. \n\n

        This volume starts with the first new Beatle song, “Free as a Bird” (based on a John Lennon
        demo,found only on The Lost Lennon Tapes Vol. 28, and covers the very earliest historical
        recordings,outtakes from the first albums, and live recordings from early concerts and BBC
        Radio sessions. \n\n

        Highlights include: \n\n

        Cry for a Shadow – Many a Beatle fanatic started down the outtake road, like I did,
        with a first listen to this song. Originally titled “Beatle Bop” and recorded in a single
        session that yielded four songs (the other three featured Tony Sheridan with the Beatles as
        a backing band),“Cry for a Shadow” is an instrumental written by Lennon and Harrison, which
        makes it unique to this day.John Lennon plays rhythm guitar, George Harrison plays lead
        guitar, Paul McCartney plays bass,and Pete Best plays drums. The sessions were produced by
        Bert Kaempfert in Hamburg, Germany,during the Beatles’ second visit from April through July
        of 1961 to play in the Reeperbahn-section clubs. \n\n

        My Bonnie and Ain’t She Sweet — At the same session, the Beatles played on “My Bonnie”
        (the first-ever single with Beatles playing), as the backing band for English singer Tony
        Sheridan,originally a member of the Jets. The popularity of this single in Liverpool brought
        the Beatles to the attention of Brian Epstein, who worked in the NEMS record store and tried
        to meet demand for the disc. John Lennon then sings a fine “Ain’t She Sweet” (his first-ever
        released vocal). \n\n

        Searchin — A Jerry Leiber – Mike Stoller comedy song that was a hit for the Coasters in 1957
        ,and a popular live favorite of the Beatles. The Coasters also had a hit with “Besame Mucho”
        and the Beatles covered that song as well. Ringo Starr had by now replaced Pete Best on
        drums.The high falsetto is George, who also plays a hesitant lead guitar. This is from their
        first audition for Decca Records in London on Jan 1., 1962, live in the studio. The Grateful
        Dead would later cover“Searchin” with a similar arrangement, Pigpen doing the Paul vocals.
        A live version is available onouttake records featuring the Dead joined by the Beach Boys!
        \n\n

        Love Me Do — An early version of the song, played a bit slower and with more of a blues
        feeling, and a cool bossa-nova beat in middle. Paul had to sing while John played harmonica
        a first for the group.Pete Best played drums on this version. \n\n

        She Loves You – Till There Was You – Twist and Shout — Live at the Princess Wales Theatre by
        Leicester Square in London, attended by the Queen. “Till There Was You” (by Meredith Wilson)
        is from the musical The Music Man and a hit for Peggy Lee in 1961. Before playing it,
        Paul said it was recorded by his favorite American group, “Sophie Tucker” (which got some
        laughs).At the end, John tells the people in the cheaper seats to clap their hands, and the
        rest to “rattle your jewelry” and then announces “Twist and Shout” (a song by Bert Russell
        and Phil Medley that was first recorded in 1962 by the Isley Brothers). A film of the
        performance shows the Queen smiling at John’s remark. \n\n

        Leave My Kitten Alone — One of the lost Beatle songs recorded during the “Beatles For Sale”
        sessions but never released.This song, written by Little Willie John, Titus Turner, and
        James McDougal, was a 1959 R and B hit for Little Willie John and covered by Johnny Preston
        before the Beatles tried it and shelved it. A reference to a “big fat bulldog” may have
        influenced John’s “Hey Bulldog” (Yellow Submarine album), which is a similar rocker. \n\n

        One After 909 — A song recorded for the ¨C11C album was actually worked on way back in the
        beginning,six years earlier. This take shows how they did it much more slowly, with an
        R and B feel to it.Posted on October 7, 2023Leave a comment on PROJECT SCROLLING TEXT
    </string>
    <string name="button_main">Send</string>
    <string name="edittext_main">Send</string>
    <string name="text_header">Enter your message here</string>
    <string name="button_second">Reply</string>
    <string name="edittext_second">Enter your reply here</string>
    <string name="text_header_reply">Reply Received</string>
    <string name="Back">Reset</string>
    <string name="editText_main">Enter Your Message</string>
    <string name="editText_second">Enter Your Reply</string>
</resources>

```


## Sekian, Terima kasih.














