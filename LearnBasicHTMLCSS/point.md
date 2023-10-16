# HTML/CSSの基礎を学ぼう
## <font color="crimson">アジェンダ</font>
- (1)進捗確認
- (2)疑問箇所の解消
- (3)テキスト内でのポイントや補足説明
- (4)次回内容の確認

## (1)進捗確認
- 1週間の作業時間の予定/実績<br>
→<br>
- 作業内容<br>
→<br>
- 所感<br>
→<br>

## (2)疑問箇所の解消
1週間学習していて気になった箇所について確認する。




## (3)テキスト内でのポイントや補足説明
- _htmlファイルにcssスタイルを外部適応する理由_<br>
基本的には外部ファイルから読み込む形をとる。理由としてアプリケーション開発の現場では各機能を役割ごとに分離させることにしている。
**可読性**と**独立性**につながる。
- リセットCSS
  ブラウザごとにデフォルトで設定されているcssのスタイルをリセットさせて予期せぬ挙動を防ぐためのもの。
  ```
  <!-- reset.css ress -->
  <link rel="stylesheet" href="https://unpkg.com/ress/dist/ress.min.css" />
  <link href="stylesheet" href="./style.css" />
  ```
 
- ビューポート
  デバイスごとの画面サイズに合わせてwebサイトを表示するための設定
  ```
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1, user-scalable=no">
  ```
  ```
  /*-----スマホ向けの記述-----*/
  @media screen and (max-width: 479px) {　/*ウィンドウ幅が0～479pxの場合にCSSを適用*/
  #menu-bg {
  background-color: #00FF00;　/*緑色*/
  }
  ```
- 疑似要素の利点
  - 構造とデザインを分離可能
  - 検索エンジンに引っかかる可能性が低い
    
    <img src="./test_icon.jpg">
    
    ```
    <ul class="test_list">
    <li class="before_list">リストの先頭に</li>
    <li class="before_list">アイコンをつけます</li>
    <li class="before_list">サイズ調整も</li>
    <li class="before_list">バッチリです！</li>
    ```
    ```
    .before_list:before {
    content:  '';                           /* 空白の要素を作る */
    height: 40px;                           /* 高さ指定 */
    width: 40px;                            /* 幅指定 */
    display:  inline-block;                 /* インラインブロックにする */
    background-image:  url(test-icon.png);  /* 背景画像指定 */
    background-size:  contain;              /* 背景画像サイズ指定 */
    background-repeat:  no-repeat;          /* 背景画像リピート指定 */
    background-position:  center;           /* 背景画像位置指定 */
    vertical-align:  middle;                /* 上下中央揃え */
    margin-right:  10px;                    /* 右側に間を */
    }
    ```

- positionとdisplay
- HTML living standard に準拠すべき理由(セマンティックなコーディング)
  - 開発者が読みやすい
  - 機械が読みやすい
- cssのサイズについて<br>
 パターンとしては絶対値基準と相対値基準の2種類
- widthとheightの使い方の違い
- margin,padding,content,border<br>
 各要素について図で理解できるようにする。<br>
 横要素のみはmargin autoが使える。この書き方はよく見かける。
- website制作で使用する便利ツール
  - 差分比較difff、Winmerge<br>
    ファイルの差分比較に使う。
  - markup validation service
  - サクラエディタ<br>
    Javaの開発でよく使われる。メモ帳に似ているが便利な使い方が可能。

## (4)次回内容の確認/日程調整










