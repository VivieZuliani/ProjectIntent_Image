# ProjectIntent_Image

# PROJECT INTENT

Nama : Vivie Zuliani Erikasari

NIM : 312210475

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

## Tugas
```
Buatlah tampilan menu Versi 02 dari project-project yang sudah dibuat sebelumnya 

dengan tambahan memanggil method Maps

dengan tampilan sebagai berikut :

![Picture](https://github.com/VivieZuliani/ProjectIntent_Image/assets/130271255/412b7f22-b8c1-43af-b82a-7995398e33c3)
```


## Hasil Run
> Berikut merupakan hasil running dari aplikasi yang telah saya buat :


https://github.com/VivieZuliani/ProjectIntent/assets/130271255/2edf1fa3-1ae8-49e2-8dc9-bf5c93d32598


> Splash Screen
1. Launcher Splash Logo

Pertama, yaitu membuat Launcher Splash Logo atau menampilkan logo / icon saat kita pertama kali membuka aplikasi.

Caranya :

A. Mempersiapkan logo atau background yang ingin dijadikan Laucher Splash

B. Jika filenya sudah tersedia, copy file lalu paste ke dalam `res`, kemudian `rename` (Pastikan untuk menggunakan huruf kecil semua)

C. Jika sudah selesai maka selanjutnya adalah menuliskan script agar file Launcher Splash Logo bisa muncul ke halaman pengguna.

> Pertama, kita buat  java class nya agar SplashActivity bisa berjalan, lalu pada `SplashActivity.java` kita masukkan kode dibawah ini :
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent intent = new Intent(SplashActivity.this, MainActivity.class);
                startActivity(intent);
                finish();
            }
        }, 1500);
    }
}

```
> Code di atas digukankan untuk menampilkan SplashScreen, ketika SplashScreen selesai dalam 2.5 detik maka akan langsung berpindah pada tampilan `MainActivity.java`.

- Selanjutnya, buka `AndroidManifest.xml`, kemudian tambahkan kode berikut ke dalam *application* :
```
 <activity
            android:name=".SplashActivity"
            android:exported="true"
            android:theme="@style/Theme.Design.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
