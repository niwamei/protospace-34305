# テーブル設計

## usersテーブル

| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| email       | string | null: false |
| password    | string | null: false |
| name        | string | null: false |
| profile     | string | null: false |
| occupation  | string | null: false |
| position    | string | null: false |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type       | Options           |
| ---------- | ---------- | ----------------- |
| title      | string     | null: false       |
| catch_copy | text       | null: false       |
| concept    | text       | null: false       |
| user       | references | foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

## commentsテーブル

| Column     | Type       | Options           |
| ---------- | ---------- | ----------------- |
| text       | text       | null: false       |
| user       | references | foreign_key: true |
| prototype  | references | foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototype