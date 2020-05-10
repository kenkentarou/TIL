インスタンスメソッドの定義のパターン

・レシーバーを暗黙的にメソッド内で使うパターン
```
class HogeHoge
  attr_accessor :title, :name

  def initialize(title, name)
    @title = title
    @name = name
  end

# インスタンスメソッド
  def hoge
    title.hogehoge
  end

end
```

・レシーバーをメソッド内で使わないパターン
※必ずしもインスタンスメソッド内で、暗黙的に存在するレシーバー（self）を使う実装をしなくても良い。
以下は、アクセサメソッド（attr_accessor）を定義せずに、メソッド内で、そのクラスのインスタンス変数のみを参照する場合

```
class HogeHoge

  def initialize(location)
    @csv_data = CSV.read(location)
  end

  # インスタンスメソッド
  # メソッド内でレシーバー（暗黙的なオブジェクト）を使っていない
  def load
    @csv_data.map { |data| Task.new(date: data[CSV_DEFINITION::DATE], title: data[CSV_DEFINITION::TITLE], done: data[CSV_DEFINITION::DONE]) }
  end
end
```
