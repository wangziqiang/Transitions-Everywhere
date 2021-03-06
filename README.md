Transitions Everywhere
============
Backport of [Transitions API from Android KitKat and Lollipop][1]. Compatible with <b>Android 2.2+</b>.

About Transitions API
============
[Video - DevBytes: Android 4.4 Transitions][2]<br>
[Sample project from Google][3]<br>
[Article about transitions and library (in Russian language)][6]

Changelog
============
<b>1.4.0</b> - Merge with Android M Preview sources<br>
<b>1.3.1 - 1.3.2</b> - Bug fix<br>
<b>1.3.0</b> - Merge with changes from Android 5.1<br>
<b>1.2.0 - 1.2.2</b> - Bug fix<br>
<b>1.1.0</b> - Port of new transitions from <b>Android 5.0 Lollipop</b>

Simple example
============
<img src="http://habrastorage.org/getpro/habr/post_images/e93/37c/0da/e9337c0dacc355523adddf1545b57e5a.gif"/>

Usage
============
Gradle:
```
dependencies {
    compile "com.github.andkulikov:transitions-everywhere:1.4.0"
}
```
Use transition classes from package `android.transitions.everywhere.*` instead of `android.transition.*` from android framework Transitions API.<br>

Transitions via XML
============
If you use XML files to create your transitions you need to put them in the res/anim folder instead of the res/transition folder. You need to use application attributes namespase instead of `android:`. For example:
```
<transitionSet xmlns:app="http://schemas.android.com/apk/res-auto"
               app:duration="400">
    <changeBounds/>
    <fade app:fadingMode="fade_in">
        <targets>
            <target app:targetId="@id/transition_title"/>
        </targets>
    </fade>
</transitionSet>
```

Transition names of views
============
Android 5.0 adds new method `setTransitionName()` for `View` class. With this library you should call `TransitionManager.setTransitionName(View v, String transitionName)` method instead to provide backward compatibility.

ProGuard configs
============
```
-keep class android.transitions.everywhere.** { *; }
-keep class android.transitions.everywhere.**.** { *; }
```

About library
============
Transition animations backported to <b>Android 3.1</b>.<br>
For Android ver. <b>>= 2.2</b> and < <b>3.0</b> scene to scene (layout to layout) changes is executed by the same API  but without animations.

<b>Note:</b> some of transitions classes was marked as hidden by developers of Android. You can find it in package  `android.transitions.everywhere.hidden`.

Thanks to github users: <b>[pardom][4]</b> and <b>[guerwan][5]</b>  

[1]: http://developer.android.com/reference/android/transition/package-summary.html
[2]: https://www.youtube.com/watch?v=S3H7nJ4QaD8
[3]: https://developer.android.com/samples/BasicTransition/index.html
[4]: https://github.com/pardom/TransitionSupportLibrary
[5]: https://github.com/guerwan/TransitionsBackport
[6]: http://habrahabr.ru/post/243363/

<br>
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-transitions--everywhere-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1050)
