# データベース設計

## 最低限必要

### products
スキンケア製品に関する情報
| フィールド | 型 | 説明 |
| --- | --- | --- |
| product_id | Int (プライマリーキー) | 製品の一意の識別子 |
| product_name | String | 製品名 |
| product_description | String | 製品説明 |
| product_price | Decimal | 製品価格 |

### ingredients
配合成分に関する情報
| フィールド | 型 | 説明 |
| --- | --- | --- |
| ingredients_id | Int (プライマリーキー) | 成分の一意の識別子 |
| ingredients_name | String | 成分名 |
| ingredients_description | String | 成分説明 |

### product_ingredients
製品と配合成分の対応
| フィールド | 型 | 説明 |
| --- | --- | --- |
| product_id | Int (フォーリンキー) | 製品の識別子（productsテーブルとリンク） |
| ingredient_id | Int (フォーリンキー) | 成分の識別子（ingredientsテーブルとリンク） |

### benefits
効能に関する情報
| フィールド | 型 | 説明 |
| --- | --- | --- |
| benefit_id | Int (プライマリーキー) | 効能の一意の識別子 |
| benefit_name | String | 効能（例："保湿", "抗酸化"など） |

### ingredient_benefits
成分と効能の対応
| フィールド | 型 | 説明 |
| --- | --- | --- |
| ingredient_id | Int (フォーリンキー) | 成分の識別子（ingredientsテーブルとリンク） |
| benefit_id | Int (フォーリンキー) | 効能の識別子（benefitsテーブルとリンク） |

### user
ユーザーに関する情報
| フィールド | 型 | 説明 |
| --- | --- | --- |
| user_id | Int (プライマリーキー) | ユーザーの一意の識別子 |
| user_name | String | ユーザー名 |
| user_birth_date | Date | ユーザーの生年月日 |
| user_skin_vector | Vector | ユーザーの肌特性を表すベクトル |
| user_concerns_vector | Vector | スキンケアに関する悩みや嗜好を表すベクトル |

---

## 追加機能

### product_reviews
製品レビューに関する情報
| フィールド | 型 | 説明 |
| --- | --- | --- |
| review_id | Int (プライマリーキー) | レビューの一意の識別子 |
| product_id | Int (フォーリンキー) | レビューされた製品の識別子（productテーブルとリンク） |
| user_id | Int (フォーリンキー) | レビューを投稿したユーザーの識別子（userテーブルとリンク） |
| review_rating | Int | ユーザーによる評価（例：1-5のスケール） |
| review_content | String | ユーザーによるレビューテキスト |
