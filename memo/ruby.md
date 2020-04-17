- インスタンス変数は未定義の状態でも自由に代入したり、参照できる
- ローカル変数は定義しておかないと使えない。いきなりローカル変数を使うとだめ。
- ゲッターメソッドは以下の例で言う、「name」、セッターメソッドは以下の例で言う「name=(value)」のことを言う
- クラス自身（クラスオブジェクト）に対してnewを実行すると、initializeの引数に値を入れてインスタンスを生成する。

```
class User
  def initialize(name)
    @name = name
  end
  
  # @nameを外部から参照するメソッド
  def name
    @name
  end
  
  # @nameを外部から変更するメソッド
  def name=(value)
    @name = value
  end
end

```
