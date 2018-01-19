# Optimize
Optimize is a simple way to help you manage your tasks &amp; time.


## Specification


## Database Diagram

## Table Overview
| Table Name     | Description | Remarks |
| -------------- | ----------- | ------- |
| time_log       | 單日時間使用  |         |
| usages         | 單項行動資訊  |         |
| objectives     | 時間使用目標  | e.g. Read_week1-week2_10hr/week, |


## Table Details

### Table: time_log

| Field              | Type               | Null | Key | Default | Remarks |
| ------------------ | ------------------ | ---- | --- | ------- | ------- |
| date               | varchar(25)        |      | PRI |         | e.g. '2018-01-18' |
| usage              | varchar(64)        | YES  |     |  NULL   | e.g. '1~2_0_3_4' |
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


### Table: objectives

| Field              | Type               | Null | Key | Default | Remarks |
| ------------------ | ------------------ | ---- | --- | ------- | ------- |
| id                 | varchar(25)        |      | PRI |         | auto_increment |
| usage_id           | varchar(25)        |      | IND |         |         |
| times              | varchar(25)        | YES  |     |         | e.g. '30hr/week' |
| start_date         | timestamp          |      |     |         |         |
| end_date           | timestamp          | YES  |     |         |         |
| created_at         | timestamp          |      |     |         |         |
| updated_at         | timestamp          |      |     |         |         |


### Index

| Keyname  | Type    | Field    |
| -------- | ------- | -------- |
| id       | PRIMARY | id       |
| start    | INDEX   | start    |