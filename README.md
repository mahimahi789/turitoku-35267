# README

# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false, unique: true|
| encrypted_password | string | null: false |
| j_name   | string | null: felse |
| j_k_name | string | null: false |
| j_k_n_name | string | null: false |
| j_k_n_c_name | string | null: false |
| birthday | date | null: false |

### Association

- has_many :items
- has_many :comments 

## items テーブル

| Column   | Type       | Options                        |
| ------   | ---------- | ------------------------------ |
| item_name | text       | null: false |
| item_description   | text | null: false |
| category_id | integer | null: false |
| condiion_id | integer | null: false |
| burden_id   | integer | null: false |
| area_id     | integer | null: false |
| days_id     | integer | null: false |
| price    | integer | null: false |
| user_id  | integer | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments 



## comments テーブル

| Column  | Type       | Options                         |
| ------- | ---------- | ------------------------------  |
| user_id | integer |  |
| item_id | integer |  |
| text | text | null: false |

### Association

- belongs_to :item
- belongs_to :user
