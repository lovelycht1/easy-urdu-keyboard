# Easy Urdu Keyboard — Native Android + GitHub Actions

یہ ایک Native Kotlin Android project ہے۔ یہ React/WebView wrapper نہیں ہے۔ اس میں Android `InputMethodService` موجود ہے، لہٰذا install ہونے کے بعد اسے Android کے keyboard settings میں enable اور select کیا جا سکتا ہے۔

## GitHub سے APK بنائیں (PC پر Android Studio ضروری نہیں)

1. ZIP extract کریں۔
2. GitHub پر نیا repository بنائیں، مثلاً `easy-urdu-keyboard`۔
3. Extract کیے گئے project کے اندر کی تمام فائلیں repository کی root میں upload کریں۔ `.github/workflows/build-apk.yml` بھی ضرور upload ہو۔
4. GitHub repository میں **Actions** tab کھولیں۔
5. پہلی بار workflow run کی اجازت مانگی جائے تو **I understand my workflows, go ahead and enable them** منتخب کریں۔
6. **Build Easy Urdu Keyboard APK** workflow کھولیں اور **Run workflow** دبائیں۔ Push پر بھی خودکار build ہو گی۔
7. Build مکمل ہونے پر run کھولیں، نیچے **Artifacts** میں `EasyUrduKeyboard-debug-apk` download کریں۔
8. ZIP artifact extract کریں۔ اس کے اندر `EasyUrduKeyboard-debug.apk` ہوگا۔ اسے Android فون میں منتقل کرکے install کریں۔

## Android پر Keyboard فعال کرنا

1. Easy Urdu Keyboard app کھولیں۔
2. **Enable Easy Urdu Keyboard** دبائیں۔
3. Android کی On-screen keyboard / Manage keyboards settings میں Easy Urdu Keyboard کو ON کریں۔
4. واپس آکر **Select Easy Urdu Keyboard** دبائیں اور فہرست سے اسے منتخب کریں۔
5. WhatsApp یا کسی بھی text field میں ٹائپ کریں۔

## اس ورژن میں کیا شامل ہے؟

- Native Android InputMethodService
- Urdu character keyboard layout
- English QWERTY layout
- Basic Roman-to-Urdu phonetic conversion and word candidates
- Urdu Editor with Copy, Share and Clear
- No INTERNET permission; no keystroke collection or network upload

## اہم حدود

- Phonetic conversion ایک چھوٹی offline dictionary اور character mapping پر مبنی ہے؛ یہ مکمل AI transliteration یا مکمل لغت نہیں۔
- Keyboard layouts بنیادی starter layouts ہیں۔ مختلف فونز، text fields، secure fields اور Android versions پر الگ الگ test کریں۔
- یہ **debug APK** بناتا ہے، Play Store release کے لیے الگ signed release build اور privacy policy درکار ہوگی۔
- GitHub Actions build مکمل ہونے سے پہلے APK موجود نہیں ہوتی؛ workflow کا green/successful ہونا ضروری ہے۔

## Build configuration

- Package: `com.easyurdu.keyboard`
- Min SDK: 23 (Android 6.0)
- Target / Compile SDK: 35
- JDK: 17
- Gradle: 8.9
- Android Gradle Plugin: 8.7.3
- Kotlin: 2.0.21
