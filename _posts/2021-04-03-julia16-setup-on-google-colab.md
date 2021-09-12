---
layout: post
excerpt: "setup-on-google-colab"
title: "[2021w][2021s]クラウド環境 Google colab 上に構築する方法（2021年）"
last_modified_at: 2021-04-03T01:29:02-05:00
permalink: /julia16-setup-on-google-colab
categories:
  - home
tags:
  - Julia
  - google colab
  - 2021s
  - 2021w
---

## 必要なもの
- インターネットへの常時接続
- Google アカウント
- 以下の条件を満たす端末
  - Web ブラウザを利用できること
  　- Google Chrome を推奨する 
  - 入力装置： コントロール (`CTRL`)キー、バックスラッシュ( `\` )キー、タブキーを確実に入力できること
  - 以上の条件から PC の利用を強く推奨する
    - フルキーボードを接続したタブレットやスマートフォンは利用可能だと邪推する
      - 私には環境を用意できないので、各自で試すこと（結果を報告してください）
    - フルキーボードを接続しないタブレットやスマートフォンの利用は全く推奨しない

## 準備
- Google アカウントを用意する
  - アカウントがないなら作成する

## 手順

### 設定ファイルを入手する
- Google のアカウントを登録する
- Google Drive を有効にする
  https://drive.google.com/
- Google Colab を有効にする
  https://colab.research.google.com/
- Googleにログインしたまま、以下の URL を閲覧する。
  > URLは、授業支援サイト kibaco を通じて連絡する
- ブラウザで新しいタブを開き、上のリンクをブラウザのURL欄に貼り付ける。以下のような画面になる

![accessNotebook](https://gyazo.com/73458ba1d6e32039679704a935753470.png)

- ページ上部の `Google Colaboratoryで開く` を選択する 
- Google Colab 上で、Notebookが開くはず

![openNotebook](https://gyazo.com/e6ce2425f4dbf8a40ce25a2f05be90e7.png)

- 「接続」ボタンが見える場合は、「接続」メニューから「ホスト型ランタイム側に接続」を選ぶ。
- 「接続済」になれば、次に進める。

![connectedRuntime](https://gyazo.com/90286dda692d57151bc3313dc17d274a.png)

- メニューから 「ファイル > _ドライブにコピーを保存_」 と進む.

### Google colab での作業

- Google Colab notebook ファイルが表示されているはず

![startGoogleColab](https://i.gyazo.com/8466049d94fbaa733518fbc23f04f56d.png)

### GPUを使わない設定にする
- メニューから「ランタイム > _ランタイムのタイプを変更_」
- 「ハードウエア アクセラレータ = _None_」 として「保存」

### この後にある「Setup = 設定」節を見つける
- 節表題の下に「1個のセルが非表示」と書いてある場合には、節表題の左側の右向き三角形「▶」をクリックする

![hidden_code_cell](https://i.gyazo.com/27efde3ae629c6d12fc484c71754b573.png)

### `%%shell` から始まるコードセルが見つかる
   
![setupCodeCell](https://i.gyazo.com/eb7337953ff4c7939f65ae409fad6235.png)


### そのコードセルを実行する
- `%%shell`  の左側の `[1]` 上にカーソルを置くと「![triangle](https://i.gyazo.com/787befb794c798a253dac970475357fb.png)」シンボル（黒丸の中に、白抜き右向き三角形）が現れる
  - そのシンボルをクリックする
- 別の方法
   - そのセルを選ぶ
  - `Ctrl` キー を押しながら `Enter` キーを打つ （以後、「`Ctrl+Enter` を押す」と記す）
- 以下のメッセージが表示された場合は、末尾の「×」を押してください（メッセージを無視する）
  ![python3](https://i.gyazo.com/a359fd093cac142d1a67e655b52250c2.png)
- 実行すると、いくつかのパッケージがインストールされる
- 実行には数分かかる

### セルの実行が終わるまで待つ
- 実行に成功すると、以下のメッセージが表示される
> `Success! Please reload this page and jump to the next section.`

### このページを再読込みする
- 用いているブラウザに応じて、`Ctrl+R`, `⌘+R`, `F5`キーのいずれかを押す
  
### 「Checking the Installation」節のコードセルから実行を始める
- コードセル内のコードを実行するには
  - `SHIFT` キー を押しながら `Enter`キーを押す（以後、「`SHIFT+Enter` を押す」と記す）
  - または、「![triangle](https://i.gyazo.com/787befb794c798a253dac970475357fb.png)」シンボルを押す
- `versioninfo()` を実行すると、Julia 言語のバージョンが表示される
- 続けて、以下の節内のコードセルを上から順番に実行する
  - Unitful のテスト
  - PyPlot のテスト
    - 以下のメッセージが表示されたら、`[ENTER]` キーを押す。（既定値 `y` を入力することに相当）
    > `install Jupyter via Conda, y/n? [y]:`

### Notebook名を変更する
- メニューから「_ファイル_ > _ノートブック名を変更_」
- ページ上部のファイル名を変更して、`[ENTER]` キーを押す
- ファイル名末尾は、半角文字の `.ipynb` で終わらせる
  - これは (Jupyter notebook の拡張子である

### 現在作業中のファイルを保存する
- メニューから「_ファイル_ > _保存_」
- プログラム作成・実行中も「保存」を操作する

### 今後の起動方法
- 今回保存した .ipynb ファイルを複製して、プログラミングを開始する

## 終わり
- [2021秋冬学期向け環境]({{ site.baseurl }}{% post_url 2021-09-01-julia162-env-2021w %}) にもどる
- [2021春夏学期向け環境]({{ site.baseurl }}{% post_url 2021-04-03-julia160-env-2021s %}) にもどる
