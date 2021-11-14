# 実践 AWSデータサイエンス ハンズオンワークショップ

[Data Science on AWS本家のワークショップコンテンツ](https://github.com/data-science-on-aws/workshop)の日本語翻訳版です。

### 本書の概要

![outline](./img/outline.png)

## クイックスタート ワークショップ（3-4時間）

[00_quickstart](./00_quickstart)は、500ページを超える「[実践 AWSデータサイエンス](https://www.oreilly.co.jp/books/9784873119687/)」のコンセプトを、3-4時間程度という超特急で体感できるハンズオンコンテンツです。

![workshop_paths1](./img/workshop_paths1.png)

このワークショップでは、Amazon SageMakerを使って自然言語処理（NLP）のワークロードを効率化する、エンドツーエンドのAI/MLパイプラインを構築します。
言語表現の獲得のためには最先端の[BERT](https://arxiv.org/abs/1810.04805)モデルを使用して、商品レビューの星評価（1〜5）を予測するテキスト分類器をトレーニングします。
BERTベースのNLPテキスト分類器を構築するために、[Amazon Customer Reviews Dataset](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)という、商品のレビュー文と星評価（1～5）を含むデータセットを使用します。

### クイックスタート ワークショップで学べること

このハンズオンワークショップを体験することで、次の内容を学ぶことができます。

- Amazon AthenaとParquetデータフォーマットを使用したS3へのデータの取り込み
- SageMakerノートブック上でのPandas、matplotlibによるデータの可視化
- SageMaker Clarifyを使用した統計的データバイアスの検出
- Scikit-Learn および SageMaker Processing Job を使用した、生データセットに対する特徴量エンジニアリングの実行
- SageMaker Feature Store を使用した特徴量の保存と共有
- TensorFlow、Keras、およびSageMakerのトレーニングジョブを使用したカスタムBERTモデルのトレーニングと評価
- SageMaker Processing Job を使用したモデルの評価
- Amazon SageMaker ML Lineage Tracking を使用したモデルアーティファクトの追跡
- SageMaker Clarify を使用したモデルバイアスおよび説明可能性分析の実行
- SageMaker Model Registry を使用したモデルの登録とバージョン管理
- SageMaker Hosting および SageMaker Endpoint を使用した REST エンドポイントへのモデルのデプロイ
- SageMaker Pipelines を使用したエンドツーエンドのモデルパイプライン構築による ML ワークフローステップの自動化

### 前提条件

**このワークショップはバージニア北部（us-east-1）リージョンで実施してください。**
ワークショップ用のカスタマーレビューデータセットが、us-east-1にあるAmazon S3バケットに置かれています。
他の東京リージョンなどで作業すると、Athenaクエリなど実行する際に、レイテンシーが非常に大きくなってしまいます。

また、このワークショップはAmazon SageMaker Studioという、機械学習の統合開発環境で実施することを前提としています。
こちらの[ドキュメント](https://docs.aws.amazon.com/sagemaker/latest/dg/onboard-quick-start.html)を参考に、SageMaker Studioの環境を構築してください。

SageMaker Studioの環境構築時に作成されるSageMaker実行ロール（`AmazonSageMaker-ExecutionRole-***`）にはあらかじめ `AmazonSageMakerFullAccess` のポリシーがアタッチされていますが、さらに `AWSGlueConsoleFullAccess` といったポリシーも追加する必要があることにもご注意ください。ワークショップ中に AWS Glue を用いる箇所があります。（実際の運用時には FullAccess ではなく、最小権限の原則に則り、必要なポリシーのみをアタッチするようにしてください。）