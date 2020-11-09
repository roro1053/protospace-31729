## users テーブル

|   Column   |  type  | Options                           |
|------------|--------|-----------------------------------|
|    email   | string | null: false                       |
|  password  | string | null: false                       |
|    name    | string | null: false                       |
|  profile   |  text  | null: false                       |
| occupation |  text  | null: false                       |
|  position  |  text  | null: false                       |

### Association
- has_many :prototypes
- has_many :comments

## prototypes テーブル
|   Column   |    type    | options                           |
|------------|------------|-----------------------------------|
|   title    |   string   | null: false                       |
| catch_copy |    text    | null: false                       |
|  concept   |    text    | null: false                       |
|   image    |            | Active Storage                    |
|    user    | references | null: false, foreign_key: true    |

### Association
- belongs_to :users
- has_many :comments

## Comments テーブル
|   Column   |    type    | options                           |
|------------|------------|-----------------------------------|
|    text    |    text    | null: false                       |
|    user    | references | null: false, foreign_key: true    |
| prototype  | references | null: false, foreign_key: true    |

### Association
- belongs_to : users
- belongs_to : prototypes
