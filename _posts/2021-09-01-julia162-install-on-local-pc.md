---
layout: post
excerpt: "install-on-local-PC"
title: "[2021w]手元 PC に実行環境を構築する方法（2021秋冬学期）"
permalink: /julia162-install-on-local-PC
last_modified_at: 2021-09-17T22:40:02-05:00
categories:
  - top
tags:
  - Julia
  - installation
  - 2021w
---

* 
{:toc}

## 0. 必要なもの
* ハードウエアの要件
  * 空きHDD容量5GB以上が望ましい
  * メインメモリ8GB以上が極めて望ましい
  * インターネットへ常時接続されていること．(接続された状態で作業する)
* OSの要件
  * Windows 7以上, Windows10 64bitを推奨, … または
  * MacOSX 10.8以上, 10.13以上を推奨, … または
  * Linux など
* CPUの要件
  * Intelプロセッサ (AMD Ryzenプロセッサを含む)、または  
  * ARMプロセッサ（Apple M1 Silicon Processor や Microsoft Surface Pro X) -- 筆者には、これらの経験がなく確実な手順を記載できません
* 用いるユーザアカウントの要件
  * 管理者アカウント
    * アプリケーションをインストール可能な権限を持つこと
  * そのアカウント名が「半角英数字」のみで構成されること
    * 「半角文字」とは、「かな漢字変換」システムを用いずに入力できる文字とみなしてください
    * すなわち，空白，記号，漢字, かな, ハングルなどを含んではいけない
  * 上の要件を満たすアカウントを用意していなければ，新たにアカウントを作成し，今後そのアカウントで作業せよ
* 既定のWeb ブラウザとして、現代的な Web ブラウザが設定されていること
  * 既定の（デフォルト default） ＝ 「指定しない場合に、選ばれる」という意味
  * お勧めする Webブラウザ： Google Chrome, Mozilla Firefox, Safari（MacOSXのみ）
  * お勧めしない Webブラウザ： Microsoft Internet Explorer
  * (参考) Windows10 → [Windows 10 で既定のブラウザーを変更する](https://support.microsoft.com/ja-jp/help/4028606/windows-10-change-your-default-browser)
  * (参考) MacOSX → [MacでSafariをデフォルトWebブラウザに設定する](https://support.apple.com/ja-jp/guide/safari/ibrwa008/mac)
* 他のソフトウエアとの競合
  * 以下の説明は、Julia と競合するソフトウエアがインストールされていないことを前提とする
    * 特に、下記で説明する PyPlot パッケージは、インストール済の Python言語の処理系と競合する可能性がある

### 注意：セキュリティ対策ソフトとの競合
* セキュリティ対策ソフトの中には、Julia が用いるパッケージの設置を妨害するものがあります
  * Kaspersky Internet Securityは、以下の PyPlot パッケージの設置を妨害することが受講生から報告されました (2020年11月頃)
* セキュリティ対策ソフトの機能を一時的に停止してみてください
 
## 1. Julia のダウンロード
* Julia 言語のダウンロードのページを閲覧する。 https://julialang.org/downloads/
* `Current stable release` の節に進む
  * 2021年7月14日時点の最新版は version 1.6.2 である。 

![JuliaBinary](https://i.gyazo.com/18e99e609d3a446d7ea5c831a9206ed5.png)

* 該当するバイナリファイルをダウンロードする
  * Windows 64bit なら `64bit installer`
  * Windows 32bit なら `32bit installer`
    * Windows のバージョンの調べ方 → [使用中の Windows オペレーティング システムのバージョンを確認する](https://www.microsoft.com/ja-jp/safety/protect/ver_win.aspx)
  * MacOS なら `64bit`   
* バイナリファイルの大きさは 50MB 以上ある。数～数十分かかる場合がある

* バイナリのインストール
  * Intel CPU機、Windows の場合 [2a. Julia のインストール Intel CPU機の Windows 向け](#2a-julia-のインストール-intel-cpu機の-windows-向け) に進む
  * Intel CPU機、MacOSX の場合 [2b. Julia のインストール Intel CPU機の MacOS 向け](#2b-julia-のインストール-intel-cpu機の-macos-向け) に進む
  * ARM CPU機の場合 [2c. Julia のインストール ARM機向け](#2c-julia-のインストール-arm機向け) に進む
  * その他のOSの場合は説明を省略

## 2a. Julia のインストール Intel CPU機の Windows 向け

* ダウンロードした `exe` ファイルをダブルクリックする
* Install ボタンを押して，作業を進める
  * インストール先ディレクトリは、変更しない（インストール場所をメモしておくとよい）
    ![win-julia-install1](https://i.gyazo.com/b848a8c4754723077e8407ce0c0a8c17.png)

  * Installation Successfull の窓が出たら、どのメニューも選ばす `Finish` ボタンを押してよい 
  ![win-julia-install2](https://i.gyazo.com/f58b9a605367180702a8ad052bb296c9.png)

* デスクトップにできたアイコン ![win-julia-icon](https://i.gyazo.com/5291fbce7ee26c538424f2dda7986633.png) をクリックして起動できたらOK
  * 起動できない場合は、OS やウイルス対策ソフトが、ダウンロードしたアプリケーションのインストールや起動を阻止していないか確認してください。
  * 信用できる作業を行っていると信じるなら、阻止を解除してください
    * Kaspersky Security が起動を阻止して、Juliaを削除(移動) する例がありました
* [3a. Juliaを起動する](#3a-juliaを起動する) に進む


## 2b. Julia のインストール Intel CPU機の MacOS 向け

* ダウンロードした `dmg` ファイルをダブルクリック
*  解凍できたら，以下の画面になる

  ![mac-julia-install](https://i.gyazo.com/c6ff5ddc6ec515aad9f518a29209137c.png)

* `Julia-1.6.app` を `Applications` フォルダにドラッグする（Julia-1.6のアイコンをマウスで選択して、Applications フォルダーに重ねる）
  * この操作を行わないで起動した Juliaでパッケージをインストールすると、次回以降に起動したJuliaでパッケージが見つからない場合がある

* `LaunchPad` または `Application` フォルダーにある Julia アイコンをクリックして起動できたらOK

    ![mac-julia](https://i.gyazo.com/9959f4f6ab43470fa2a77b2a3e5d6202.png) 

  * MacOS が Julia の起動を阻止する場合がある
    * 「開く」を選べば起動するが、警告が毎回出るのは煩わしいかもしれない

![mac-julia-blocked](https://i.gyazo.com/7465ea17f3e83609a6644218d98c60dd.png)

  * 「ダウンロードしたアプリケーションの起動を許可しない」ように設定している場合は、以下のように許可する
    * MacOSの 「システム環境設定」> 「セキュリティとプライバシー」> [一般] に飛ぶ
    * 左下の🔒「鍵マーク」を解除🔓して、「確認済みの開発元からのアプリケーションを許可」ボタンを選択する

![mac-security](https://gyazo.com/a22975c6888dee31699994a9626c6b24.png)


  * 上とは異なる理由で起動できない場合は、OS やウイルス対策ソフトが、ダウンロードしたアプリケーションのインストールや起動を阻止していないか確認してください。
    * 信用できる作業を行っていると信じるなら、阻止を解除してください
  

* ターミナルから Juliaを起動したい場合は、アプリケーション内の Juliaのシンボリックリンクを、例えば `/usr/local/bin/` に作っておくとよい。
  * ターミナルを起動して、`%`プロンプトに対して、以下の1行を打ち込む(`[ENTER]` は「 `ENTER` キーを押すこと」を意味する)。パスワードを求められる
  > `sudo ln -s /Applications/Julia-1.6.app/Contents/Resources/julia/bin/julia  /usr/local/bin/julia-16` [ENTER]

  * `/usr/local/bin/julia-16` で起動できるようになります
* [3a. Juliaを起動する](#3a-juliaを起動する) に進む

## 2c. Julia のインストール ARM機向け
(2021/9/17追記)
* 筆者には、以下の経験がなく動作保証ができません
* Apple Silicon機に Rosetta2 を入れると、Intel CPU向け実行ファイルを実行できます -> https://support.apple.com/ja-jp/HT211861
* Apple Silicon機 (MacOSX 11.4 - Big Sur以上)向けに Julia v1.7.0-rcバイナリが公開されています → [Upcoming release: v1.7.0-rc1 (September 12, 2021)](https://julialang.org/downloads/#:~:text=Upcoming%20release%3A%20v1.7.0-rc1%20(September%2012%2C%202021)), macOS ARM (M-series Processor)
* Windows 10 on ARM は、Intel向けバイナリをエミュレートします。Microsoft Storeから Julia のアプリをインストールするとよいでしょう。
* M1 Mac用のParallels というソフト上で、Linuxを実行できます。その Linux上で Generic Linux on ARM用の Juliaバイナリを使えるでしょう。
* PC経験が豊富なら、自分で Build 可能でしょう。Microsoft SQ1/SQ2 は ARM64 (AArch64)機のはずです。手順の参考 → [Arm 32bit 環境で Julia を動かす](https://qiita.com/SatoshiTerasaki/items/df62e3d3a1037271e1d7)
* [3a. Juliaを起動する](#3a-juliaを起動する) に進む

## 3a. Juliaを起動する

* ファイル・エクスプローラ(Windows) またはFinder(Mac)を起動する
* 自分のホームディレクトリ（フォルダー）に移動する.
  * アカウントが `hs` なら，ホームディレクトリは，
    * Windows なら `c:¥users¥hs`
      * 円マーク `¥` の代わりに、バックスラッシュ `\` で表示される場合がある 
    * MacOSX なら `/Users/hs`
* ホームディレクトリに `.julia` という名前のディレクトリ（フォルダー） があれば，それを削除する

## 3b. パッケージ設置の準備
![CONDA_JL_VERSION](https://i.gyazo.com/c9aeab3a149e7f7542b69a46248f6ac8.png)

* Julia を起動する
* プロンプト `julia>` は，命令を待ち受ける状態である（コマンド・モード）
* `1+1` を打ち込んだ後 `ENTER`キー を押す。計算結果 `2` が表示される。
* 次の文を打ち込む。全て半角文字である。大文字・小文字は区別される。以後 `[ENTER]` は「 `ENTER` キーを押すこと」を意味する。（下のテキストはcopy&pasteできません。キーボードから打ち込んでください。以下同様です） 
  > `ENV["CONDA_JL_VERSION"]=3` [ENTER]

* 次の文を打ち込む。全て半角文字である。大文字・小文字は区別される。
  > `ENV["MPL_BACKEND"]="TkAgg"` [ENTER]


## 3c. Unitfulパッケージのインストール

![Uniftul](https://i.gyazo.com/1e00137c491bc8de2e864378ca1ffc8a.png)

* `]` キーを押すと，プロンプトが `pkg>` に変わる（パッケージ・モードに入る）
* 次の文を打ち込む。
  > `add Unitful` [ENTER]

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
  > `using Unitful` [ENTER]
  * 比較的親切なメッセージが表示される
    * 以下のメッセージは、上の `add Unitful` が失敗したことを意味する。
      > Run `import Pkg; Pkg.add("Unitful")` to install the Unitful package.
    * 上の指示に従い `import Pkg; Pkg.add("Unitful")` と打ち込んでみる

* さらに，次のように打ち込む
  > `1u”m”` [ENTER]

* 計算結果 `1 m` または `1 u"m"` が返ればOK


## 3d. PyPlotパッケージのインストール

![PyPlot](https://i.gyazo.com/3a0e24c9b21e205a5968098304cbbc46.png)

* `]` キーを押して、パッケージモードに入る。プロンプトが `pkg>` に変わる
* 次の文を打ち込む。
  > `add PyPlot` [ENTER]

  * 新しく `PyPlot` パッケージを導入する場合には10分以上かかる場合がある
* `pkg>` プロンプトが出るまで待つ。
* `[CTRL]+c` を押して、パッケージ・モードを抜ける。プロンプトは `julia>` に戻る
* 次の文を打ち込む。エラーメッセージが出ないことを確認する。
  > `using PyPlot` [ENTER]

  * 新しく `PyPlot` パッケージを起動する場合には10分以上かかる場合がある
* `julia>` プロンプトが出るまで待つ。
  * 始めて実行する場合には数分かかる
  * エラーメッセージ（英語）が出たら、指示に従う
    * 例えば `Please run Pkg.build("PyCall")` というメッセージが出たら、
      > Pkg.build(“PyCall”) [ENTER]

* `julia>` プロンプトに対して、次のように打つ
  > `plot([1,3,2])` [ENTER]


* グラフが表示されたらOK

![PyPlot_plot](https://i.gyazo.com/1f736220e223d4cd865e8d5272780607.png)


## 4a. IJuliaパッケージのインストール
*  `]` キーを押してパッケージモードへ.プロンプトは `pkg>`
* `add IJulia [ENTER]` と打ち込む.
  * 新しく `IJulia` パッケージを入れる場合には10分以上かかる場合がある
  * 途中で、以下のメッセージが出たら、`ENTER` キーを押して進める
    > install Jupyter via Conda , y/n? [y]:
* `[CTRL]+c` を押してコマンドモードへ.プロンプトは `julia>`
* `using IJulia` [ENTER] と打つ
  * 新しく `IJulia` パッケージを起動する場合には10分以上かかる場合がある
  * 途中で、以下のメッセージが出たら、`ENTER` キーを押して進める
    > install Jupyter via Conda , y/n? [y]:
* プロンプト `julia>` が出たら `notebook()` [ENTER] と打つ

  ![start-jupyter](https://i.gyazo.com/41e553fc0309d00fd90bad417127518f.png)


* ブラウザが立ち上がるはず（次の節へ）
  * ブラウザが立ち上がらない場合は
    * 既定のブラウザが設定されていることを確認する（本ページ冒頭の「必要なもの」 > 「既定のWebブラウザ」を参照）
    * セキュリティ設定やウイルス対策ソフトがブラウザの起動を阻止してないか確認する

  ![start-jupyter](https://i.gyazo.com/5b5a315f345d3b61728b115b66b54c1b.png)

## 4b. Jupyter notebookの起動
* ブラウザに `Jupyter notebook` の起動画面が表示される
* 画面右側の `New` ボタンを押す．
* `Julia 1.6` を選んで起動する (`Julia 1.6.2` と表示される場合もあります)
  * kernelのリストに `Julia 1.6` が見つからない場合
    * Jupyter notebookを既にインストール済のPCで起こる可能性がある
    * kernel.json というファイルを適切に設定する
    * 分からない場合は相談してください

## 4c. Jupyter notebook上でのプロット確認
* 起動した `Notebook` 上で作業する

![jupyter-session1](https://i.gyazo.com/2a67362ddf8615f0f912500fae5ec149.png)

* セル内で命令を書く
  * `1+1` と打って、`[SHIFT]` キーを押しながら`[ENTER]` キーを打つと実行される。
    * 以後 `[SHIFT]+[ENTER]` は、「`[SHIFT]` キーを押しながら`[ENTER]` キーを打つ」を意味する

![jupyter-session2](https://i.gyazo.com/671e2a735b697e28bfd98f18c4df930a.png)

* セル内に、次のように打つ
  > `using PyPlot` [SHIFT]+[ENTER]
  * エラーメッセージ（英語）が出たら、指示に従う
    * 例えば `Please run Pkg.build("PyCall")` というメッセージが出たら
      > `import Pkg; Pkg.build(“PyCall”)` [SHIFT]+[ENTER]

* セル内で、次のように打つ
  > `plot([1,3,2])` [SHIFT]+[ENTER]

* ブラウザ内にグラフが描かれれば ok

![jupyter-session3](https://i.gyazo.com/b43976c757e8e45df9bb86ccb6871023.png)

* Jupyter notebook を終了するには
  * 右上の `Logout` ボタンを押す

![jupyter-session3](https://i.gyazo.com/e72ef36b76223dc446bcadf7247c7e53.png)

* 以上で構築作業は終了

## 5. 授業開始時の操作
* プログラミング開始時に Jupyter notebook を起動する
  * Julia を起動
  * `julia>` プロンプトに対して、以下のように順に打ち込む
    > `using IJulia` [ENTER]

    > `notebook()` [ENTER]

  ![start-notebook](https://i.gyazo.com/45b52e651c4dc20c811b0a6955e19442.png)

  * Jupyter notebook のホーム画面が表示される

  ![start-ijulia](https://i.gyazo.com/5b5a315f345d3b61728b115b66b54c1b.png)

* 新しい notebook を作成する
  * 画面右側の `New` ボタンを押す．
  * `Julia 1.6` を選ぶ


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
- [2021秋冬学期向け環境]({{ site.baseurl }}{% post_url 2021-09-02-julia162-env-2021w %}) にもどる
