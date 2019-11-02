# README

## groups_usersテーブル

Things you may want to cover:
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|emil|string|null: false, index: true|

### Association
has_many :group_users
has_many :groups
has_many :messages

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user|integer|null: false, foreign_key: true|
|group|integer|null: false, foreign_key: true|

### Association
has_many :group_users
has_many :users
has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|foreign_key: true|
|group|references|foreign_key: true|
|content|string||
|image|string||

### Association

belongs_to :group
belongs_to :user