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

- `xcrun crashlog <path/to/crash>` でLLDBのクラッシュログスクリプトを呼び出せるようになった
- スレッドパフォーマンスチェッカーが追加された
  - アプリターゲットのRunスキームで有効にできる
  - アプリのデバッグ中に、Issueナビゲーターとソースエディターに実行時のパフォーマンスの問題を表示する
- `swift-healthcheck` コマンドが追加された
  - Swift式エバリュエーターが機能していないときに、Swiftコンパイラー診断へ直接アクセスできる
  - これにより、デバッガーでモジュールのインポートが失敗する原因となるプロジェクトの設定ミスを簡単に特定できる
- 起動スキームアクションの `.xcresult` バンドルを開くことができるようになった
- レポートナビゲータに新しい起動ログを表示するようになった
  - Xcodeがインストール、起動、およびデバッグするために実行するアクションが表示される

### ドキュメンテーション

- Swift-DocCがObjective-CとCAPIのドキュメントの作成に対応した
- Swift-DocCが作成するWebサイトに、ドキュメントを探索およびフィルタリングするための新しいナビゲーションサイドバーが追加された
- Swift-DocCドキュメントは、デフォルトでGitHub Pagesを含むほとんどのマネージドホスティングサービスと互換性があるようになった

### ローカライゼーション

- ローカライズのためにローカルのSwiftパッケージをエクスポートできるようになった
  - プロジェクトまたはワークスペースに含まれるすべてのプロジェクトとSwiftパッケージの単一のローカリゼーションカタログを生成する
  - `xcodebuild` コマンドに `-importLocalizations` と `-exportLocalizations` でSwiftパッケージをインポートまたはエクスポートできる

### シミュレーター

- リモート通知に対応した
  - PC: Apple siliconまたはT2 プロセッサを搭載、かつmacOS 13+
  - シミュレーター: iOS 16+

### ソースエディタ

- スクロール時にコード構造の要素をエディターの上部に固定するようになった
  - 「Show: Code structure while scrolling」で切り替えられる
- 不足しているインポートを追加する修正が提案されるようになった
- コードを `if` 文で括ると、ブロック内が自動で再インデントされるようになった
- 正規表現の構文の強調表示と編集の対応が追加された
- 正規表現リテラルを同等の正規表現ビルダーに変換できるようになった
  - 「Editor > Refactoring > Convert to Regex Builder」で変換できる

## Swift 5.7

- https://developer.apple.com/documentation/xcode-release-notes/xcode-14-release-notes
- https://github.com/apple/swift/blob/main/CHANGELOG.md#swift-57
- 標準ライブラリに `Regex<Output>` 型と正規表現リテラル、新しい文字列処理アルゴリズムが追加された
  - https://github.com/apple/swift-evolution/blob/main/proposals/0355-regex-syntax-run-time-construction.md
  - https://github.com/apple/swift-evolution/blob/main/proposals/0354-regex-literals.md
  - https://github.com/apple/swift-evolution/blob/main/proposals/0357-regex-string-processing-algorithms.md
  - https://github.com/apple/swift-evolution/blob/main/proposals/0350-regex-type-overview.md
  - 例  
    ```swift
    // Initialization from a string
    let pattern = "a[bc]+"
    let regex = try! Regex(pattern)
    
    // Regex literal
    let regex = #/a[bc]+/#
    ```
- 新しく追加された正規表現リテラルに対して「ベアスラッシュ」構文を有効にする
  - 既存のコードがコンパイルされない可能性がある
  - プロジェクトのビルド設定にある「Enable Bare Slash Regex Literals」チェック（ `SWIFT_ENABLE_BARE_SLASH_REGEX = NO` ）をOFFにして無効にすることもできる
- 多くのトップレベルの位置に書き込まれたプレースホルダータイプのタイプを推測できるようになった
  - 例
    ```swift
    func replaceMe() -> _ {
        [42]
    }
    ```
- `inout` からC言語のポインタへの変換がビルドエラーにならなくなった
  - https://github.com/apple/swift-evolution/blob/main/proposals/0324-c-lang-pointer-arg-conversion.md
  - 例
    ```swift
    // C declaration:
    // long read_long(const char *input);
    
    func test() -> Int {
        var x = 3
        return read_long(&x) // !!!: ビルドエラーにならなくなった
    }
    ```
- プロトコルタイプの値を使用してジェネリック関数を呼び出すことができるようになった
  - https://github.com/apple/swift-evolution/blob/main/proposals/0352-implicit-open-existentials.md
  - 例
    ```swift
    protocol P {
        associatedtype A
        func getA() -> A
    }
    
    func takeP<T: P>(_ value: T) { }
    
    func test(p: any P) {
        takeP(p) // !!!: ビルドエラーにならなくなった
    }
    ```
