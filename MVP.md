# MVP
## コンセプト
ユーザーに寄り添った透明性のあるスキンケア製品のレコメンドエンジン

## 機能

- データベース
  - スキンケア製品とその配合成分のデータベース
  - 配合成分とその効能に関するデータベース
    - 効能はベクトル化して保存しておく

- ビュー
  - ユーザープロファイル（属性、肌質、肌トラブルなど）の入力フォーム
  - 悩みや不安などの細かいニーズをヒアリングする機能
  - 抽出した製品をランキング表示＋それぞれに対する推薦根拠を表示する

- ビジネスロジック
  - 収集した情報を要素分解＋定量化する
  - 定量化されたデータをキーにしてFunction callingで製品を抽出＋ランク付け
  - 抽出した製品に対してLLMで根拠を生成する
