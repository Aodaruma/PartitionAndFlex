# Partition & Flex

kd 木みたいに変形して配置したり、オブジェクト自体を分割して変形させたりするスクリプトです。

現在は **version 1.22** が最新です。

![thumbnail](https://github.com/Aodaruma/Aodaruma-AviUtl-Script/blob/main/Partition%26Flex/partiotionFlexThumbnail.png)

以下のスクリプトが備わっています。

- **オブジェクト配置**

  オブジェクトや個別オブジェクトを、指定範囲内に変形して配置します。
  以下はパラメーターの説明です

  - sizeX
    - X 軸方向の範囲を指定します。
  - sizeY
    - Y 軸方向の範囲を指定します。
  - grid(%)
    - グリッド状に配置する影響度です。
  - seedAF(%)
    - 分割に用いる乱数の seed を連続的に変化させるパラメーターです。
  - 個別対応
    - 個別オブジェクトの個数に合わせて分割・変形・配置します。
  - 個数(非個別)
    - ↑ のパラメーターが off の時、ここに指定された個数だけ分割します。
  - 変形(%)
    - 元のオブジェクトの形状・配置からどれだけ変化させるか影響度を指定します。
  - 分割解像度
    - 分割を行う乱数のステップを指定します。
  - 間隔
    - 各分割されたオブジェクトそれぞれの間隔を指定します。
  - order
    - 個別オブジェクトを変形させるとき、変形の文字の並べ方を指定します。
      - 数字 `0`, `1`, `2` が入力された時
        - `0` : **kd木順序** / 分割された順番から割り振ります。
        - `1` : **横書き順序** / 横書きの並べ方で割り振ります。
        - `2`  : **縦書き順序** / 縦書きの並べ方で割り振ります。
      - 文字 `"r"` が入力された時
        - **ランダム順序** / ランダムに並べ方を割り振ります。ランダムのseedは `seed` パラメーターと同期しています。
      -  `{0,1,2}` などの数字を要素としたテーブルが入力された時
        - 数字 `0` が入力された順番をもとに、各テーブルの要素の順番に並べ替えて配置します。省略された要素は、数字 `0` が入力された順番で補完されます。
  - easing
    - _seedAF(%)_ のパラメーターのイージングの種類を指定します。
      使用するときは、`easing.lua`、`easing_aviutl.lua` が必要です。導入方法は[こちら](https://seguimiii.com/aviutl-tech/easingtra)を参照ください。
      もし上述のファイルがない場合・正常に読み込めない場合・不正な値が入力された場合は、_seedAF(%)_ はリニアで変形します。
  - seed
    - 分割に用いる乱数の seed です。

- **オブジェクト分割 （補完なし）**

  オブジェクトを分割して、変形させます。

  - 分割数
    - オブジェクトを分割する回数です。$n$ 回分割するごとに $3^n$​ だけ変形部分が増えます。
  - grid(%)
    - グリッド状に変形する影響度です。元に戻す変形と捉えてもらって構いません。
  - seedAF(%)
    - 分割に用いる乱数の seed を連続的に変化させるパラメーターです。
  - 分割解像度
    - 分割を行う乱数のステップを指定します。
  - easing
    - _seedAF(%)_ のパラメーターのイージングの種類を指定します。
      使用するときは、`easing.lua`、`easing_aviutl.lua` が必要です。導入方法は[こちら](https://seguimiii.com/aviutl-tech/easingtra)を参照ください。
      もし上述のファイルがない場合・正常に読み込めない場合・不正な値が入力された場合は、_seedAF(%)_ はリニアで変形します。
  - seed
    - 分割に用いる乱数の seed です。

## 導入方法 / how to install

[こちらのリポジトリ](https://github.com/Aodaruma/Aodaruma-AviUtl-Script)を参照してください。

## ライセンス / Licence

[こちらのリポジトリ](https://github.com/Aodaruma/Aodaruma-AviUtl-Script)を参照してください。

## バグ・意見 / how to report bugs

Twitter の DM に送るか、issue を立ち上げてください。

## 今後の予定

- [ ] オブジェクト分割（補完あり）を開発します*（時期未定）*
