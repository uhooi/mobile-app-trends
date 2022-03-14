# Google I/O 2021

## 概要

Google I/O 2021（05/18 - 05/20）の発表について紹介します。

- https://events.google.com/io/?lng=ja

## Android 12

- https://developer.android.com/about/versions/12/summary
- https://developer.android.com/about/versions/12/behavior-changes-all
- https://www.youtube.com/watch?v=D2cU_itNDAI
- 基本的にアプリがバックグラウンドで実行している間はフォアグラウンドサービスを開始できなくなった
  - https://developer.android.com/about/versions/12/foreground-services
  - フォアグラウンドサービスから `WorkManager` に移行すればいい
- __正確なアラーム許可に特別なアプリアクセスが必要になった__
  - https://developer.android.com/about/versions/12/behavior-changes-12#exact-alarm-permission
  - デバイスはバッテリー寿命など大量のリソースを消費するため、正確なアラームが絶対に必要かどうか検討すべき
- アプリがシステムダイアログを閉じられなくなった
  - https://developer.android.com/about/versions/12/behavior-changes-all#close-system-dialogs
- Bluetoothの権限の追加
  - https://developer.android.com/about/versions/12/features/bluetooth-permissions
- Webインテントの解決
  - https://developer.android.com/about/versions/12/web-intent-resolution
  - 特定のWebインテントに __未承認のドメインが含まれている場合、そのインテントをアクティビティでなくデフォルトブラウザで開く__
- __オーバースクロール効果が変わった__
  - https://developer.android.com/about/versions/12/overscroll
- 通知のカスタマイズが変わった
  - https://developer.android.com/about/versions/12/behavior-changes-12#custom-notifications
- __スプラッシュ画面が追加された__
  - https://developer.android.com/about/versions/12/features/splash-screen
- ウィジェットが改善された
  - https://developer.android.com/about/versions/12/features/widgets
- Bluetoothの接続時に位置情報の許可が不要になった

## Android Studio Preview

- https://developer.android.com/studio/preview?hl=ja
- バージョンの付け方を変えた
  - https://www.youtube.com/watch?v=WRNWzhrl6-s
  - 例: Arctic Fox (2020.3.1)
    - 2020: IntelliJのバージョンの年
    - 3: IntelliJのメジャーバージョン
    - 1: Android Studioのメジャーバージョン
    - Arctic Fox: 数字だけだとわかりづらいのでコードネームを付ける

### Arctic Fox (2020.3.1)

- https://android-developers-jp.googleblog.com/2021/07/android-studio-arctic-fox-beta.html
- 2021/07/16現在: Beta 5
- IntelliJ 2020.3の更新が含まれている
  - https://blog.jetbrains.com/idea/2020/12/intellij-idea-2020-3/
- Jetpack Composeに対する更新が多い
- __Android 12用のLintチェックが追加された__
  - スプラッシュ画面のカスタム宣言
  - 高精度の位置情報の使用に対する低精度の位置情報の利用許可
  - メディア形式
  - センサーの高サンプリングレートの許可に関するチェック
- __Apple Siliconのサポート（プレビュー版）__
- IDE内でエミュレータを開ける
  - Preferences > Tools > Emulator > Launch in a tool window
- Background Task Inspectorの追加
  - https://developer.android.com/studio/preview/features?utm_source=android-studio#workmanager-inspector
  - WorkManager 2.5.0以降で使える
  - View > Tool Windows > App Inspection
  - アプリのバックグラウンドワーカーを可視化、監視、デバッグできる
- 複数端末で並行してインストルメンテーションテストを実行できるようになった
  - https://developer.android.com/studio/preview/features#instrumentation-testing

### Bumblebee (2021.1.1)

- 2021/07/16現在: Canary 3
- Canary版なので省略

## Conclusion

- WWDC20でAndroidの機能を多く取り込んだように、iOSの機能を多く取り込んだように感じた
- Androidのデザインが一新されたのが印象的だった
