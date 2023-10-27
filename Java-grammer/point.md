- Javaの概要を理解しよう
  1996年から使われ始め現在では日本、海外問わず多くの国で使用されている言語です。また、日本では現在も多くの企業で利用されているため、案件数も非常に多くなっています。
  - Javaの特徴
  プログラミング言語には実行方法が主に2つあります。インタプリタ型とコンパイラ型がありJavaはコンパイラ型です。
　この実行方法の方が実行速度が速い特徴があります。
　また、プログラミング言語で必須と呼ばれるものにライブラリとフレームワークがあります。
　ライブラリとはよく使用する処理を再利用することで余計な工数を削減するためのツールです。
　フレームワークとは開発者が1から機能を作る必要がないよう土台を自動で生成してくれるツールです。現在ではSpring1強になっています。
  - Javaでできること
- Javaの開発環境を構築しよう
  Javaの開発に必要なものは以下の2つです。
  ・JDK(Java Development Kit)
  ・統合開発環境(IDE)
  Javaでよく使われるのはEclipse
- Javaの基本的な使い方を理解しよう
  - Javaクラスの基本的な書き方
    まずはプログラムの入り口にあたるmainクラスから見ていきましょう。
    ```
    public class HelloWorld {
    public static void main(String[] args) {
        // Hello Worldと表示
        System.out.println("Hello World");
    }
}
    ```
  - コメントのつけ方は2通りあります。
    ```
    // 1行でコメントを記入する場所
    ```
    ```
    /* 複数行で
       コメントを
       記入する場所 */
    ```
  - プロジェクトとパッケージの作成
    先頭英語大文字は非推奨
  - クラスの作成
    先頭は英語大文字
- データの扱い方を理解しよう
  Javaで扱うデータ型の種類と特徴を説明します。
  - データを扱って表示、計算をしてみよう
- (課題)四則演算を計算してみよう
- 変数を理解しよう
  まず前提としてデータをそのままの状態(ハードコーディング)で扱うことは避けられています。
  - 変数を使用するステップ
    - 宣言(箱を用意する)
    - 代入(箱にデータを入れる)
    - 参照(箱に入っているデータを利用する)
    ```
    // 宣言
    int number ;
    // 代入
    number = 123;
    // 参照
    System.out.println(number);
    // 再代入
    number = 456;
    // 参照
    System.out.println(number);
    ```
  - final
    finalを変数の前につけることで再代入ができなくなります。
    ```
    final double PI = 3.14159 // 円周率
    ```
  - 命名規則
  Javaの変数ではローワーキャメルケースが慣例。キャメルとはラクダのこと。
  例：studentNumber,student
- データの型変換を理解しよう
  Javaの型変換には2パターンあります。自動型変換と手動型変換です。
  - 自動型変換
    コンパイラがコンパイル(翻訳時)に自動で変換してくれます。該当パターンはデータよりも大きい変数に代入するとき。
    ```
    long valLong = 123; // int型の値をlong型へ型変換してから代入
    ```
  - 手動型変換
    キャスト演算子を使用します。データよりも小さい変数に代入するときなどに使用します。
  ```
        int distance = 120; // 距離(m)
        int time = 25; // 所要時間(秒)
        // 距離と所要時間から速度(m/秒)を計算
        float speed =  (float)distance / (float)time;
  ```
- 条件分岐のif文を理解しよう
  条件分岐とは条件によって特定の処理だけ実行したいときに使用します。
  - if文
  - switch文
  - 比較演算子
  - if文の書き方
  ```
  if( 条件式A ) {
    条件式Aがtrue（真）のときの処理
} else if( 条件式B ) {
    条件式Aはfalse（偽）だが、条件式Bはtrue（真）のときの処理
} else {
    条件式Aも条件式Bもfalse（偽）のときの処理
}
  ```
  - 論理演算子&&,||
