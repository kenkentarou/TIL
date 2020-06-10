#　クラスメソッドのテクニック的な話

クラスメソッドにすると、レシーバに複数のオブジェクトの集合を使うことができる。

例：
monthly_sale.rb

class << self

  def less_than_minimum_relic_share?
   
   first.site.minimum_relic_share > all.sum(&:relic_share)
  
  end
  
end 
 
 siteが複数のmonthly_saleを持つ関連付けになっているとすると、
 
 @monthluy_sales.less_than_minimum_relic_shareとかで使える。
 メソッドの中では、レシーバーとしてのmonthly_salesをallとかmapとかで受けることができる
 また、first.siteの部分は、レシーバーの@monthly_salesに対しての、
 firstで一番目のオブジェクトを取って来て、それに対して、siteで関連するsiteのオブジェクトを取って来ている。
 関連付けになっているモデルのデータもこれで取ってこれる。（この場合は何を取って来ても全て紐づいているsiteは同じなので、このやり方でもできるが、
 紐づいているものがそれぞれ違う場合にはこのやり方だと不十分なケースもある。）
