#テーブル設計

## users テーブル

  |  Coliumn   |  Type  | Option    |
  |------------|--------|--------   |
  |email       |string  |null:false |
  |password    |string  |null:false |
  |name        |string  |null:false |
  |profile     |text    |null:false |
  |occupation  |text    |null:false |
  |position    |text    |null:false |

### Association
  - has_many :comments
  - has_many :prototypes


## prototypes テーブル

  |  Coliumn   |  Type     | Option                        |
  |------------|-----------|-------------------------------|
  |title       |string     |null:false                     |
  |catch_copy  |text       |null:false                     |
  |concept     |text       |null:false                     |
  |image       |           |                               |<!--ActiveStorageで実装-->
  |user        |references |null: false, foreign_key: true |

### Association
  - has_many :comments
  - belongs_to :users

## comments テーブル

  |  Coliumn  |  Type     | Option                        |
  |-----------|-----------|-------------------------------|
  |text       |text       |null:false                     |
  |user       |references |null: false, foreign_key: true |
  |prototype  |references |null: false, foreign_key: true |

### Association
  - belongs_to :users
  - belongs_to :prototypes
