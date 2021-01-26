# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | null: false |
| password  | string | null: false |
| name      | string | null: false |
| profile   | text   | null: false |
| occupation| text   | null: false |
| position  | text   | null: false |

### Association

- has_many :prototypes
- has_many :comment

## prototypes テーブル

| Column      | Type            | Options     |
| ----------- | --------------- | ----------- |
| title       | string          | null: false |
| catch_copy  | text            | null: false |
| concept     | text            | null: false |
| image       | ActiveStorage   | null: false |
| user        | reference       | null: false |
### Association

- has_many :comment
- belong_to :users

## comment テーブル

| Column      | Type       | Options     |
| ----------  | ---------- | ----------- |
| text        | text       | null: false |
| user        | references | null: false |
| prototype   | references | null: false |

### Association

- belongs_to :users
- belongs_to :prototypes