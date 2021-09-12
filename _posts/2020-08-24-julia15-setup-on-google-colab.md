---
layout: post
excerpt: "setup-on-google-colab"
title: "[2020w]クラウド環境 Google colab 上に構築する方法（2020秋冬学期）"
last_modified_at: 2020-09-28T01:29:02-05:00
permalink: /julia15-setup-on-google-colab
categories:
- googlecolab
tags:
- Julia
- google colab
- 2020w
---

## 必要なもの
- インターネットへの常時接続
- Google アカウント
- 以下の条件を満たす端末
  - Web ブラウザを利用できること
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
- 以下の URL を閲覧する。 Google へのログインが必要である
  > URLは、授業支援サイト kibaco を通じて連絡する
- 貴君の google drive にコピーする
  - `Connected apps` = `Connect Google colab` というボタンが現れたら、それを押す。
    - メニューから 「ファイル > _ドライブにコピーを保存_」 と進む.

### Google colab を起動する
- 以下をブラウザで閲覧 (Google Colaboratory のトップページ)
  > https://colab.research.google.com/
- Google アカウントの入力を促されたらログインする

![selectGoogleColab](https://i.gyazo.com/6087d984b00cc7cfa74dbc8758a49127.png)

- ファイルの選択を促されるはず
  - ファイルの選択が表示されていないなら、メニューから 「ファイル」 を選ぶ.
- `Google drive` タブを選ぶと、上でコピーしたファイル（拡張子 `.ipynb` ）が見つかるはず
- そのファイルを選ぶ
- 選んだファイルが表示されるはず

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
- [2020秋冬学期向け環境]({{ site.baseurl }}{% post_url 2020-08-24-env-2020w-julia15 %}) にもどる
