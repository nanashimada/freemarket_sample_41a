
# README



## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|nickname|string|null: false|
|phonetic|string|null: false|
|user_image|string|
|introduction|text|
|birth_id|integer|null: false, foreign_key: true|
|address_id|integer|null: false, foreign_key: true|
|credit_id|integer|null: false, foreign_key: true|
|item_id|integer|null: false, foreign_key: true|

### Association
- has_many :items
- has_one :address
- has_one :birth
- has_one :credit



## addressテーブル

|Column|Type|Options|
|------|----|-------|
|prefecture|string|null: false|
|city|string|null: false|
|house_number|string|null: false|
|post_code|integer|
|building|string|

### Association
- belongs_to :user



## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|year|integer|null: false|
|month|integer|null: false|
|day|integer|null: false|


### Association
- belongs_to :user



## creditテーブル

|Column|Type|Options|
|------|----|-------|

### Association
- belongs_to :user



## itemsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|value_id|integer|null: false, foreign_key: true|
|parent_category_id|integer|null: false, foreign_key: true|
|name|string|null: false|
|image|string|null: false|
|description|string|null: false|
|status|integer|null: false|
|delivery_fee|integer|null: false|
|pre_date|integer|null: false|


### Association
- belongs_to :user
- has_one :parent_category




## parent_categoryテーブル

|Column|Type|Options|
|------|----|-------|
|large_category_id|integer|null: false, foreign_key: true|
|midium_category_id|integer|null: false, foreign_key: true|
|small_category_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :items
- has_one :large_category
- has_one :midium_category
- has_one :small_category


## large_categoryテーブル

|Column|Type|Options|
|------|----|-------|
|category_name|string|null: false|

### Association
- belongs_to :parent_category


## midium_categoryテーブル

|Column|Type|Options|
|------|----|-------|
|category_name|string|null: false|

### Association
- belongs_to :parent_category


## small_categoryテーブル

|Column|Type|Options|
|------|----|-------|
|category_name|string|null: false|

### Association
- belongs_to :parent_category



## valueテーブル

|Column|Type|Options|
|------|----|-------|
|price|string|null: false|
|profit|string|null: false|


### Association
- belongs_to :item
