# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

# テーブル設計

## usersテーブル
| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| family_name        | string | null: false               |
| first_name         | string | null: false               |
| family_name_kana   | string | null: false               |
| first_name_kana    | string | null: false               |
| birth      　　　   | date   | null: false               |

### Associations
- has_many :movies
- has_many :comments

## movieテーブル
| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| movie_title     | string     | null: false                    |
| introduction    | text       | null: false                    |
| category_id     | integer    | null: false                    |
| user            | references | null: false, foreign_key: true |

### Associations
- belongs_to :user
- belongs_to_active_hash :category

## commentsテーブル
| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | text       | null: false                    |
| user    | references | null: false, foreign_key: true |
| movie   | references | null: false, foreign_key: true |

### Associations
- belongs_to :user
- belongs_to :movie

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...