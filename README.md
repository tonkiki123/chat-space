# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
|messages_id|integer|null: false,foreign_key: true|
### Association
- has_many :groups, through: :groups_users
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|messages_id|integer|null: false,foreign_key: true|
### Association
- has_many :users, through: :groups_users
- has_many :messages
- has_many :members

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|groups_id|integer|null: false,foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
 

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|groups_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user