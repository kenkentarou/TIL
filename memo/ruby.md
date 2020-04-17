- インスタンス変数は未定義の状態でも自由に代入したり、参照できる
- ローカル変数は定義しておかないと使えない。いきなりローカル変数を使うとだめ。
- セッターメソッド以下の例で言う、「name」メソッドのことをいう

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
