# Custom Firmware for Ploopy Trackball

Ploopy Trackball をカスタマイズするための独自ファームウェアです。
本リポジトリのソースコードを使用することを前提としています。

---

## ファームウェアのビルド方法

### 1. QMK のセットアップ

QMK のビルド環境をセットアップします。

`qmk setup

### 2. 本リポジトリの取得

GitHub からクローンするか、ZIP をダウンロードして展開してください。

### 3. post_rules.mk について

本ファームウェアでは Ploopy Trackball 用のカスタム `post_rules.mk` を使用します。  
QMK 本体に含まれるものとは内容が異なるため、本リポジトリの `post_rules.mk` をQMK 本体側に上書きしてください。

---

## ビルド

`qmk compile -kb ploopyco/trackball -km nyanz-lab

---

## 書き込み方法

### ブートローダーモードへの入り方

左下ボタンを押しながら USB ケーブルを接続すると、デバイスがブートローダーモードで起動します。  
PC に UF2 ドライブとして認識されます。

### QMK CLI を使用する場合

`qmk flash -kb ploopyco/trackball -km nyanz-lab

### ドラッグ＆ドロップで書き込む場合

生成された `.uf2` ファイルを、表示された UF2 ドライブにドラッグ＆ドロップしてください。

---

## 注意事項

※ 古いPloopy 公式ファームウェアを使用すると、ブートローダーモードに入れなくなる場合があります。 

