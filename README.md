# RNSplash
##### React Native Splash Screen


## Change Default Background Color for the all Screen


**Add this Line in** ``` android/app/src/main/res/values/colors.xml ```
```
<resources>
    ......
    <color name="app_bg">#282c34</color>
</resources>
```

**Add this Line in** ``` android/app/src/main/res/values/styles.xml ``` 
```
.....
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    .....
    <item name="android:windowBackground">@color/app_bg</item>
</style>
```

**To set the Default Status Bar Color for the all Screen, Add this Line in** ``` android/app/src/main/res/values/styles.xml ```
```
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    .....
    <item name="android:statusBarColor">@color/app_bg</item>
</style>
```

**To set the Default Status Bar Text Color, Add this Line in** ``` android/app/src/main/res/values/styles.xml ```
```
<style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    .....
    <item name="android:windowLightStatusBar">false</item>
</style>
```
```
- set **false** to light-content
- set **true** to dark-content
```



## To Change Splash Screen Background Color.

**Edit this Line in** ``` android/app/src/main/res/values/colors.xml ```
```
<resources>
    <color name="splashscreen_bg">(your color)</color>
</resources>
```

**Add this Line in** ```App.js```
```
import React, { useEffect } from 'react'; // add this.
import SplashScreen from 'react-native-splash-screen' //add this.

export public function App extends Component{
    useEffect(() => {
        SplashScreen.hide();
    }, [])
    render(){
        return(......)
    }
}
```