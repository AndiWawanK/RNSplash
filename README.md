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

export default class App extends React.Component{
    // add this.
    useEffect(() => {
        SplashScreen.hide();
    }, [])

    ....
    render(){
        return(......)
    }
}
```

**Import { Platform & StatusBar } in Components that want to use StatusBar**
##### Example:
``` 
.....
import { Platform, StatusBar, SafeAreaView } from "react-native"
import { Header } from "native-base";

const HeaderChild = (props) => {
    return(
        <SafeAreaView>
            {Platform.OS === 'ios' && <StatusBar barStyle="light-content" />} // Like this.
            <Header style={{ height: 70, backgroundColor: "#0172BA" }} noShadow>
                {props.children}
            </Header>
        </SafeAreaView>
    );
}
......
```