- __ジェネリック関数で引数にデフォルト値を指定できるようになった__
  - 例
    ```swift
    func compute<C: Collection>(_ values: C = [0, 1, 2]) { // !!!: ビルドエラーにならなくなった
        // ...
    }
    ```
- __連想型（ `associatedtype` ）を持つプロトコルを型として使えるようになった__
  - https://github.com/apple/swift-evolution/blob/main/proposals/0309-unlock-existential-types-for-all-protocols.md
  - 例
    ```swift
    protocol Surface {...}
    
    protocol Solid {
        associatedtype SurfaceType: Surface
        func boundary() -> SurfaceType
    }
    
    let solid: any Solid = ... // !!!: ビルドエラーにならなくなった
    
    let boundary = solid.boundary()
    ```
- __プロトコルに山カッコで関連型を書けるようになった__
  - https://github.com/apple/swift-evolution/blob/main/proposals/0346-light-weight-same-type-syntax.md
  - これにより、 `where` を使わずに制約を付けられるようになってスッキリした
  - `where` を使って実現できないことができるようになった
  - 例  
    ```swift
    protocol Graph<Vertex, Edge> { // !!!: ビルドエラーにならなくなった
        associatedtype Vertex
        associatedtype Edge
    }
    
    // Before
    func shortestPath<V, E, G>(_: G, from: V, to: V) -> [E] where G: Graph, G.Vertex == V, G.Edge == E
    extension Graph where Vertex == Int, Edge == String { ... }
    
    // After
    func shortestPath<V, E>(_: some Graph<V, E>, from: V, to: V) -> [E]
    extension Graph<Int, String> { ... }
    func build() -> some Graph<Int, String> { ... } // !!!: `where` を使って書けない
    ```
- TBD
  - https://github.com/apple/swift-evolution/blob/main/proposals/0353-constrained-existential-types.md
- __関数の引数に `some` が使えるようになった__
  - https://github.com/apple/swift-evolution/blob/main/proposals/0341-opaque-parameters.md
  - 例  
    ```swift
    // Before
    func horizontal<V1: View, V2: View>(_ v1: V1, _ v2: V2) -> some View { ... }
    
    // After
    func horizontal(_ v1: some View, _ v2: some View) -> some View { ... }
    ```
- __関数の戻り値の構造的な位置で `some` が使えるようになった__
  - https://github.com/apple/swift-evolution/blob/main/proposals/0328-structural-opaque-result-types.md
  - 例  
    ```swift
    func someDictionary() -> [some Hashable: some Codable] {
        [ 1: "One", 2: "Two" ]
    }
    ```
- TBD
  - https://github.com/apple/swift-evolution/blob/main/proposals/0326-extending-multi-statement-closure-inference.md
- __`if-let` 構文を省略して書けるようになった__
  - https://github.com/apple/swift-evolution/blob/main/proposals/0345-if-let-shorthand.md
  - 例  
    ```swift
    // Before
    if let foo = foo { ... }
    
    // After
    if let foo { ... }
    ```
- `@available(*, noasync)` 属性が追加された
  - https://github.com/apple/swift-evolution/blob/main/proposals/0340-swift-noasync.md
  - 非同期コンテキストから宣言を使えない
- トップレベルのコードが非同期呼び出しに対応した
  - https://github.com/apple/swift-evolution/blob/main/proposals/0343-top-level-concurrency.md
  - `@MainActor` で実行される
- 分散アクターの導入により、分散プログラミングをネイティブに対応した
  - https://github.com/apple/swift-evolution/blob/main/proposals/0336-distributed-actor-isolation.md
  - https://github.com/apple/swift-evolution/blob/main/proposals/0344-distributed-actor-runtime.md
  - `distributed actor` と `distributed func` を分散アクターの内部で定義できるようになった
  - 分散アクター内のストアドプロパティは外部から参照できない
  - 分散関数は潜在的なネットワーク接続を考慮し、暗黙的に `async` かつ `throws` となる
- `actor` のイニシャライザ内でストアドプロパティへの危険なアクセスをコンパイラがチェックするようになった
  - https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md
  - TBD
- 時間と時計を表す型が追加された
  - https://github.com/apple/swift-evolution/blob/main/proposals/0329-clock-instant-duration.md
  - 時計を表す `Clock` プロトコル
  - 時間のインスタンスを定義するための `InstantProtocol` プロトコル
  - 2つの `InstantProtocol` 型の間の経過時間を定義するための `DurationProtocol` プロトコル
  - 一般的に使われる `Clock` 型は `SuspendingClock` 型と `ContinuousClock` で、システムの最も基本的なクロックを表している
    - `SuspendingClock` 型はマシンが停止している間は進行しないが、 `ContinuousClock` 型はマシンの状態に関係なく進行する 

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
