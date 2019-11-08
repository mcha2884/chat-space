## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null:false|
|name|string|null:false|
### Association
- belongs_to :messages
- has_many :users,through: :groups_users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null:false|
|body|text|null:false|
|image|string|null:false|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null:false|
|name|string|null:false|
|e-mail|varchar(100)|null:false|

### Association
- has_many :groups,through: :groups_users
- belongs_to :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key: true|
|group_id|integer|null:false,foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
