# WWDC22

## 概要

WWDC22（06/06 - 06/10）の発表内容を紹介します。

- https://developer.apple.com/wwdc22/

## iOS & iPadOS 16

- https://developer.apple.com/documentation/ios-ipados-release-notes/ios-ipados-16-release-notes

### 共通

- TBD

### iOS 16のみ

- TBD

### iPadOS 16のみ

- TBD

## macOS Ventura

- TBD

## Safari

- TBD

## Xcode 14

- https://developer.apple.com/documentation/xcode-release-notes/xcode-14-release-notes
- macOS 12.4+

### 全般

- __単一のターゲットで複数のプラットフォームに対応__ した
  - 特定のプラットフォーム向けの依存関係、コード、リソース、ビルド設定を条件付きで含められる
- iPadOS向けのDriverKitドライバーの開発に対応した
- WatchKit AppとWatchKit App Extensionターゲットを単一のWatchKit Appターゲットに組み合わせた、watchOSアプリ向けの新しいデフォルトのテンプレートが追加された
  - コード、アセット、ローカライズの管理がシンプルになった
  - 単一ターゲットのwatchOSアプリはwatchOS 7+にデプロイできる
- __ビットコードが非推奨になり、iOS・tvOS・watchOSのビルドにはデフォルトで含まれなくなった__
- ビットコードはwatchOSとtvOSアプリに不要となり、App Storeは Xcode 14からのビットコードの提出を受け入れないようになった

### アセットカタログ

- __1024x1024の画像のみでアプリアイコンを指定できるようになった__
  - ターゲットに合わせて自動的にリサイズされる

### ビルドシステム

- __ビルドログ用のアシスタントエディターが追加された__
  - ビルドパフォーマンスの問題を特定するため、並列処理に焦点を当てた
  - 縦軸が並列度のレベル、横軸が時間を表し、色付きのブロックのグリッドとしてイベントを表示する
- __Swiftターゲットの依存関係と並行してターゲットをコンパイルできるようになった__
- `EAGER_LINKING` ビルド設定が追加された
  - ビルドの並列化を向上させる
- `FUSE_BUILD_SCRIPT_PHASES` ビルド設定が追加された
  - 異なるビルドフェーズからタスクを並行して実行する
  - 入出力の依存関係が順序を強制しない場合に使う
  - run script build phasesで指定する
- 推奨する最小デプロイメントターゲットのビルド設定が追加された  
  - `RECOMMENDED_MACOSX_DEPLOYMENT_TARGET`
  - `RECOMMENDED_IPHONEOS_DEPLOYMENT_TARGET`
  - `RECOMMENDED_TVOS_DEPLOYMENT_TARGET`
  - `RECOMMENDED_WATCHOS_DEPLOYMENT_TARGET`
  - `RECOMMENDED_DRIVERKIT_DEPLOYMENT_TARGET`
- `ENABLE_USER_SCRIPT_SANDBOXING` ビルド設定が追加された
  - shell script build phasesでサンドボックス化できるようになった
  - ファイルアクセスをホワイトリスト化する
- legacy build systemが削除された
- 以下のアーキテクチャ用のデプロイメントターゲットを使ったiOSプロジェクトのビルドをサポートしなくなった
  - armv7
  - armv7s
  - i386

### デバッグ

- TBD

## SwiftUI

- https://developer.apple.com/documentation/ios-ipados-release-notes/ios-ipados-16-release-notes
- [ViewBuilder](https://developer.apple.com/documentation/SwiftUI/ViewBuilder) を受け入れる `alert` 修飾子を使い、 [Alert](https://developer.apple.com/documentation/SwiftUI/Alert) に [TextField](https://developer.apple.com/documentation/SwiftUI/TextField) を配置できるようになった
- [Label](https://developer.apple.com/documentation/SwiftUI/Label) を持つコントロールや [Section](https://developer.apple.com/documentation/SwiftUI/Section) などのビューについて、ビュービルダーコンテンツは複数のビューをタイトルやサブタイトルなどの階層的な要素として自動的に配置し、スタイルを設定するようになった
  - ラベルビューを階層的でなく水平に配置する場合、ビューを `HStack` でラップする
- `TextField` が複数行のテキストに対応した
  - [Axis.vertical](https://developer.apple.com/documentation/SwiftUI/Axis/vertical) を使うと、フォームのようにテキストが短～中程度の長さになることが想定されるコンテキストで複数行のレンダリングを行える
  - 長文のテキスト編集は、引き続き [TextEditor](https://developer.apple.com/documentation/SwiftUI/TextEditor) を使う
- ナビゲーションバーに新しいデフォルトの動作が追加された
  - タイトルが提供されない場合、インラインタイトル表示モードがデフォルトになる
  - タイトルが提供される場合、デフォルトはラージのまま
  - [navigationBarTitleDisplayMode(\_:)](https://developer.apple.com/documentation/SwiftUI/View/navigationBarTitleDisplayMode(_:)) 修飾子を使うと、デフォルトを変更できる
  - デフォルトでは、ナビゲーションバーは表示するコンテンツがある場合のみレンダリングされる
  - ナビゲーションバーにタイトル、ツールバーアイテムまたは検索コンテンツがない場合、自動的に非表示になる
  - 空のナビゲーションバーを表示するには、 [navigationBarHidden(\_:)](https://developer.apple.com/documentation/SwiftUI/View/navigationBarHidden(_:)) または新しい `.toolbar(.visible)` 修飾子を使う
- `list` がセクションフッターに対応した
- `toolbar` 修飾子が複数の階層で適用されている場合、同じ配置を持つ親のアイテムに子のアイテムが追加されるようになった
- `.windowResizability(.contentSize)` を使う場合、SwiftUIで作成されたウィンドウはそのコンテンツのサイズに基づいて、リサイズ可能でフルスクリーンなフラグを設定する
- [HorizontalEdge.leading](https://developer.apple.com/documentation/SwiftUI/HorizontalEdge/leading) と [HorizontalEdge.trailing](https://developer.apple.com/documentation/SwiftUI/HorizontalEdge/trailing) のアラインメントガイドを使い、 [List](https://developer.apple.com/documentation/SwiftUI/List) セパレータのインセットをカスタマイズできるようになった
- `list` の実装に [UITableView](https://developer.apple.com/documentation/uikit/uitableview) を使わなくなった
- SwiftUIは、ビューとビューコントローラーのrepresentableが値型であることを実行時に強制するようになった
- シンボル画像は、デフォルトで自動的に決定されたシンボルレンダリングモードを使うようになった
  - シンボル画像を常にモノクロでレンダリングする場合、 [SymbolRenderingMode](https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode) 修飾子を使う
- `list` 内のメニュースタイルを持つピッカーは、デフォルトでその `label` を表示する
  - `label` を非表示にする場合、 `Hidden()` 修飾子を使う
- `list` 内のピッカーは、デフォルトでメニュースタイルになる
- `text` と `image` ビューの変更は、デフォルトでアニメーションされるようになった
  - アニメーションを無効にする場合、 `.contentsTransition(.identity)` を使う
- リストとフォームでは、スクロールジェスチャーが開始されると、ソフトウェアキーボードを自動的に閉じる
  - 以前の動作に戻す場合、 `.scrollDismissesKeyboard(.never)` を使う

## Conclusion

TBD

## 参考リンク

### 非公式

- TBD
