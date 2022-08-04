package com.example.qgp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import com.example.qgp.databinding.ActivityMainBinding

class MainActivity : AppCompatActivity() {
    lateinit var binding: ActivityMainBinding
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        binding = ActivityMainBinding.inflate(layoutInflater)
        setContentView(binding.root)
        binding.tvText.setOnClickListener {
            binding.tvText.text = getQuotes()
        }
    }
    private fun getQuotes(): String{
        return resources.getStringArray(R.array.quotes)[randomNumber()]
    }
    private fun randomNumber(): Int{
        val size = resources.getStringArray(R.array.quotes).size - 1
        return (0..size). random()
    }
}

//////////////////////


<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.QGP" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>



///////////

<?xml version="1.0" encoding="utf-8"?><!--
   Sample data extraction rules file; uncomment and customize as necessary.
   See https://developer.android.com/about/versions/12/backup-restore#xml-changes
   for details.
-->
<data-extraction-rules>
    <cloud-backup>
        <!-- TODO: Use <include> and <exclude> to control what is backed up.
        <include .../>
        <exclude .../>
        -->
    </cloud-backup>
    <!--
    <device-transfer>
        <include .../>
        <exclude .../>
    </device-transfer>
    -->
</data-extraction-rules>





/////////////////////////

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="com.example.qgp">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.QGP"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>



////////////////////////////

<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string-array name="quotes">
        <item>Что разум человека может постигнуть и во что он может поверить, того он способен достичь.
Наполеон Хилл, журналист и писатель </item>
        <item>Стремитесь не к успеху, а к ценностям, которые он дает.
Альберт Эйнштейн </item>
        <item>Своим успехом я обязана тому, что никогда не оправдывалась и не принимала оправданий от других.
Флоренс Найтингейл</item>
        <item>За свою карьеру я пропустил более 9000 бросков, проиграл почти 300 игр. 26 раз мне доверяли сделать финальный победный бросок, и я промахивался. Я терпел поражения снова, и снова, и снова. И именно поэтому я добился успеха.
Майкл Джордан</item>
        <item>Сложнее всего начать действовать, все остальное зависит только от упорства.
Амелия Эрхарт</item>
        <item>Надо любить жизнь больше, чем смысл жизни.
Федор Достоевский</item>
        <item>Жизнь - это то, что с тобой происходит, пока ты строишь планы.
Джон Леннон</item>
        <item>Логика может привести Вас от пункта А к пункту Б, а воображение — куда угодно.
Альберт Эйнштейн</item>
        <item>Через 20 лет вы будете больше разочарованы теми вещами, которые вы не делали, чем теми, которые вы сделали. Так отчальте от тихой пристани. Почувствуйте попутный ветер в вашем парусе. Двигайтесь вперед, действуйте, открывайте!
Марк Твен</item>
        <item>Начинать всегда стоит с того, что сеет сомнения.
Борис Стругацкий</item>
        <item>Настоящая ответственность бывает только личной.
Фазиль Искандер</item>
        <item>Неосмысленная жизнь не стоит того, чтобы жить.
Сократ</item>
        <item>80% успеха - это появиться в нужном месте в нужное время.
Вуди Аллен</item>
        <item>Ваше время ограничено, не тратьте его, живя чужой жизнью
Стив Джобс</item>
        <item>Победа - это еще не все, все - это постоянное желание побеждать.
Винс Ломбарди, тренер по американскому футболу</item>
        <item>Наука — это организованные знания, мудрость — это организованная жизнь.
Иммануил Кант</item>
        <item>В моем словаре нет слова «невозможно».
Наполеон Бонапарт</item>
        <item>ы никогда не пересечете океан, если не наберетесь мужества потерять берег из виду.
Христофор Колумб</item>
         <item> Свобода ничего не стоит, если она не включает в себя свободу ошибаться.
Махатма Ганди</item>
         <item>Либо вы управляете вашим днем, либо день управляет вами.
Джим Рон, оратор и бизнес-тренер</item>
    </string-array>



///////////////////

plugins {
    id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
}

android {
    compileSdk 32

    defaultConfig {
        applicationId "com.example.qgp"
        minSdk 21
        targetSdk 32
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = '1.8'
    }
    buildFeatures{
        viewBinding true
    }
}

dependencies {

    implementation 'androidx.core:core-ktx:1.8.0'
    implementation 'androidx.appcompat:appcompat:1.4.2'
    implementation 'com.google.android.material:material:1.6.1'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    testImplementation 'junit:junit:4.13.2'
    androidTestImplementation 'androidx.test.ext:junit:1.1.3'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.4.0'
}



/////////////////////


/**
 * Automatically generated file. DO NOT MODIFY
 */
package com.example.qgp;

public final class BuildConfig {
  public static final boolean DEBUG = Boolean.parseBoolean("true");
  public static final String APPLICATION_ID = "com.example.qgp";
  public static final String BUILD_TYPE = "debug";
  public static final int VERSION_CODE = 1;
  public static final String VERSION_NAME = "1.0";
}


//////////////




