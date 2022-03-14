# WWDC21

## 概要

WWDC21（06/07 - 06/11）の発表について紹介します。

- https://developer.apple.com/wwdc21/

## iOS & iPadOS 15

- https://developer.apple.com/documentation/ios-ipados-release-notes/ios-ipados-15-beta-release-notes

### 共通

- ソフトウェアアップデートで、iOS（iPad OS） 14のまま重要なセキュリティアップデートのみ行うことができる

#### 集中モード

- __通知が自動的にフィルタリングされる__
- __集中時に通知を許可するか設定できる__

#### 通知

- https://developer.apple.com/videos/play/wwdc2021/10091
- デザインが一新される
  - 今までよりアイコンが大きく表示される
- 通知の要約が1日に1回届く
- __通知を一時的に非表示にできる__
- 中断レベルが2つ増えて4つになった
  - https://developer.apple.com/documentation/usernotifications/unnotificationinterruptionlevel
  - Passive
    - 静かに通知される
    - Androidのサイレント通知と同じイメージだと思う
  - Time Sensitive
    - すぐに注意を払う必要がある通知
  - 明示的に指定しないと __今より通知がユーザーに見られなくなる__

#### アクセシビリティ

- 画面表示とテキストサイズの設定を __アプリごとにカスタマイズできるようになる__
- __VoiceOverで画像内の人物やオブジェクトが詳しく読み上げられるようになる__

### iOS 15のみ

- https://www.apple.com/jp/ios/ios-15-preview/
- https://www.apple.com/jp/ios/ios-15-preview/features/
- アプリ間でドラッグ&ドロップできるようになる

### iPadOS 15のみ

- https://www.apple.com/jp/ipados/ipados-preview/
- https://www.apple.com/jp/ipados/ipados-preview/features/
- iOS 14で追加されたAppライブラリとウィジェットが、iPadOSでも使えるようになる
- Swift Playgroundsを利用すると、SwiftUIでアプリを開発して直接App Storeに提出できる
- ユニバーサルコントロール
  - 設定なしにMacとiPad間でシームレスに作業できるようになる
  - カーソルの端末間移動
  - 入力した文字の共有
- スクリブル（Apple Pencilで書いた文字をテキストに変換する機能）が日本語に対応される

## macOS Monterey

- https://developer.apple.com/documentation/macos-release-notes/macos-12-beta-release-notes
- iOSの「ショートカット」アプリが使えるようになる

## Safari

- デザインが一新される
  - タブバーが画面下部にフローティングしているため、 __画面下部にUIコンポーネントを固定しているWebサイトはデザインを見直す必要がある__
  - OS問わずデザインが変わる
    - iOSとmacOSではタブバーが画面下部にあるが、iPadOSでは画面上部のまま

## Xcode 13

- https://developer.apple.com/documentation/xcode-release-notes/xcode-13-beta-release-notes
- https://developer.apple.com/xcode/whats-new/
- https://developer.apple.com/jp/xcode/whats-new/
- [Xcode Cloud](#xcode-cloud) の追加
- GitHubのPR操作がXcodeに統合
- DocCの追加
  - ドキュメントを作成・表示する機能
- テストが繰り返し実行できるようになった
- Swiftのコード補完やシンタックスハイライトが高速かつ確実になった
- ブレークポイントを行のみでなく列にも張れるようになった
- __Vimキーバインドのサポート__

### Xcode Cloud

- https://developer.apple.com/xcode-cloud/
- __Apple公式のCI/CDサービス__
- Xcodeに統合されている
- App Store Connectにダッシュボードが追加された
- 料金は未定

## Swift 5.5

- https://github.com/apple/swift/blob/main/CHANGELOG.md#swift-55
- __async/awaitをはじめとした並行プログラミングのサポート__
  - iOS 15から使える

## Conclusion

- ハードの発表はなかった
- Xcode CloudやDocC、Swiftのasync/awaitなど、全体的にデベロッパーフレンドリーな内容が多かった

## 参考リンク

### 非公式

- https://iphone-mania.jp/news-373449/
- https://www.slideshare.net/mogmet/ios-15-notification-focusnotification-summarysend-communication
