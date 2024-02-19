# API Docs

## ベースパス

`/api/v1/`

## 記事の取得

### 記事タイトルの一覧取得

#### Method

GET

#### URL

```
/articles?page={number}
```

#### StatusCode

##### 取得成功
200

#### Response

```
{
  "articles": [
    {
      "id": 0,
      "title": "title",
      "created_at": "2024/02/20 00:00:00"
    }
  ]
}
```

### 記事の詳細取得

#### Method

GET

#### URL

```
/article/{article_id}
```

#### StatusCode

##### 取得成功
200

##### 記事が見つからない場合
404

#### Response

```
{
  "article": {
    "id": 0,
    "title": "title",
    "body": "body",
    "created_at": "2024-02-20 00:00:00"
  }
}
```

## 記事の登録

### 登録者の認証

#### Method

POST

#### URL

```
/auth/signin
```

#### StatusCode

##### 認証成功
200

##### 認証失敗
401

#### Request

```
{
  "email": "hogehoge@fugafuga.com",
  "password": "example"
}
```

#### Response
なし

### 記事の登録

#### Method
POST

#### URL
```
/admin/article
```

#### StatusCode
##### 作成成功
201

#### RequestBody
```
{
  "title": "title",
  "body": "body"
}
```
