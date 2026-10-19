# تنگه هرمز — پروژه اندروید

این پروژه شامل نسخه فعلی بازی و گردش‌کار خودکار برای ساخت فایل APK آزمایشی است.

## ساخت APK به‌صورت خودکار (بدون نصب Android Studio روی رایانه شخصی)

1. وارد GitHub شوید و یک مخزن جدید بسازید.
2. فایل‌های داخل این پوشه را در مخزن بارگذاری کنید (همراه پوشه مخفی `.github`).
3. اگر مخزن روی شاخه `main` باشد، از بخش **Actions** می‌توانید اجرای `Build Android APK` را انتخاب کنید. با هر بار Push به `main` هم ساخت اجرا می‌شود.
4. پس از موفقیت، اجرای workflow را باز کنید و از بخش **Artifacts** فایل `Strait-of-Hormuz-debug-APK` را دانلود کنید.
5. فایل ZIP دانلودشده را باز کنید؛ داخل آن `app-debug.apk` قرار دارد. آن را به گوشی اندروید منتقل و نصب کنید. ممکن است لازم باشد اجازه نصب از همان منبع را در تنظیمات گوشی فعال کنید.

## ساخت محلی

نیاز است Node.js، JDK 21 و Android Studio/Android SDK نصب باشند:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

خروجی: `android/app/build/outputs/apk/debug/app-debug.apk`

## مهم

- شناسه بسته فعلی: `com.codabtin.straitofhormuz`
- خروجی این گردش‌کار **debug APK** برای نصب و آزمایش است؛ هنوز APK انتشار نهاییِ امضاشده نیست.
- برای انتشار در Google Play یا توزیع رسمی، باید کلید امضای release، اطلاعات فروشگاه، آیکن نهایی و آزمایش روی دستگاه واقعی تکمیل شود.
- این گردش‌کار برای ساخت APK به حساب GitHub و دسترسی به GitHub Actions نیاز دارد.
