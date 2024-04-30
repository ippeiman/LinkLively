# LinkLively

ここにプロジェクトの概要説明を記載します。

## 機能一覧

- ユーザー管理（登録、ログイン、ログアウト）
- イベントの作成、編集、削除
- イベントへの参加登録
- 貢献度の記録と評価
- 通知機能
- レポート生成機能

## 技術スタック

- Ruby on Rails
- PostgreSQL
- React (オプション)
- Docker (オプション)

## データベース設計

### Users（ユーザー）

| Column              | Type    | Description        |
|---------------------|---------|--------------------|
| id                  | integer | 主キー             |
| email               | string  | メールアドレス     |
| encrypted_password  | string  | 暗号化されたパスワード |
| name                | string  | ユーザー名         |
| birthdate           | date    | 生年月日           |
| created_at          | datetime| 作成日時           |
| updated_at          | datetime| 更新日時           |

### Events（イベント）

| Column              | Type    | Description        |
|---------------------|---------|--------------------|
| id                  | integer | 主キー             |
| name                | string  | イベント名         |
| description         | text    | 説明               |
| date                | date    | 開催日             |
| created_by_user_id  | integer | 作成者ID           |
| created_at          | datetime| 作成日時           |
| updated_at          | datetime| 更新日時           |

### Participants（参加者）

| Column              | Type    | Description        |
|---------------------|---------|--------------------|
| id                  | integer | 主キー             |
| user_id             | integer | ユーザーID         |
| event_id            | integer | イベントID         |
| status              | string  | 参加状況           |
| created_at          | datetime| 作成日時           |
| updated_at          | datetime| 更新日時           |

### Contributions（貢献）

| Column              | Type    | Description        |
|---------------------|---------|--------------------|
| id                  | integer | 主キー             |
| participant_id      | integer | 参加者ID           |
| description         | text    | 貢献の内容         |
| points              | integer | 貢献ポイント       |
| created_at          | datetime| 作成日時           |
| updated_at          | datetime| 更新日時           |

### Feedbacks（フィードバック）

| Column              | Type    | Description        |
|---------------------|---------|--------------------|
| id                  | integer | 主キー             |
| contribution_id     | integer | 貢献ID             |
| user_id             | integer | ユーザーID         |
| comment             | text    | コメント           |
| created_at          | datetime| 作成日時           |
| updated_at          | datetime| 更新日時           |