- 条件分岐のswitch文を理解しよう
if文のほかにswitch文という条件分岐の方法があります。両者はそれぞれ利用シーンが異なるため、特徴を抑え使い分けられるようにしましょう。
　- if文のデメリット
  if文は分岐が多くなればなるほど可読性が落ち、メンテナンスもしづらくなります。
  - switch文の書き方
  switch文の記述方法はJavaのバージョンによって異なります。<br>
  2020年にJava14にバージョンアップしswitch文の仕様が変更されました。<br>
  実務では以前の記述方法も使用されているため、現場ごとに記載を合わせるようにします。
  ```
  // Java14以降の記述方法
  int ranking = 1; // 順位

  switch(ranking) {
    case 1  -> System.out.println("金メダル");
    case 2  -> System.out.println("銀メダル");
    case 3  -> System.out.println("銅メダル");
    default -> System.out.println("参加賞"); // どの条件にも当てはまらなかった場合
  }
  // Java13までの記述方法
  switch(ranking) {
    case 1:
      System.out.println("金メダル");
      break; // break文と呼ばれ書かないと次の条件式も実行してしまう。
    case 2:
      System.out.println("銀メダル");
      break;
    case 3:
      System.out.println("銅メダル");
      break;
    default:
      System.out.println("参加賞");
      break;
  }
  // break文の記載漏れなどで生じるウォークスルーを防ぐために仕様変更が行われた。
  ```
  - switch式
Java14以降ではswitch文の結果を変数に格納し、使用することも可能です。
```
award = switch(ranking) {
    case 1  -> "金メダル";
    case 2  -> "銀メダル";
    case 3  -> "銅メダル";
    default -> "参加賞";
};
```
- 繰り返し処理のfor文を理解しよう
 繰り返し処理とは同様の内容の処理を指定した条件の間、連続で実施することを言います。<br>
 Javaではよく使用するものとしてfor文とwhile文があります。<br>
 この章ではfor文について説明したいと思います。<br>
  - for文の書き方
  ```
  // for(初期化式;条件式;条件式)
  for(int i = 0; i < 11; i ++){
    System.out.println(i);
  }
  ```
  - スコープ
  - 無限ループ
  - break文とcontinue文
- 繰り返し処理のwhile文を理解しよう<br>
  前回、繰り返し処理で決まった回数だけ処理を繰り返すfor文について学習しました。<br>
  一方で毎回の処理の回数がランダムな処理についてはどうしたらよいでしょうか？<br>
  while文を使用することで、ランダム回数の繰り返し処理について、便利に記述することが可能です。<br>
  - while文の書き方
  ```
  int dice=0;
  // while(条件式)
  while( dice != 6 ) {
    // サイコロを振る(1～6の目をランダムで生成)
    // Math.ceilで小数点以下の切り上げ
    dice = (int)( Math.ceil( Math.random() * 6 ) );
    System.out.println("サイコロの目は" + dice);
  }
  ```
  - do-while文
- 配列を理解しよう
  配列とは複数の同じ種類のデータを1つの変数にまとめたものです。
  - 配列の使い方
  基本的には変数と同様に(1)宣言→(2)代入→(3)参照の順に使用します。
  ```
  // (1)宣言
  int[] scoreArray = new int [5]; // 推奨
  int scoreArray[] = new int [5];
  // (2)代入
  scoreArray[2] = 50;
  // (3)参照
  System.out.println(scoreArray[2]);
  ```
  もしくは(1)と(2)を同時に行う初期化も使用できます。
  ```
  int [] scoreArray = {10,20,30,40,50};
  ```
  - index外の要素を参照した場合
  indexとは配列の書くように振られている番号です。振られていない番号に対して参照するとエラーが発生してしまいます。
  ```
  System.out.println(scoreArray[6]);
  ```
  対策として配列.lengthを使用し、要素外参照を予防する。
  - 拡張for文
  拡張for文とはfor文の別の記述方法のことで配列の要素数の数だけ繰り返し処理を実行することができます。<br>
  この書き方だと細かい繰り返し条件の指定はできませんが、要素外参照や無限ループを予防することができます。
  ```
  int[] scoreArray = { 70, 85, 80, 95, 90 }; // 点数

  // scoreArrayの各要素を順番に表示
  for( int score : scoreArray ) {
    System.out.println(score);
  }
  ```
- ［課題］1から100まである素数を見つけよう
- メソッドを理解しよう
 メソッドとはよく利用する一連の処理をひとまとめにし再利用できる形にしたものです。
 - mainメソッド
 前章までで既に使用していたメソッドで、プログラムの処理の始めと終わりは必ずこのメソッドで終わります。
 ```
 public static void main(String[] args) {
    処理内容;
 }
 ```
 - 修飾子
 - メソッドの命名規則(復習)
 - メソッドの書き方と呼び出し方
 ```
        int greeting = 123;

        // greetingメソッドの呼び出し（1回目）
        greeting();

        // greeting変数の値を表示
        System.out.println(greeting);

        // greetingメソッドの呼び出し（2回目）
        greeting();
    }

    // 朝のあいさつを表示するメソッド
    public static void greeting() {
        System.out.println("おはようございます！");
        System.out.println("昨日はよく眠れましたか？");
        System.out.println("今日も一日頑張りましょう！");
    }
  ```
