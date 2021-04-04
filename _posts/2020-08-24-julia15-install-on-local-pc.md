---
layout: post
excerpt: "install-on-local-PC"
title: "[2020w]手元 PC に実行環境を構築する方法（2020秋冬学期）"
permalink: /julia15-install-on-local-PC
last_modified_at: 2020-10-10T22:40:02-05:00
categories:
  - localpc
tags:
  - Julia
  - installation
---

## 必要なもの
* ハードウエアの要件
  * 空きHDD容量5GB以上が望ましい
  * メインメモリ8GB以上が極めて望ましい
  * インターネットへ常時接続されていること．(接続された状態で作業する)
* OSの要件
  * Windows 7以上, Windows10 64bitを推奨, … または
  * MacOSX 10.8以上, 10.13以上を推奨, … または
  * Linux など
* 用いるユーザアカウントの要件
  * 管理者アカウント
    * アプリケーションをインストール可能な権限を持つこと
  * そのアカウント名が「半角英数字」のみで構成されること
    * 「半角文字」とは、「かな漢字変換」システムを用いずに入力できる文字とみなしてください
    * すなわち，空白，記号，漢字, かな, ハングルなどを含んではいけない
    * そのようなアカウントを用意していなければ，新たにアカウントを作成し，今後そのアカウントで作業せよ