```

Selesai sudah kita membuat perintah Launcher Splash  Logo, 

Selanjutnya kita akan ke tahap berikutnya yaitu membuat menu untuk menampilkan semua project yang sudah dibuat pada sudah dibuat pada pertemuan sebelumnya.

## 2. Menu Utama
> Yang kedua, disini kita akan membuat menu utamanya yang akan berjalan setelah SplashScreen Logo.

Caranya yaitu :

Jika awal pembuatan project kita memilih template Empty Views Activity, maka pada layout otomatis terbuat file `activity_main.xml` dan pada java akan ada `MainActivity.java`.

Maka langsung saja kita buka `activity_main.xml`, dan buat code seperti berikut ini:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/bground2"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="85dp"
        android:layout_height="16dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.173"/>

    <Button
        android:id="@+id/HelloButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="152dp"
        android:gravity="center_horizontal"
        android:text="Hallo"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/PCount"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.31" />

    <TextView
        android:id="@+id/PSianida"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.201"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.429" />

    <TextView
        android:id="@+id/PTwo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.22"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.567" />

    <TextView
        android:id="@+id/PAlarm"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.715" />

    <Button
        android:id="@+id/CountButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="220dp"
        android:gravity="center_horizontal"
        android:text="Count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/SianidaButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="288dp"
        android:gravity="center_horizontal"
        android:text="Sianida"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/bTwoButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="352dp"
        android:gravity="center_horizontal"
        android:text="Two"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/AlarmButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="420dp"
        android:gravity="center_horizontal"
        android:text="Alarm"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="48dp"
        android:text="Project Intent"
        android:textSize="35dp"
        android:textColor="@color/white"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

- Maka tampilannya akan seperti ini :

  ![<img width="610" alt="Screenshot 2023-11-24 004820](https://github.com/VivieZuliani/ProjectIntent/assets/130271255/e2a79096-cb08-4cc8-b5ee-ca1af9c16b5e)

- Setelah itu tambahkan code intent untuk masing-masing tombol pada `MainActivity.java` :
```
package com.example.project;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.provider.AlarmClock;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Find the HelloButton
        findViewById(R.id.AlarmButton).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
               startActivity(new Intent(MainActivity.this, AlarmActivity.class));
            }
        });
    }

    private void activity_alarm() {
        Intent activity_alarm = new Intent(AlarmClock.ACTION_SET_ALARM);
        startActivity(activity_alarm);
    }

    public void activity_hallo(View view) {
        Intent activity_hallo = new Intent(MainActivity.this, HalloActivity.class);
        startActivity(activity_hallo);
    }

    public void activity_count(View view) {
        Intent activity_count = new Intent(MainActivity.this, CountActivity.class);
        startActivity(activity_count);
    }

    public void activity_sianida(View view){
        Intent activity_sianida = new Intent(MainActivity.this, SianidaActivity.class);
        startActivity(activity_sianida);
    }

    public void activity_two(View view){
        Intent activity_two = new Intent(MainActivity.this, TwoActivity.class);
        startActivity(activity_two);
    }
    public void activity_Two2(View view) {
        Intent two2Activity = new Intent(MainActivity.this, Two2Activity.class);
        startActivity(two2Activity);
    }
}
```

> Button *activity_hallo, activity_sianida dan activity_two* menggunakan Explicit Intent, sedangkan project *activity_alarm* menggunakan Implicit Intent.

> Menu halaman utama dan tombol-tombol aplikasi sudah berhasil dibuat. Maka, selanjutnya yang perlu kita lakukan adalah menambahkan script pada `AndroidManifest.xml` agar aplikasi dapat berjalan.


## 3. AndroidManifest.xml
Didalam `AndroidManifest.xml` kita tambahkan semua java class dari semua project kita sebelumnya. Berikut nama java class dari berbagai project yang telah saya buat:

a. Project Hello World = HelloActivity.java

b. Project Count = CountActivity.java

c. Project Scroll Movie = SianidaActivity.java

d. Project TwoActivity = TwoActivity.java dan Two2Activity.java

e. Project Set Alarm = MainActivity.java (karena merupakan Implicit Intent, jadi code untuk set alarm langsung dibuat disini)

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission
        android:name="com.android.alarm.permission.SET_ALARM" />

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Project"
        tools:targetApi="31">

        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.SET_ALARM"/>
                <category android:name="android.intent.category.DEFAULT"/>
            </intent-filter>
        </activity>

        <activity
            android:name=".Two2Activity"
            android:exported="true" />

        <activity
            android:name=".TwoActivity"
            android:exported="true">
        </activity>

        <activity
            android:name=".SianidaActivity"
            android:exported="true" />

        <activity
            android:name=".CountActivity"
            android:exported="true" />

        <activity
            android:name=".HalloActivity"
            android:exported="true" />

        <activity
            android:name=".SplashActivity"
            android:exported="true"
            android:theme="@style/Theme.Design.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```


