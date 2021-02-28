###users テーブル
|column    |types |Options    |
|----------|------|-----------|
|email     |string|null: false|
|password  |string|null: false|
|name      |string|null: false|
|profile   |text  |null: false|
|occupation|text  |null: false|
|position  |text  |null: false|

###Association
has many :prototypes
has many :comments


###prototypes テーブル
|column    |types        |Options    |
|----------|-------------|-----------|
|title     |string       |null: false                   |
|catch_copy|text         |null: false                   |
|concept   |text         |null: false                   |
|user      |reference    |null: false, foreign_key: true|

###Association
has many :comments


###comments テーブル
|column    |types        |Options                       |
|----------|-------------|------------------------------|
|text      |string       |null: false                   |
|user      |reference    |null: false, foreign_key: true|
|prototype |reference    |null: false, foreign_key: true|


###Association
belongs_to :users
belongs_to :prototypes