- メソッドの引数・戻り値を理解しよう
 引数とはメソッドに渡すデータのことです。一方、戻り値はメソッド内での処理を実行し、呼び出し元に渡されるデータのことです。
 - メソッドに引数を渡してみよう
 - メソッドから戻り値を受け取ってみよう
 - メソッドのオーバーロード
 メソッド名が同じメソッドでも渡す引数の内容の違いによって複数作成することができます。これをオーバーロードといいます。
 条件は以下の通りです。
 ・引数のデータ型が異なる
 ・引数の数が異なる
 ・引数の順番が異なる
```
public static void main(String[] args) {
        test(123);        // test(1)を呼び出す
        test(1.23F);      // test(2)を呼び出す
        test(123, 1.23F); // test(3)を呼び出す
        test(1.23F, 123); // test(4)を呼び出す
    }

    // test(1)
    public static void test( int i ) {
        System.out.println("(1)int型：" + i );
    }

    // test(2)
    public static void test( float f ) {
        System.out.println("(2)float型：" + f );
    }

    // test(3)
    public static void test( int i, float f ) {
        System.out.println("(3)int型：" + i + "／float型：" + f );
    }

    // test(4)
    public static void test( float f, int i ) {
        System.out.println("(4)float型：" + f + "／int型：" + i );
    }
```
  - 戻り値を使ってみよう
  ```
public static void main(String[] args) {

        int[] scoreArray = { 70, 85, 80, 95, 90, 120 }; // 点数

        // 点数ごとに成績を付ける
        for( int score : scoreArray ) {
            System.out.println( score + "点だと成績は" + getGrade(score) );
        }
    }

    // 点数から成績を求めるメソッド
    public static char getGrade( final int score ) {
        char grade = 'C';

        // 点数が不正だった場合は成績を「－」としてメソッドを終了
        if( (score < 0) || (100 < score) ) {
            return '－';
        }

    	  // 点数によって成績を決める
    	  if( 90 <= score ) {
    	      grade = 'A';
    	  } else if( 80 <= score ) {
    	      grade = 'B';
        }

        // 求めた成績を戻り値として返す
        return grade;
    }
}
```
- クラスを理解しよう
 クラスとは特徴をもったモノ(オブジェクト)を作成する際の設計図の役割を担っているものです。
 例えば、自動車を例にしてみると、
 ・トラック
 ・普通自動車
 ・消防車
 など設計図(自動車)をもとに様々な乗り物(オブジェクト)を生成することが可能になります。
 また、クラスをもとに生成されたオブジェクトをインスタンス(実体)と呼びます。
　- クラスの使い方
  ```
  public static void main(String[] args) {

        // 商品データを生成
        Product shampoo = new Product( "シャンプー", 800, 10 );
        Product coffee  = new Product( "コーヒー", 500, 5 );

        // シャンプーを7点注文
        shampoo.takeOrder(7);

        // コーヒーを3点注文
        coffee.takeOrder(3);

        // シャンプーを5点注文
        shampoo.takeOrder(5);
    }
  ```
  ```
  // 商品クラス
public class Product {
    // フィールド（内部データ）
    private String name  = ""; // 商品名
    private int    price = 0;  // 価格（税込）
    private int    stock = 0;  // 在庫数

    // コンストラクタ（初期化処理）
    public Product( String name, int price, int stock ) {
        this.name  = name;
        this.price = price;
        this.stock = stock;

        System.out.println("【商品データ生成】" + this.name );
        System.out.println("価格：" + this.price +
                           "円（税込）／在庫数：" + this.stock );
    }

    // 【メソッド】注文を受けて在庫数を更新する
    // number：注文数
    public void takeOrder( final int number ) {
        System.out.println("【注文処理開始】");
        System.out.println("商品名：" + this.name );
        System.out.println("単品価格：" + this.price + "円（税込）" );
        System.out.println("注文数：" + number +
                           "／在庫数：" + this.stock );

        // 注文数が在庫数を超えていたら購入不可
        if( this.stock < number ) {
            System.out.println( this.name + "は在庫不足です" );
            return; // 購入できないため終了
        }

        // 購入金額を計算
        int total = this.price * number;
        System.out.println( number + "点で合計" +
                            total + "円（税込）です");

        // 購入のため在庫数を更新
        this.stock -= number;
        System.out.println( this.name + "の残り在庫は" + this.stock );
    }
}
```
 - import
