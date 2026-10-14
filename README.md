# My IPTV - Android App (Xtream Codes login)

Is app mein user ko URL nahi dalna padta. Server URL app ke andar fix hai,
user sirf **username** aur **password** dalta hai.

## Features
- Login (sirf username + password), login yaad rehta hai
- Live TV, Movies, Series (category ke hisab se)
- Search box, account expiry date, Logout
- HLS (.m3u8) player, agar na chale to automatically .ts try karta hai

## Step 1: Apna server URL daalo (zaroori)
File kholo: `app/src/main/java/com/iptv/app/Config.kt`

```kotlin
const val BASE_URL = "http://example.com:8080"   // <- yahan apna IPTV URL likho
```
Aakhir mein `/` mat lagana. App ka naam badalna ho to `app/src/main/res/values/strings.xml` mein `app_name`.

## Step 2: APK banao (koi ek tarika)

### Tarika A: Android Studio (PC par)
1. Android Studio install karo (developer.android.com/studio).
2. `File > Open` se is `IPTVApp` folder ko kholo, Gradle sync hone do.
3. `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
4. APK yahan milegi: `app/build/outputs/apk/debug/app-debug.apk`
5. APK ko phone mein bhej kar install karo (Unknown sources allow karna hoga).

### Tarika B: GitHub se (PC ke baghair)
1. github.com par naya repository banao aur is folder ki saari files upload karo.
2. `Actions` tab > `Build APK` > `Run workflow`.
3. 3-5 minute baad run ke andar `app-debug-apk` download karo (zip mein APK hogi).

## Note
- Series aur Movies Xtream Codes API se aate hain. Agar tumhara provider sirf M3U link deta hai
  to alag parsing chahiye hogi.
- Release/Play Store ke liye apni signing key banani hogi.
