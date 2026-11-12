# NEXUS Android APK — Hindi setup guide

Yeh Android Studio project hai. Is package mein abhi compiled APK nahi hai. GitHub Actions cloud build se APK banayega.

## 1) Online daily lessons kaise update honge

- `content/daily.json` mein daily quote, word, fact, English phrase aur personality activity edit karein.
- `content/daily.json` ko isi public `NEXUS-Android` GitHub repository mein rakhein.
- `app/src/main/assets/www/index.html` mein `NEXUS_DAILY_FEED` URL mein `YOUR-USERNAME` ko apne GitHub username se replace karein:
  `https://raw.githubusercontent.com/YOUR-USERNAME/NEXUS-Android/main/content/daily.json`
- App internet se latest JSON laayega; agar internet/feed unavailable ho, built-in lesson dikhayega.

## 2) APK phone se banane ka tarika

1. GitHub par login karein aur **New repository** banayein, naam `NEXUS-Android` rakhein.
2. Is ZIP ko phone mein extract karein.
3. Extracted folder ke andar ki saari files/folders GitHub repository mein upload karein. `.github/workflows/build-apk.yml` bhi upload hona chahiye.
4. GitHub repository mein **Actions** tab kholein. `Build NEXUS Android APK` workflow select karke **Run workflow** dabayein.
5. Build complete hone ke baad workflow run ke neeche **Artifacts** mein `NEXUS-debug-apk` milega. Use download karke ZIP extract karein; `app-debug.apk` install karein.
6. Android agar permission maange, browser/file manager ke liye “Install unknown apps” allow karein. APK sirf apne trusted GitHub repository ke build se install karein.

## 3) Daily content ko update karna

`content/daily.json` ko isi repository mein edit karke commit/push karein. Agli baar app khulega to latest content fetch karega. App APK dobara banane ki zaroorat nahi, jab tak app ka code/design change na ho.

## App details
- App name: NEXUS
- Package ID: `com.nexus.learning`
- Minimum Android: Android 6.0 (API 23)
- Online access: Internet permission enabled
- Notes/progress: device par locally save hote hain; app data clear/uninstall karne par mit sakte hain.

**Important:** APK ko publicly distribute karne se pehle signed release build, privacy policy, content moderation aur testing complete karein. Is project ka current workflow debug APK banata hai, Play Store release nahi.
