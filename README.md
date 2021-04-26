# テーブル設計

   users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | NOT NULL    |
| password  | string | NOT NULL    |
| name      | string | NOT NULL    | 
| profile   | text   | NOT NULL    | 
| occupation| text   | NOT NULL    | 
| position  | text   | NOT NULL    | 

    Association

- belongs_to :prototypes
- has_many :comments

   prototypes テーブル

| Column      | Type   | Options     |
| --------    | ------ | ----------- |
| title       | string | NOT NULL    |
| catch_copy  | text   | NOT NULL    |
| concept     | text   | NOT NULL    | 
| image       | ActiveStorageで実装   |
| user        | references型         | 

    Association

- has_many :comments
- belongs_to :users

    comments テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| text     | text    | NOT NULL   |
| user     | references型         |
| prototype| references型         | 

    Association

- belongs_to :users
- belongs_to :prototypes