## 4. Code Values At Project (Strings, Colors, dan Dimens)
>`strings.xml`
```
<resources>
    <string name="app_name">Project</string>
    <string name="text">Bagiamana Kabar Anda Hari ini</string>
    <string name="article_title">Kasus Sianida </string>
    <string name="article_subtitle">ICE COLD!</string>
    <string name="article_text">In a vault deep inside Abbey Road Studios in London — protected by an unmarked, triple-locked, police-alarmed door — are something like 400 hours of unreleased Beatles recordings, starting from June 2, 1962 and ending with the very last tracks recorded for the Let It Be album. The best of the best were released by Apple Records in the form of the 3-volume Anthology series. For more information, see the Beatles Time Capsule at www.rockument.com. \n\n This volume starts with the first new Beatle song, “Free as a Bird” (based on a John Lennon demo, found only on The Lost Lennon Tapes Vol. 28, and covers the very earliest historical recordings, outtakes from the first albums, and live recordings from early concerts and BBC Radio sessions. \n\n

Highlights include: \n\n

Cry for a Shadow – Many a Beatle fanatic started down the outtake road, like I did, with a first listen to this song. Originally titled “Beatle Bop” and recorded in a single session that yielded four songs (the other three featured Tony Sheridan with the Beatles as a backing band), “Cry for a Shadow” is an instrumental written by Lennon and Harrison, which makes it unique to this day. John Lennon plays rhythm guitar, George Harrison plays lead guitar, Paul McCartney plays bass, and Pete Best plays drums. The sessions were produced by Bert Kaempfert in Hamburg, Germany, during the Beatles’ second visit from April through July of 1961 to play in the Reeperbahn-section clubs. \n\n

My Bonnie and Ain’t She Sweet — At the same session, the Beatles played on “My Bonnie” (the first-ever single with Beatles playing), as the backing band for English singer Tony Sheridan, originally a member of the Jets. The popularity of this single in Liverpool brought the Beatles to the attention of Brian Epstein, who worked in the NEMS record store and tried to meet demand for the disc. John Lennon then sings a fine “Ain’t She Sweet” (his first-ever released vocal). \n\n

Searchin — A Jerry Leiber – Mike Stoller comedy song that was a hit for the Coasters in 1957, and a popular live favorite of the Beatles. The Coasters also had a hit with “Besame Mucho” and the Beatles covered that song as well. Ringo Starr had by now replaced Pete Best on drums. The high falsetto is George, who also plays a hesitant lead guitar. This is from their first audition for Decca Records in London on Jan 1., 1962, live in the studio. The Grateful Dead would later cover “Searchin” with a similar arrangement, Pigpen doing the Paul vocals. A live version is available on outtake records featuring the Dead joined by the Beach Boys! \n\n

Love Me Do — An early version of the song, played a bit slower and with more of a blues feeling, and a cool bossa-nova beat in middle. Paul had to sing while John played harmonica — a first for the group. Pete Best played drums on this version. \n\n

She Loves You – Till There Was You – Twist and Shout — Live at the Princess Wales Theatre by Leicester Square in London, attended by the Queen. “Till There Was You” (by Meredith Wilson) is from the musical The Music Man and a hit for Peggy Lee in 1961. Before playing it, Paul said it was recorded by his favorite American group, “Sophie Tucker” (which got some laughs). At the end, John tells the people in the cheaper seats to clap their hands, and the rest to “rattle your jewelry” and then announces “Twist and Shout” (a song by Bert Russell and Phil Medley that was first recorded in 1962 by the Isley Brothers). A film of the performance shows the Queen smiling at John’s remark. \n\n

Leave My Kitten Alone — One of the lost Beatle songs recorded during the “Beatles For Sale” sessions but never released. This song, written by Little Willie John, Titus Turner, and James McDougal, was a 1959 RB hit for Little Willie John and covered by Johnny Preston before the Beatles tried it and shelved it. A reference to a “big fat bulldog” may have influenced John’s “Hey Bulldog” (Yellow Submarine album), which is a similar rocker. \n\n

One After 909 — A song recorded for the ¨C11C album was actually worked on way back in the beginning, six years earlier. This take shows how they did it much more slowly, with an RB feel to it.</string>

    <string name="button_main">Send</string>
    <string name="editText_main">Enter Your Message Here</string>
    <string name="text_header">Message Received</string>
    <string name="second_button">Reply</string>
    <string name="editText_second">Enter Your Reply Here</string>
    <string name="text_header_reply">Reply Received</string>

</resources>
```


>`colors.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="yellow">#FFFF00</color>
    <color name="blue">#0000FF</color>
    <color name="red">#FF0000</color>
    <color name="green">#00FF0C</color>
    <color name="purple">#EC00FF</color>
    <color name="orange">#FF6800</color>

    
    <array name="fibonacci_colors">
        <item>@color/black</item>
        <item>@color/white</item>
        <item>@color/red</item>
        <item>@color/green</item>
        <item>@color/purple</item>
        <item>@color/orange</item>
        <item>@color/blue</item>
    </array>

</resources>
```


