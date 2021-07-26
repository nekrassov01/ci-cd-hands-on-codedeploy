# CodeDeployの設定

![](images/pipeline_codedeploy_focus.png)

CodePipelineからのデプロイ先を作成するため、先にCodeDeployの設定を行っていきます。

CodeDeployではアプリケーションとデプロイグループを作成していきます。

簡単に説明すると、アプリケーションはデプロイの設定をまとめるものであり、デプロイグループはデプロイ先のインスタンスの集合とデプロイの設定をまとめたものです。

CodeDeployのアプリケーションの画面からアプリケーションの作成をクリックします。

![](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2018/10/d6036a2cd7ed241bfd1cf3db1c349982.png)

表示されたダイアログに以下のような入力項目を入力します。

| 入力項目                           | 値               |
| ---------------------------------- | ---------------- |
| アプリケーション名                 | `hands-on-app`   |
| コンピューティングプラットフォーム | EC2/オンプレミス |

アプリケーションの作成をクリックすると、CodeDeployのアプリケーションが作成され、当該アプリケーションの詳細画面が表示されます。

![](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2018/10/801c72268e6b9258abcee851dd3ca369.png)

この画面からさらに「デプロイグループの作成」をクリックし、このアプリケーションにデプロイグループを作成します。

| 入力項目                         | 値                                                     |
| -------------------------------- | ------------------------------------------------------ |
| デプロイグループ名               | `hands-on-deploy-group`                                |
| サービスロール                   | `hands-on-environment-CodeDeploy-ServiceRole`          |
| デプロイタイプ                   | `インプレース`                                           |
| Amazon EC2 Auto Scalingグループ | ✔                                                      |
| Auto Scalingグループ            | `hands-on-environment-EC2AutoScalingGroup-XXXXXXX`     |
| デプロイ設定                     | `CodeDeployDefault.HalfAtOnce`                           |
| ロードバランシングを有効にする   | ✔                                                      |
|                                  | Application Load BalancerまたはNetwork Load Balancer |
| Choose a load balancer           | `hands-on-environment-TargetGroup`                     |


