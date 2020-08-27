# CDK Pipelines手順

## 前提条件
- GitHubアカウント、リポジトリ
- 1つ以上のAWSアカウント
- AWS CDKのバージョン1.51.0以降
- AWS CLIインストール

## 事前準備

#### 1.assume role
1. AWS CLIをインストールします。
2. 対象ファイル(`aws-assume-role.sh`、`config`、`credentials`)を`USERPROFILE/.aws`直下に配置し、configファイルの`mfa_serial`を自分のユーザに書き換えてください。
3. Git Bash等で`USERPROFILE/.aws`フォルダを開き、assume roleコマンドを入力します。
    ```
    aws-assume-role.sh -p service-operation
    ```
4. 対象アカウントのMFAコードを入力します。
5. `set complete`と表示されたら成功です。

#### 2.GitHub個人用アクセストークンの登録
Githubトークンの取得
https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token

AWSシークレットマネージャーへの登録
https://docs.aws.amazon.com/secretsmanager/latest/userguide/tutorials_basic.html

## 実施手順
下記URLのUse case application～
https://aws.amazon.com/jp/blogs/developer/cdk-pipelines-continuous-delivery-for-aws-cdk-applications/

##参考URL
- CDK Pipelines発表記事
https://aws.amazon.com/jp/about-aws/whats-new/2020/07/announcing-cdk-pipelines-preview/

- AWS CDK Pipelinesドキュメント
https://docs.aws.amazon.com/cdk/api/latest/docs/pipelines-readme.html

- CDK Pipelines解説記事
https://aws-blog.de/2020/07/the-cdk-pipeline-construct.html