>`dimen.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <dimen name="padding_regular">10dp</dimen>
    <dimen name="line_spacing">5sp</dimen>
</resources>
```

## 5. Code Layout and Java At Project (ALL)
### A. Code Alarm
> `activity_alarm.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    tools:context=".AlarmActivity">

</androidx.constraintlayout.widget.ConstraintLayout>
```

 
> `AlarmActivity.java`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    tools:context=".AlarmActivity">

</androidx.constraintlayout.widget.ConstraintLayout>
```


### B. Code Count
> `activity_count.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".MainActivity"
    tools:ignore="ExtraText">

    <TextView
        android:id="@+id/fibonacciNumberTextView"
        android:layout_width="435dp"
        android:layout_height="652dp"
        android:gravity="center_vertical"
        android:background="@color/yellow"
        android:text="0"
        android:textAlignment="center"
        android:textColor="@color/blue"
        android:textSize="110sp"
        app:layout_constraintBottom_toTopOf="@id/showFibonacciButton"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintVertical_bias="0.26"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/showToastButton"
        android:layout_width="192dp"
        android:layout_height="100dp"
        android:background="#2196F3"
        android:text="Toast"
        android:textColor="@color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="MissingConstraints"/>

    <LinearLayout
        android:id="@+id/buttonContainer"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="horizontal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        >

        <Button
            android:id="@+id/showFibonacciButton"
            android:layout_width="218dp"
            android:layout_height="100dp"
            android:background="#2196F3"
            android:text="Hitung" />

        <Button
            android:id="@+id/resetButton"
            android:layout_width="218dp"
            android:layout_height="100dp"
            android:background="#2196F3"
            android:text="Reset" />

    </LinearLayout>

    <Button
        android:id="@+id/enterMaxButton"
        android:layout_width="218dp"
        android:layout_height="100dp"
        android:background="#2196F3"
        android:text="Enter Max"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/backToMainButton"
        android:layout_width="215dp"
        android:layout_height="70dp"
        android:text="Kembali"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.85" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

> `CountActivity.java`
```
package com.example.project;

import android.content.DialogInterface;
import android.content.Intent;
import android.content.res.Resources;
import android.content.res.TypedArray;
import android.os.Build;
import android.os.Bundle;
import android.text.InputType;
import android.view.Gravity;
import android.view.View;
import android.widget.AutoCompleteTextView;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import java.util.Random;

public class CountActivity extends AppCompatActivity {
    private static final int NUM_COLORS = 7;
    private int previousFibonacci = 1;

    private int currentFibonacci = 0;
    private int maxFibonacciValue = 100; // Default max value
    private TextView textView;
    private Button showFibonacciButton;
    private Button resetButton;
    private Button showToastButton;
    private Button enterMaxButton;

    private void changeTextColor() {
        Resources res = getResources();
        TypedArray colors = res.obtainTypedArray(R.array.fibonacci_colors);

        int randomIndex = new Random().nextInt(NUM_COLORS);
        int randomColor = colors.getColor(randomIndex, 0);

        textView.setTextColor(randomColor);
    }

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_count);

        TextView fibonacciNumberTextView = findViewById(R.id.fibonacciNumberTextView);
            showFibonacciButton = findViewById(R.id.showFibonacciButton);
            resetButton = findViewById(R.id.resetButton);
            showToastButton = findViewById(R.id.showToastButton);
            enterMaxButton = findViewById(R.id.showToastButton);
            Button backToMainButton = findViewById(R.id.backToMainButton);

            backToMainButton.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    Intent intent = new Intent(CountActivity.this, MainActivity.class);
                    startActivity(intent);
                }
            });

            enterMaxButton.setOnClickListener(new View.OnClickListener(){
                @Override
                public void onClick(View v) {
                    showMaxInputDialog();
                }
            });

            showFibonacciButton.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    int nextFibonacci = currentFibonacci + previousFibonacci;

                    if (maxFibonacciValue == 0 || nextFibonacci <= maxFibonacciValue){
                        textView.setText(String.valueOf(nextFibonacci));
                        changeTextColor();
                        previousFibonacci = currentFibonacci;
                        currentFibonacci = nextFibonacci;
                    } else {
                        Toast.makeText(CountActivity.this, "Reached Max Fibonacci Value", Toast.LENGTH_SHORT).show();
                    }
                }
            });

            showToastButton.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    String toastMessage = "Fibonacci Number: " + currentFibonacci;
                    Toast toast = Toast.makeText(CountActivity.this, toastMessage, Toast.LENGTH_SHORT);
                    toast.setGravity(Gravity.TOP, 0, 16);
                    toast.show();
                }
            });

            resetButton.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    currentFibonacci = 0;
                    previousFibonacci = 1;
                    textView.setText("0");
                }
            });
    }

    private void showMaxInputDialog(){
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("Enter Max Number, 0 = No Limit");

        final EditText input = new EditText(this);
        input.setInputType(InputType.TYPE_CLASS_NUMBER);
        builder.setView(input);

        builder.setPositiveButton("OK", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialogInterface, int i) {
                try{
                    int newMax = Integer.parseInt(input.getText().toString());

                    if(newMax >= 0){
                        maxFibonacciValue = newMax;
                    } else {
                        Toast.makeText(CountActivity.this, "Enter a valid non-negative number", Toast.LENGTH_SHORT).show();
                    }
                } catch (NumberFormatException e){
                    Toast.makeText(CountActivity.this, "Invalid input", Toast.LENGTH_SHORT).show();
                }
            }
        });

        builder.setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialogInterface, int i) {
                dialogInterface.cancel();
            }
        });

        builder.show();
    }

}

```


### C. Code Hallo
> `activity_hallo.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/bground"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/text"
        android:textColor="@color/blue"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>

    <Button
        android:id="@+id/backToMainButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Back"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.976" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

> `HalloActivity.java`
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class HalloActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_hallo);

        Button backToMainButton = findViewById(R.id.backToMainButton);

        backToMainButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(HalloActivity.this, MainActivity.class);
                startActivity(intent);
            }
        });
    }
}

```


