# CardDrawer

Card Drawer is a library that provide an extra card behavior on drawer, such as, move view or scaling view's height while drawer on slide.

![Alt Text](https://raw.githubusercontent.com/RupinSahu/CardDrawer/master/CardDrawer.gif)
Android 9.0+ support

## Including In Your Project
If you are a Maven user you can easily include the library by specifying it as
a dependency:

#### Maven
1. Add the JitPack repository to your build file
 ``` xml
<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
```
2.Add the dependency

``` xml
<dependency>
  <groupId>com.github.RupinSahu</groupId>
  <artifactId>CardDrawer</artifactId>
  <version>-SNAPSHOT</version>
</dependency>
```
#### Gradle
```groovy
dependencies {
   implementation 'com.github.RupinSahu:CardDrawer:-SNAPSHOT'
}
```

if **the gradle unable to sync**, you may include this line in project level gradle,
```groovy
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

## How to use
**Creating the layout**
```xml
<?xml version="1.0" encoding="utf-8"?>
<com.rupins.drawercardbehaviour.CardDrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    android:background="@color/colorWhite"
    tools:openDrawer="start">

    <include
        layout="@layout/app_bar_default"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

    <android.support.design.widget.NavigationView
        android:id="@+id/nav_view"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="start"
        android:fitsSystemWindows="true"
        android:background="@color/colorWhite"
        app:headerLayout="@layout/nav_header_main"
        app:menu="@menu/activity_drawer" />

    <android.support.design.widget.NavigationView
        android:id="@+id/nav_view_notification"
        android:background="@color/colorPrimary"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="end"
        android:fitsSystemWindows="false">
        <include layout="@layout/content_notification"/>
    </android.support.design.widget.NavigationView>

</com.rupins.drawercardbehaviour.CardDrawerLayout>

```

**Initialize**
```java
drawer = (CardDrawerLayout) findViewById(R.id.drawer_layout);
```

**Use custom behavior**
```java
drawer.useCustomBehavior(Gravity.START); //assign custom behavior for "Left" drawer
drawer.useCustomBehavior(Gravity.END); //assign custom behavior for "Right" drawer 
```

**Customize**
```java
drawer.setViewScale(Gravity.START, 0.9f); //set height scale for main view (0f to 1f)
drawer.setViewElevation(Gravity.START, 20);//set main view elevation when drawer open (dimension)
drawer.setViewScrimColor(Gravity.START, Color.TRANSPARENT);//set drawer overlay coloe (color)
drawer.setDrawerElevation(Gravity.START, 20);//set drawer elevation (dimension)

drawer.setRadius(Gravity.START, 25);//set end container's corner radius (dimension)
```

## Contact
For any enquiries, please send an email to rupinsahu007@gmail.com. 

## Donation
If this project helps you reduce time to develop, you can give me a cup of coffee :-)

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.me/RupinSahu)


## License

    Copyright 2016-2017 Rupin Sahu

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