* 既定のWeb ブラウザとして、現代的な Web ブラウザが設定されていること
  * 既定の（デフォルト default） ＝ 「指定しない場合に、選ばれる」という意味
  * お勧めする Webブラウザ： Google Chrome, Mozilla Firefox, Safari（MacOSXのみ）
  * お勧めしない Webブラウザ： Microsoft Internet Explorer
  * (参考) Windows10 → [Windows 10 で既定のブラウザーを変更する](https://support.microsoft.com/ja-jp/help/4028606/windows-10-change-your-default-browser)
  * (参考) MacOSX → [MacでSafariをデフォルトWebブラウザに設定する](https://support.apple.com/ja-jp/guide/safari/ibrwa008/mac)
* 他のソフトウエアとの競合
  * 以下の説明は、Julia と競合するソフトウエアがインストールされていないことを前提とする
    * 特に、下記で説明する PyPlot パッケージは、インストール済の Python言語の処理系と競合する可能性がある

### セキュリティ対策ソフトとの競合
* Julia が用いるパッケージの設置を妨害するセキュリティ対策ソフトがあります
  * カスペルスキーが、以下の PyPlot パッケージの設置を妨害することが報告されました
* セキュリティ対策ソフトの機能を一時的に停止してみてください
 
## Julia のダウンロード
* Julia 言語のダウンロードのページを閲覧する。 https://julialang.org/downloads/
* `Current stable release` の節に進む
  * 2020年9月23日時点の最新版は version 1.5.2 である。（以下は v1.5.1当時） 

![JuliaBinary](https://i.gyazo.com/61b3931cb920349d6dbd0ad81686dece.png)

* 該当するバイナリファイルをダウンロードする
  * Windows 64bit なら `64bit installer`
  * Windows 32bit なら `32bit installer`
    * Windows のバージョンの調べ方 → [使用中の Windows オペレーティング システムのバージョンを確認する](https://www.microsoft.com/ja-jp/safety/protect/ver_win.aspx)
  * MacOS なら `64bit`   
* バイナリファイルの大きさは 50MB 以上ある。数～数十分かかる場合がある

* バイナリのインストール
  * Windows の場合 [Julia のインストール Windows 向け](#julia-のインストール-windows-向け) に進む
  * MacOSX の場合 [Julia のインストール MacOS 向け](#julia-のインストール-macos-向け) に進む
  * 他のOSの場合は説明を省略

* [パッケージのインストール：準備0](パッケージのインストール：準備０)に進む

## Julia のインストール Windows 向け
* ダウンロードした `exe` ファイルをダブルクリックする
* Install ボタンを押して，作業を進める
  * インストール先ディレクトリは、そのままでよい

![win-julia-install1](https://i.gyazo.com/1b23318228488a7f3e13d2b298169add.png)

  * Installation Successfull の窓が出たら、何も選ばす `Finish` ボタンを押してよい 

![win-julia-install2](https://i.gyazo.com/28a35e18b656ff60ac3d7fe1d4a62b2f.png)

* デスクトップにできたアイコン ![win-julia-icon](https://i.gyazo.com/fe66887c8b205766060bf5cd7fb59380.png) をクリックして起動できたらOK
  * 起動できない場合は、OS やウイルス対策ソフトが、ダウンロードしたアプリケーションのインストールや起動を阻止していないか確認してください。信用できる作業を行っているなら、阻止を解除してください
* [パッケージのインストール：準備０](#パッケージのインストール：準備０) に進む


## Julia のインストール MacOS 向け
* ダウンロードした `dmg` ファイルをダブルクリック
*  解凍できたら，以下の画面になる

![mac-julia-install](https://i.gyazo.com/21336bbf9d53c8f8d0dc1e1e04ff5557.png)

* `Julia-1.5.app` を `Applications` フォルダにドラッグする
* `Application` フォルダーの Julia アイコン ![mac-julia](https://i.gyazo.com/7904a9ed7f518051d99728cb59686098.png) をクリックして起動できたらOK
  * 起動できない場合は、OS やウイルス対策ソフトが、ダウンロードしたアプリケーションのインストールや起動を阻止していないか確認してください。信用できる作業を行っているなら、阻止を解除してください
  * MacOS が Julia の起動を阻止している場合：「システム環境設定」> 「セキュリティとプライバシー」> [一般]。「ダウンロードしたアプリケーションの実行許可：」が灰色になっていたら、ロック解除して、「App Store と確認済みの開発元からのアプリケーションを許可」を選択
* [パッケージのインストール：準備０](#パッケージのインストール準備０) に進む

## パッケージのインストール：準備０
* ファイル・エクスプローラ(Windows) またはFinder(Mac)を起動する
* 自分のホームディレクトリ（フォルダー）に移動する.
  * アカウントが `hs` なら，ホームディレクトリは，
    * Windows なら `c:¥users¥hs`
      * 円マーク `¥` の代わりに、バックスラッシュ `\` で表示される場合がある 
    * MacOSX なら `/Users/hs`
* ホームディレクトリに `.julia` という名前のディレクトリ（フォルダー） があれば，それを削除する

## パッケージのインストール：準備１
![CONDA_JL_VERSION](https://i.gyazo.com/0abc14ceb0433b9957c22aeb1a3fc3a1.png)

* Julia を起動する
* プロンプト `julia>` は，命令を待ち受ける状態である（コマンド・モード）
* `1+1` を打ち込んだ後 `ENTER`キー を押す。計算結果 `2` が表示される。
  * 以後 `[ENTER]` は「 `ENTER` キーを押すこと」を意味する
* 次の文を打ち込む。全て半角文字である。大文字・小文字は区別される
  > ENV[“CONDA_JL_VERSION”]=3 [ENTER]

* 次の文を打ち込む。全て半角文字である。大文字・小文字は区別される
  > ENV[“MPL_BACKEND”]=“TkAgg” [ENTER]


## パッケージのインストール：Unitful

![Uniftul](https://i.gyazo.com/8e458c4f3a0d672befdf22311752a126.png)

* `]` キーを押すと，プロンプトが `pkg>` に変わる（パッケージ・モードに入る）
* 次の文を打ち込む。
  > add Unitful [ENTER]

* 新しくパッケージを入れる場合には、たくさんのメッセージが出る。赤字のテキストはエラーメッセージである。
  * 比較的親切なメッセージが表示される
    * 以下のメッセージは、パッケージが見つからないことを意味する。`add` の後に正しいパッケージ名をタイプする。
      > ERROR: The following package names could not be resolved:
    * 以下のメッセージは、インターネット接続が切断された可能性を示唆する
      > Warning: Some registries failed to update
    * パッケージ一覧の更新中は、パッケージの追加が失敗する。この場合は、5分程度経過してから、再び試す。

* `pkg>` プロンプトが出るまで待つ。
* コントロール `CTRL` キーを押しながら `c` を押す（パッケージ・モードから抜ける）
  * 以後 `[CTRL]+c` は「コントロールキーを押しながら `c` を押すこと」を意味する
* `julia>` プロンプトが出ているはず（現在コマンド・モードである）
* 次の文を打ち込む。エラーメッセージが出ないことを確認する。
  > using Unitful [ENTER]
  * 比較的親切なメッセージが表示される
    * 以下のメッセージは、上の `add Unitful` が失敗したことを意味する。
      > Run `import Pkg; Pkg.add("Unitful")` to install the Unitful package.
    * 上の指示に従い `import Pkg; Pkg.add("Unitful")` と打ち込んでみる

* さらに，次のように打ち込む
  > 1u”m” [ENTER]

* 計算結果 `1 m` または `1 u"m"` が返ればOK


### パッケージのインストール：PyPlot

![PyPlot](https://i.gyazo.com/8730cac281c67aebb81c12f77f1b0591.png)

* `]` キーを押して、パッケージモードに入る。プロンプトが `pkg>` に変わる
* 次の文を打ち込む。
  > add PyPlot [ENTER]

  * 新しく `PyPlot` パッケージを導入する場合には10分以上かかる場合がある
* `pkg>` プロンプトが出るまで待つ。
* `[CTRL]+c` を押して、パッケージ・モードを抜ける。プロンプトは `julia>` に戻る
* 次の文を打ち込む。エラーメッセージが出ないことを確認する。
  > using PyPlot [ENTER]

  * 新しく `PyPlot` パッケージを起動する場合には10分以上かかる場合がある
* `julia>` プロンプトが出るまで待つ。
  * 始めて実行する場合には数分かかる
  * エラーメッセージ（英語）が出たら、指示に従う
    * 例えば `Please run Pkg.build("PyCall")` というメッセージが出たら、
      > Pkg.build(“PyCall”) [ENTER]

* `julia>` プロンプトに対して、次のように打つ
  > plot([1,3,2]) [ENTER]


* グラフが表示されたらOK

![PyPlot_plot](https://i.gyazo.com/1f736220e223d4cd865e8d5272780607.png)


## パッケージのインストール：IJulia = Jupyter notebook (1)
*  `]` キーを押してパッケージモードへ.プロンプトは `pkg>`
* `add IJulia [ENTER]` と打ち込む.
  * 新しく `IJulia` パッケージを入れる場合には10分以上かかる場合がある
  * 途中で、以下のメッセージが出たら、`ENTER` キーを押して進める
    > install Jupyter via Conda , y/n? [y]:
* `[CTRL]+c` を押してコマンドモードへ.プロンプトは `julia>`
* `using IJulia [ENTER]` と打つ
  * 新しく `IJulia` パッケージを起動する場合には10分以上かかる場合がある
  * 途中で、以下のメッセージが出たら、`ENTER` キーを押して進める
    > install Jupyter via Conda , y/n? [y]:
* プロンプト `julia>` が出たら `notebook() [ENTER]` と打つ
* ブラウザが立ち上がるはず（次の節へ）
  * ブラウザが立ち上がらない場合は
    * 既定のブラウザが設定されていることを確認する（本ページ冒頭の「必要なもの」 > 「既定のWebブラウザ」を参照）
    * セキュリティ設定やウイルス対策ソフトがブラウザの起動を阻止してないか確認する

![start-ijulia](https://i.gyazo.com/ee9d12ec3106a1030855556ed4e9a6cc.png)

## パッケージのインストール：IJulia = Jupyter notebook (2)
* ブラウザに `Jupyter notebook` の起動画面が表示される
* 画面右側の `New` ボタンを押す．
* `Julia 1.5` を選んで起動する

  ![start-jupyter](https://i.gyazo.com/52f0347c3650a43ce4bffc46a22a7edd.png)

## パッケージのインストール：IJulia = Jupyter notebook (3)
* 起動した `Notebook` 上で作業する

![jupyter-session1](https://i.gyazo.com/3b2114b0b2b229c89af77abd7f32c147.png)

* セル内で命令を書く
  * `1+1` と打って、`[SHIFT]` キーを押しながら`[ENTER]` キーを打つと実行される。
    * 以後 `[SHIFT]+[ENTER]` は、「`[SHIFT]` キーを押しながら`[ENTER]` キーを打つ」を意味する

![jupyter-session2](https://i.gyazo.com/5329692e77c6bf2938b9f6432e4e4e97.png)

* セル内に、次のように打つ
  > using PyPlot [SHIFT]+[ENTER]
  * エラーメッセージ（英語）が出たら、指示に従う
    * 例えば `Please run Pkg.build("PyCall")` というメッセージが出たら
      > import Pkg; Pkg.build(“PyCall”) [SHIFT]+[ENTER]

* セル内で、次のように打つ
  > plot([1,3,2]) [SHIFT]+[ENTER]

* ブラウザ内にグラフが描かれれば ok

![jupyter-session3](https://i.gyazo.com/7b579d4c690a4e14f765fa50791ca19b.png)

* Jupyter notebook を終了するには
  * 右上の `Logout` ボタンを押す

![jupyter-session3](https://i.gyazo.com/e72ef36b76223dc446bcadf7247c7e53.png)

* 以上で構築作業は終了

## 授業開始時の操作
* プログラミング開始時に Jupyter notebook を起動する
  * Julia を起動
  * `julia>` プロンプトに対して、以下のように順に打ち込む
    > using IJulia [ENTER]

    > notebook() [ENTER]

  ![start-notebook](https://i.gyazo.com/24f0e06bd778bef9380c4bfe44654633.png)

  * Jupyter notebook のホーム画面が表示される

  ![start-jupyter](https://i.gyazo.com/52f0347c3650a43ce4bffc46a22a7edd.png)

* 新しい notebook を作成する
  * 画面右側の `New` ボタンを押す．
  * `Julia 1.5` を選ぶ

    ![start-jupyter](https://i.gyazo.com/e72ef36b76223dc446bcadf7247c7e53.png)

* コードセルにプログラム片を入力し、`[SHIFT]+[ENTER]` キーを押すと実行される

* たまに `[File]` メニューから `[Save and CheckPoint]` を選ぶ(保存)
  * ホームディレクトリの下に、拡張子 `.ipynb` のファイルが保存される
 
  ![jupyter-session3](https://i.gyazo.com/924c5f1296f296a7dd2c09b1bc4d69b0.png)

* Notebook名を変更する
  * Notebook を作成した直後の名前は `Untitled`+数字 である
  * ページ上部のNotebook名をクリックすると、新しい名前を入れるテキストボックスが表示される
    * 新しい名前を入れて `Rename` ボタンを押すと変更される    
  ![rename-notebook](https://i.gyazo.com/cbe35bb76b4cedb4ce3024b489d3ecde.png)

* Notebook ファイルをローカルPCに保存する
  * `[File]` メニューから `[Download As]` 
  * そのサブメニューから `[Notebook (.ipynb)]`

* notebook の編集を終える
  * `[File]` メニューから `[Download As]` 
  * そのサブメニューから `[Notebook (.ipynb)]`

* Jupyter notebook を終了するには
  * 右上の `Logout` ボタンを押す

## 終わり
- [2020秋冬学期向け環境]({{ site.baseurl }}{% post_url 2020-08-24-env-2020w-julia15 %}) にもどる
