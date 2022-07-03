# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

# テーブル設計

## users テーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null:false, unique: true|
|encrypted_password|string|null: false|
|first_name|string|null: false|
|last_name|string|null: false|
|first_name_kana|string|null: false|
|last_name_kana|string|null: false|
|birthday|date|null: false|

## items テーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|info|text|null: false|
|category_id|integer|null: false| <!--Activehash-->
|sales_status_id|integer|null: false| <!--Activehash-->
|shipping_fee_status_id|integer|null: false| <!--Activehash-->
|prefecture_id|integer|null: false| <!--Activehash-->
|scheduled_id|integer|null: false| <!--Activehash-->
|price|integer|null: false|
|user|references|null: false, foreign_key: true|

## orders テーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|item|references|null: false, foreign_key: true|

## addresses テーブル

|Column|Type|Options|
|------|----|-------|
|post_code|string|null: false|
|prefecture_id|integer|null: false| <!--Activehash-->
|city|string|null: false|
|address|string|null: false|
|building|string|
|phone_number|string|null: false|
|order|references|null: false, foreign_key: true|
