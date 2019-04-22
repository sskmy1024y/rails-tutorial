# Rails Tutorial My Memo

## Chapter2
### 1.  モデルの作成
   
データモデルの作り方。

![ユーザのデータモデル](https://railstutorial.jp/chapters/images/figures/demo_user_model.png)

例えばこのようなusersモデルを作りたい時は、 `scaffold`コマンドを用いる。

``` bash
$ rails generate scaffold User name:string email:string
# rails generate scaffold [Model名] [カラム名:型] [カラム名:型]
```

データベースをマイグレートする。
```bash
$ rails db:migrate
```

### 2. モデルの関連付け

モデル同士の関連付け。

```ruby : app/models/user.rb
class User < ApplicationRecord
  has_many :microposts
end
```

```ruby : app/models/micropost.rb
class Micropost < ApplicationRecord
  belongs_to :user
  validates :content, length: { maximum: 140 }
end
```