### D. Code Main
> `activity_main.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/bground2"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="85dp"
        android:layout_height="16dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.173"/>

    <Button
        android:id="@+id/HelloButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="152dp"
        android:gravity="center_horizontal"
        android:text="Hallo"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/PCount"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.31" />

    <TextView
        android:id="@+id/PSianida"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.201"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.429" />

    <TextView
        android:id="@+id/PTwo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.22"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.567" />

    <TextView
        android:id="@+id/PAlarm"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.196"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.715" />

    <Button
        android:id="@+id/CountButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="220dp"
        android:gravity="center_horizontal"
        android:text="Count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/SianidaButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="288dp"
        android:gravity="center_horizontal"
        android:text="Sianida"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/bTwoButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="352dp"
        android:gravity="center_horizontal"
        android:text="Two"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/AlarmButton"
        android:layout_width="320dp"
        android:layout_height="49dp"
        android:layout_marginTop="420dp"
        android:gravity="center_horizontal"
        android:text="Alarm"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.494"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="48dp"
        android:text="Project Intent"
        android:textSize="35dp"
        android:textColor="@color/white"
        android:textStyle="bold"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

> `MainActivity.java`
```
package com.example.project;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.provider.AlarmClock;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Find the HelloButton
        findViewById(R.id.AlarmButton).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
               startActivity(new Intent(MainActivity.this, AlarmActivity.class));
            }
        });
    }

    private void activity_alarm() {
        Intent activity_alarm = new Intent(AlarmClock.ACTION_SET_ALARM);
        startActivity(activity_alarm);
    }

    public void activity_hallo(View view) {
        Intent activity_hallo = new Intent(MainActivity.this, HalloActivity.class);
        startActivity(activity_hallo);
    }

    public void activity_count(View view) {
        Intent activity_count = new Intent(MainActivity.this, CountActivity.class);
        startActivity(activity_count);
    }

    public void activity_sianida(View view){
        Intent activity_sianida = new Intent(MainActivity.this, SianidaActivity.class);
        startActivity(activity_sianida);
    }

    public void activity_two(View view){
        Intent activity_two = new Intent(MainActivity.this, TwoActivity.class);
        startActivity(activity_two);
    }
    public void activity_Two2(View view) {
        Intent two2Activity = new Intent(MainActivity.this, Two2Activity.class);
        startActivity(two2Activity);
    }
}
```


### E. Code Sianida
> `activity_sianida.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".SianidaActivity">


    <TextView
        android:id="@+id/article_heading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/black"
        android:padding="@dimen/padding_regular"
        android:text="@string/article_title"
        android:textAppearance="@android:style/TextAppearance.DeviceDefault.Large"
        android:textColor="@android:color/white"
        android:textStyle="bold"/>

    <ScrollView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/article_heading">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <TextView
                android:id="@+id/article_subheading"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:padding="@dimen/padding_regular"
                android:text="@string/article_subtitle"
                android:textAlignment="center"
                android:textAppearance="@android:style/TextAppearance.DeviceDefault"
                android:textColor="#1AA0C1"/>

            <TextView
                android:id="@+id/article"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:autoLink="web"
                android:lineSpacingExtra="@dimen/line_spacing"
                android:padding="@dimen/padding_regular"
                android:text="@string/article_text"
                tools:ignore="VisualLintLongText"/>

            <Button
                android:id="@+id/backToMainButton"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="Back"
                app:layout_constraintBottom_toBottomOf="parent"
                app:layout_constraintEnd_toEndOf="parent"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintTop_toTopOf="parent"
                app:layout_constraintVertical_bias="0.976"/>

        </LinearLayout>
    </ScrollView>

</androidx.constraintlayout.widget.ConstraintLayout>
```

> `SianidaActivity.java`
```
package com.example.project;

import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class SianidaActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_sianida);

        @SuppressLint("MissingInflatedId") Button backToMainButton = findViewById(R.id.backToMainButton);

        backToMainButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(SianidaActivity.this, MainActivity.class);
                startActivity(intent);
            }
        });
    }
}

```


### F. Code Splash
> `activity_splash.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="@drawable/splash"
    tools:context=".SplashActivity">

</RelativeLayout>
```

> `SplashActivity.java`
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent intent = new Intent(SplashActivity.this, MainActivity.class);
                startActivity(intent);
                finish();
            }
        }, 1500);
    }
}

```


### G. Code Two2 (Reply Messsage)
> `activity_two2.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    tools:context=".Two2Activity">

    <ImageView
        android:id="@+id/background"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:adjustViewBounds="true"
        android:scaleType="centerCrop"/>

    <TextView
        android:id="@+id/text_header"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="16dp"
        android:text="@string/text_header"
        android:textAppearance="@style/TextAppearance.AppCompat.Medium"
        android:textStyle="bold"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>

    <TextView
        android:id="@+id/text_message"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="8dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/text_header" />

    <Button
        android:id="@+id/button_second"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="16dp"
        android:layout_marginRight="16dp"
        android:text="@string/second_button"
        android:onClick="returnReply"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        tools:ignore="UsingOnClickXml"/>

    <EditText
        android:id="@+id/editText_main"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="16dp"
        android:ems="10"
        android:hint="@string/editText_second"
        android:inputType="textLongMessage"
        android:minHeight="48dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@id/button_second"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

> `Two2Activity.java`
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class Two2Activity extends AppCompatActivity {

    public static final String EXTRA_REPLY = "com.example.project.extra.REPLY";
    public static final String EXTRA_MESSAGE = "com.example.project.extra.MESSAGE";
    private EditText mReply;

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_two2);

        mReply = findViewById(R.id.editText_main);

        Intent intent = getIntent();
        String message = intent.getStringExtra(Two2Activity.EXTRA_MESSAGE);

        TextView textView = findViewById(R.id.text_message);
        textView.setText(message);
    }

    public void returnReply(View view){
        String reply = mReply.getText().toString();
        Intent replyIntent = new Intent();
        replyIntent.putExtra(EXTRA_REPLY, reply);
        setResult(RESULT_OK, replyIntent);
        finish();
    }
}

```


