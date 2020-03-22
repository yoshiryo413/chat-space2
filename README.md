# README

# DB設計

## user table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string| null: false|
|password|string|null: false|

### association

- has_many :groups through :groups_users
- has_many :messages 

## message table

|Column|Type|Options|
|------|----|-------|
|boby|text|null: false|
|image|string| 
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### association

- belongs_to :user
- belongs_to :group 

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group name|string|null: false,|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :messages
- has_many :users through :groups_users