importとは他のパッケージにあるクラスを使用したい場合に記述します。
Eclipseでは自動入力してくれる。
```
import パッケージ名.クラス名;
```
- ［課題］車クラスを作って動かそう
- Javaのカプセル化を理解しよう
  カプセル化とは外部から該当クラスの情報を自由に変更されないためにクラスのフィールドを守ることです。
  守るためにはアクセス修飾子というものを使用します。
  また、外部クラスからアクセスしたい場合はセッターとゲッターというものを使用します。
- クラスの継承を理解しよう
継承とは別のクラスの情報を受け継ぎ、新たにクラスを生成することです。
  - オーバーライド
  - super
  - protectedとアクセス修飾子なし
  - 抽象メソッド
  - ポリモーフィズム
- コレクションを理解しよう
  コレクションとは複数のデータのまとまりのことです。コレクションの代表的なものはList、Map、Setなどがあります。
  以前の章で習った配列との違いは要素を変更できる点や用途によってコレクションごとに異なる使い方ができることです。
  - List
    Listは格納した順番にデータを保存するコレクションで重複も許されます。
    今回は代表的なArrayListというものについて学習したいと思います。
    ```
            // 宣言
        List<Integer> list = new ArrayList<Integer>();
        // 追加
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        // 削除
        list.remove(1);
        // 参照
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
    ```

  - Map
    Mapはキーとバリューといった2つの要素が1セットになって格納されているコレクションです。
    今回はHashMapについて学習したいと思います。
    ```
            // 宣言
        Map<Integer, String> map = new HashMap<Integer, String>();
        // 追加
        map.put(1, "林");
        map.put(2, "田中");
        map.put(3, "小林");
        map.put(4, "佐々木");
        // 削除
        map.remove(1);
        // 参照
        for (int i = 0; i < map.size(); i++) {
            System.out.println("キーが" + (i + 1) + "の人の名前は" + map.get(i + 1));
        }
    ```
    
  - Set
    Setはこれまでの2つのコレクションとは異なり重複を許容しないコレクションです。つまり、同じ内容のデータを追加しても先に追加されたデータだけ残されます。
    今回はHashSetについて学習したいと思います。
    ```
            // 宣言
        Set<Integer> set = new HashSet<Integer>();
        // 追加
        set.add(1);
        set.add(2);
        set.add(3);
        set.add(3);
        set.add(3);
        set.add(4);
        set.add(4);
        // 要素数の確認
        set.forEach(e -> System.out.println(e));
        // 削除
        set.remove(1);
        // 参照
        System.out.println(set);
     ```
  - 継承を使って自分と家族を紹介しよう
  - Stringクラスを理解しよう
    Stringクラスを学ぶことで文字列を加工したり、比較したりと様々な処理が可能となります。
    - equalsメソッド
    equalsメソッドは文字列同士を比較するメソッドです。一方で==は等価演算子で文字列同士のインスタンスが等しいか比べます。
    - lengthメソッド
    lengthメソッドは文字列の長さが知りたいときに使用します。なお、他に配列の長さ長さでも使用できます。
    - エスケープシーケンス
  - Mathクラスを理解しよう
    Mathクラスを理解することで数値を扱った様々な処理が可能となります。
　　- sqrtメソッド
    引数で渡した値の平方根を戻り値として返します。
    - cbrtメソッド
    引数で渡した値の立方根を戻り値として返します。
　　- roundメソッド
    乱数を返します。
　- 日時を扱うクラスを理解しよう#1
   Calenderクラスは月の初期値が0なので気を付ける。
　- 辞書プログラムを作ろう
  - 日時を扱うクラスを理解しよう#2
  - Scannerクラスで入力する方法を理解しよう
  ScannerクラスとはJavaプログラムに対しての入力処理を実施するクラスです。
  - 例外処理に対処する方法を理解しよう
　例外処理とはプログラムの実行中に異常な事態が発生した際に対応する処理のことです。
　異常な事態のことを例外といいます。
    - Exceptionクラス
    Exceptionクラスには種類があります。
　　エラーと検査例外と非検査例外です。
　　・エラー<br>
    Javaの動作環境などプログラム外の問題で対処はできない。
    ・検査例外
    例外処理が実装されたかどうかコンパイラがチェックしているもの。対処が必要です。
    ・非検査例外
    例外処理が実装されたかどうかコンパイラがチェックしていないもの。対処は不要。
    - try~catch
    - throwsの利用シーン
