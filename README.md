

<img width="230" height="230" alt="aaa@2x" src="https://github.com/user-attachments/assets/0bca8a0c-6031-48fb-ac1e-25a814ff3019" />

# Scripta!
Edge-tab script launcher for Illustrator, Photoshop, and InDesign on macOS

<img width="396" height="640" alt="SS_CleanShot_27_004022" src="https://github.com/user-attachments/assets/11bacaa8-14ff-4c53-ad54-cdce35a3939f" />

Illustrator、Photoshop、そしてInDesign用のスクリプトランチャーです。
指定した画面端にタブで常駐し、Ai/Ps/IDでのみ表示します。
対応OSはSequoia（15.6）以降。Intel/AppleSilicon両対応

ダウンロードはここからzipを →[Latest](https://github.com/Yamonov/Scripta/releases/latest)

メニューバーにカラー設定プリセット名を表示する、[ACEMenu Plus](https://github.com/Yamonov/ACEMenu2) もよろしく

## ドネーションウェア

無料で使用できますが、気に入ったらこちらからご寄付お願いします（クリックでジャンプ）

[<img height="300" alt="qr_eVqcN75Gm8vX6nHfDj77O00" src="https://github.com/user-attachments/assets/a6af0494-29e4-44b1-b329-1369f3b3b134" />](https://donate.stripe.com/eVqcN75Gm8vX6nHfDj77O00)

## 機能

+ Illustrator、Photoshop、InDesignのどのアプリで使うかを選択できます
+ 画面の四辺にタブとして置けます
+ アプリ毎に以下の表示を変えられます

  + タブ位置（上下左右）
  + 辺上のタブ位置（⌘+ドラッグで移動可能）
  + UIカラーモード（ダーク/ライト）
  + タブの大きさ
  + 配置するモニタ
+ アプリ毎に複数のスクリプトフォルダを登録でき、タブで切り替えられます
+ スクリプトにキーボードショートカットを設定できます
  + キーボードショートカットはアプリ毎、またタブとして切り替えられる登録フォルダごとに設定できます
  + ファイルリストを右クリックで、ショートカットキー登録画面に移動します
  + ファイルリスト右クリックから、設定したショートカットキーを一時的にオンオフできます
+ スクリプトをお気に入り登録できます。お気に入りは先頭グループに固まります
  + ショートカットキーを設定したものはその下にグループでまとまります
  + ボタンでグループをまとめる位置を上下に切り替えられます(v 1.4.1)。下からポップアップしたとき、カーソル移動量が減って便利
+ スクリプトをインクリメンタルサーチ可能な検索欄があります
  + TABキーを押してフォーカスを外せば、前面アプリのキー入力ができるようになります
+ SCRIPTMETA対応スクリプトのアップデートを調べられます。参考：(SCRIPTMETA仕様）[https://gist.github.com/Yamonov/31698801e781a6c6fa606634d34f771e]
  + 対応スクリプトに説明文があれば、ポップアップで表示します(Ver 1.2)
  + ポップアップオンオフをボタンで切り替えられます 
+ タブへのマウスオーバーで開くモードや、開きっぱなしで手動で閉じるモードを簡単に切り替えられます
+ スクリプトの出力ログを記録し、環境設定から閲覧できます
  + ログ保存はオンオフできます
+ 日/英対応です

## 機能詳細

+ スクリプトファイルは、高速なAppleEventでアプリケーションに「打ちっぱなし」で引き渡します。osascript経由の実行もフォールバックとして用意しています
  + ログ保存モードではタイムアウト付きでアプリごとのCueで実行しますが、ログ保存オフモードと体感で変化はありません
+ サーチ欄にフォーカスが当たっていないとき、Scripta!で設定したショートカットキー以外のキーは全て前面アプリ側で問題無く受け取れます
+ 指定したアプリが前面にないときは、何もしません。起動項目に入れて常時起動しても気にならないような動作を目指しています

## 画面説明

### メインウインドウ

+ リスト中のスクリプトを右クリックで、Finderで開いたり編集したり、キーボードショートカットを登録する設定画面に移動できます
  + SCRIPTMETAタグをGUIで編集できます(v1.3)
+ ⌘+ドラッグで位置移動できます
+ ウインドウサイズを変更できます
+ ショートカットキーをoption+クリックで一時的にオンオフできます(v1.3)


<img width="1940" height="1200" alt="アセット 42" src="https://github.com/user-attachments/assets/25cc5caf-78ea-4feb-8293-bab53fee1307" />

#### SCRIPTMETA情報表示

+ メタ情報表示ボタンがオンのとき
  + 情報を持つスクリプトファイル名に少し色がつきます
  + マウスオーバーで情報をポップアップ表示します。Commandキーを押しながらマウスオーバーで即表示します
    
<img width="2204" height="2000" alt="8" src="https://github.com/user-attachments/assets/3d0a25a6-6b7e-466b-8186-49dbc943dc2b" />

SCRIPTMETA バージョン1.3に対応し、更新確認をしないローカル開発のスクリプトに、説明文やバージョン情報を埋め込み、アプリ上で表示できるようになりました。
SCRIPTMETAタグをGUIで編集できるようになりました(v 1.3)

記述方法は本ページ最下部へ

### 環境設定ウインドウ

#### 一般

+ パネルを表示するアプリを選択できます。必ずひとつは選択されていなければなりません
+ 起動項目に設定できます
+ ファイルリスト右クリックの編集メニューから、ExtendScript系とAppleScript系それぞれの追加編集アプリを設定できます
+ Sparkleを搭載し、自動アップデートや手動での確認・自動ダウンロードとインストールが可能です
+ パネルが見えなくなったときなどのために、パネル位置や全設定のリセットボタンを用意しています
  
<img width="862" height="712" alt="SS_Scripta_25_003974@2x" src="https://github.com/user-attachments/assets/5f395c67-fe31-4023-978e-ba51a3828190" />

#### 表示

+ タブのマウスオーバーで展開ウインドウを開く速度を選択できます
+ リスト中の文字サイズを小・中・大で選べます
+ リストのスクリプト名部分のベースライン位置を微調整できます（Ver 1.1.5）
+ タブやウインドウに影を付けて、視認性を高められます。見失いやすいと感じたときにオンにしてください
+ 全対象アプリの表示設定をここで設定できます。内容はパネルメニューと同じです

<img width="862" height="1193" alt="5" src="https://github.com/user-attachments/assets/6fcb4324-b8a5-42b4-9649-740202dfb499" />

#### スクリプトフォルダ

+ 各アプリごとに、スクリプトの入っているフォルダを５つまで設定できます

<img width="862" height="712" alt="SS_Scripta_25_003978@2x" src="https://github.com/user-attachments/assets/8db4237f-d203-4501-8b58-b1e860e09ac3" />

#### ショートカット

+ 各アプリのそれぞれのタブ（登録フォルダ）ごとに、ショートカットキーを設定できます
+ ショートカットキーの設定されているスクリプトは、チェックボックスで一時的にキーをオフにできます
  + ファイルリスト右クリックメニューからもオンオフできます
+ お気に入りとショートカットキーを設定用ファイル＆テキストで書き出し、別環境で読み込むことができるようになりました(v1.3)
  + フォルダパスが違っても、ある程度類推して同じスクリプトにお気に入りやショートカットを復元できます 
    
<img width="862" height="712" alt="22" src="https://github.com/user-attachments/assets/316ce8e5-63af-4a04-b46e-235e42d2b4b4" />

#### SCRIPTMETA

+ SCRIPTMETAタグ対応のスクリプトが登録フォルダ内にあれば、スクリプトのアップデートを調べられます
+ アップデートのあるスクリプトは、青い文字や↑ボタンで、配布サイトを開きます（自動アップデートは仕様上行いません）
+ SCRIPTMETAタグの更新は、登録フォルダスキャンで行ってください。Local SubsetのDiscription等を検出・更新します
+ 
<img width="862" height="1193" alt="6" src="https://github.com/user-attachments/assets/02cc1fe3-d193-40fa-ac22-4c946ef45159" />

#### スクリプト実行ログ

+ ログ記録をオンにすると、スクリプトの出力するログを記録し、閲覧できます
+ AppleEvents経由でなく、フォールバックでosascript経由になった場合は、行に<<fallback>>が付きます
+ ログファイルは100MBを上限とし、ここで表示するのは512KBまでです（軽量化のため）
  
<img width="862" height="1193" alt="7" src="https://github.com/user-attachments/assets/eb1459f8-d318-4f1f-b4ba-a7f87e9ac85b" />

#### 右クリックメニュー/SCRIPTMETA編集ウインドウ(v1.3)

+ SCRIPTMETAタグを、簡易なローカル使用向け（Local Subset）と、公開用のフルセット規格（Update Profile）両方をGUIで編集可能にしました
+ GUIでタグをスクリプトに埋め込めます。スクリプトの説明をスクリプト自体にタグで埋め込むことで、いつでもリスト内から説明を見られます
  + ローカル環境でのスクリプト配布や、開発時のメモに活用できます
  + Local Subsetで雑に埋め込んだものを、フルセット規格にいつでも昇格できます
+ フルセット規格編集画面では、スクリプト公開サイトに配置するタグを自動生成します。コピペで使用できます
+ スクリプト自体にタグを書き込むので、バックアップも世代ごとにできるようにしました。いつでも元のスクリプトに戻れます
+ GUI編集ロック用に、パスワードを設定できるようにしました（v1.3.1）SCRIPTMETA v1.4の仕様として追加しています
  + ロックのかかったスクリプトはGUI編集時にパスワードを入力しないと編集できません。もちろんテキストエディタで簡単に編集できますが、敷居は上がります。 

ローカル使用向けタグ編集画面

<img width="612" height="935" alt="s1" src="https://github.com/user-attachments/assets/4a7d4e67-9614-4bb6-b626-4df53ede9edd" />

バックアップ管理画面。スクリプト毎に編集した世代を保存します。世代を選択して書き戻せます

<img width="1012" height="935" alt="s2" src="https://github.com/user-attachments/assets/389871bc-8a50-4207-8ed8-6598f5428b64" />

フル規格（公開用）SCRIPTMETAタグ編集画面。サイトにコピペで貼り付けられるタグジェネレータを備えます

<img width="1112" height="1024" alt="s3" src="https://github.com/user-attachments/assets/25c679ac-6004-4dea-a657-7f9552de1240" />


### SCRIPTMETA記述方法

SCRIPTMETA v1.3では、仕様を更新用フル規格のUpdate Profileと、ローカル利用向けにLocal Subsetに分けています。
Local Subset規格では、以下のメタ情報をスクリプト内に埋め込み、対応アプリで表示することができます。

+ スクリプトの説明
+ バージョン
+ 対応アプリ

ExtendScriptなら、スクリプト冒頭のブロックコメント内に以下のように書きます。

```javascript

/*

SCRIPTMETA-BEGIN
Script-ID=org.iwashi.testscript-subset
Target-App=Photoshop
Version=1.5
Name=スクリプトメタ！
Description-BEGIN
■テスト用のスクリプトです。
操作方法など

Description-BEGINは2回目は無視されます。
開始後、行頭にDescription-ENDが出るまでは説明文として、改行も含めてそのまま使われます。
Description-END
SCRIPTMETA-END

*/

```

SCRIPTMETAブロックが整っていれば、ブロックコメント内に何かあっても問題ありません。

必要なタグは以下

| タグ | 必要性 | 説明 |
| --- | --- | --- |
| Script-ID | 必須 | 全世界で必ず一意になるIDを考えてください。<br>逆ドメイン記法で、例えば `com.yamadatarou.InDesignScript2202.jsx` としていくのがいいでしょう |
| Target-App | 任意 | クライアントアプリで表示されます。あったほうがやさしい |
| Version | 任意 | アプリで表示されます。<br>Update Profile規格では必須ですが、Local Subset規格ではメモ書き程度の意味しか持ちません |
| Name | 任意 | 同上。ファイル名より分かりやすくする、日本語で名前をつけるなど |
| Author | ※ 任意 | 作者名を入れてください。パスワード設定時は必須項目になります |
| Edit-Password-SHA256 | 任意 | salt+UTF-8パスワードのSHA256コードです。GUIにロックがかかり、編集にパスワードが必要になります<br>スクリプト自体の編集ができなくなるわけではありません。ただのテキストですから…<br>編集不可にしてSCRIPTMETA対応させたい場合は、難読化（jsxbin）したコードをSCRIPTMETA付きのjsxにeval()で埋め込んでください。 |
| Description | 推奨 | Description-BEGIN行とDescription-END行で囲んだ範囲が説明文として表示されます<br>これがLocal Subset規格の目的でもあります。|


詳細はこちら
[SCRIPTMETA仕様書＆アプリ作成用AI指示書](https://gist.github.com/Yamonov/31698801e781a6c6fa606634d34f771e)



