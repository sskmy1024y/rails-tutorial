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

## Chapter3
### 1. 静的なPageコントローラを生成

```bash
$ docker-compose run web rails generate controller StaticPages home help
```

### 2. ルーティングを設定

```ruby : config/routes.rb
 Rails.application.routes.draw do
  get  'static_pages/home' #<- 新しいページ
  get  'static_pages/help'
  root 'application#hello'
  end
```