### H. Code Two
> `activity_two.xml`
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".TwoActivity">

    <ImageView
        android:id="@+id/background"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:adjustViewBounds="true"
        android:scaleType="centerCrop"
        tools:layout_editor_absoluteX="0dp"
        tools:layout_editor_absoluteY="40dp"/>

    <TextView
        android:id="@+id/text_header_reply"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="16dp"
        android:text="@string/text_header_reply"
        android:textAppearance="@style/TextAppearance.AppCompat.Medium"
        android:textStyle="bold"
        android:visibility="invisible"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>

    <TextView
        android:id="@+id/text_message_reply"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginLeft="8dp"
        android:layout_marginTop="8dp"
        android:visibility="invisible"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/text_header_reply" />

    <Button
        android:id="@+id/button_main"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="16dp"
        android:layout_marginRight="16dp"
        android:text="@string/button_main"
        android:background="@color/blue"
        android:onClick="LaunchSecondActivity"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        tools:ignore="UsingOnClickInXml"/>

    <EditText
        android:id="@+id/editText_main"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="16dp"
        android:ems="10"
        android:hint="@string/editText_main"
        android:inputType="textLongMessage"
        android:minHeight="48dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartOf="@id/button_main"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/backToMainButton"
        android:layout_width="103dp"
        android:layout_height="47dp"
        android:layout_marginRight="8dp"
        android:layout_marginBottom="88dp"
        android:text="Back"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintRight_toRightOf="parent"/>
</androidx.constraintlayout.widget.ConstraintLayout>
```

> `TwoActivity.java`
```
package com.example.project;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class TwoActivity extends AppCompatActivity {
    private static final String LOG_TAG = TwoActivity.class.getSimpleName();
    private static final String EXTRA_MESSAGE = "com.example.project.extra.MESSAGE";
    public static final int TEXT_REQUEST = 1;
    private EditText mMessageEditText;
    private TextView mReplyHeadTextView;
    private TextView mReplyTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_two);

        mMessageEditText = findViewById(R.id.editText_main);
        mReplyHeadTextView = findViewById(R.id.text_header_reply);
        mReplyTextView = findViewById(R.id.text_message_reply);

        Button backToMainButton = findViewById(R.id.backToMainButton);

        backToMainButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(TwoActivity.this, MainActivity.class);
            }
        });
    }

    public void LaunchSecondActivity(View view) {
        Log.d(LOG_TAG, "Button clicked!");
        Intent intent = new Intent(this, Two2Activity.class);
        String message = mMessageEditText.getText().toString();
        intent.putExtra(EXTRA_MESSAGE, message);
        startActivityForResult(intent, TEXT_REQUEST);
    }

    @Override
    public void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        Log.d(LOG_TAG, "onActivityResult: requestCode=" + requestCode + ", resultCode=" + resultCode);
        if (requestCode == TEXT_REQUEST) {
            if (resultCode == RESULT_OK) {
                if (data != null) {
                    String reply = data.getStringExtra(Two2Activity.EXTRA_REPLY);
                    Log.d(LOG_TAG, "Reply received: " + reply);

                    mReplyHeadTextView.setVisibility(View.VISIBLE);
                    mReplyTextView.setText(reply);
                    mReplyTextView.setVisibility(View.VISIBLE);
                } else {
                    Log.e(LOG_TAG, "Intent data is null");
                }
            }
        }
    }
}
```

# Sekian Untuk Project Kali ini, Terima Kasih







