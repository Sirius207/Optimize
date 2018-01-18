# Optimize
Optimize is a simple way to help you manage your tasks &amp; time.


## Specification


## Database Diagram

## Table Overview
| Table Name     | Description | Remarks |
| -------------- | ----------- | ------- |
| time_log       | 單日時間使用  |         |
| usages         | 單項行動資訊  |         |
| goal           | 時間使用目標  | e.g. Read: 10hr/week, from.week.to.week |


## Table Details

### Table: time_log

| Field              | Type               | Null | Key | Default | Remarks |
| ------------------ | ------------------ | ---- | --- | ------- | ------- |
| date               | varchar(25)        |      | PRI |         | 2018-01-18 |
| usage              | varchar(64)        | YES  |     |  NULL   |         |
| created_at         | timestamp          |      |     |         |         |
| updated_at         | timestamp          |      |     |         |         |


### Index

| Keyname  | Type    | Field    |
| -------- | ------- | -------- |
| date     | PRIMARY | date  |
| usage    | INDEX   | usage |

### Table: usages

| Field              | Type               | Null | Key | Default | Remarks |
| ------------------ | ------------------ | ---- | --- | ------- | ------- |
| id                 | varchar(25)        |      | PRI |         | auto_increment |
| title              | varchar(25)        |      |     |         | e.g. 'Read'    |
| Style              | varchar(25)        |      |     |         | e.g. '#fff'  |
| children           | [varchar(25)]      |      |     |  []     |         |
| created_at         | timestamp          |      |     |         |         |
| updated_at         | timestamp          |      |     |         |         |


### Index

| Keyname  | Type    | Field    |
| -------- | ------- | -------- |
| id       | PRIMARY | id       |
| title    | INDEX   | title    |
