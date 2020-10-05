## users テーブル
| Column     | Type   | Options                        |
| ---------- | ------ | ------------------------------ |
| email      | string | null: false, foreign_key: true |
| password   | string | null: false, foreign_key: true |
| name       | string | null: false, foreign_key: true |
| profile    | text   | null: false, foreign_key: true |
| occupation | text   | null: false, foreign_key: true |
| position   | text   | null: false, foreign_key: true |

### Association
- has_many :comments
- has_many :prototypes

## comments テーブル
| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototype

## prototypes テーブル
| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false, foreign_key: true |
| catch_copy | text       | null: false, foreign_key: true |
| concept    | text       | null: false, foreign_key: true |
| user       | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments