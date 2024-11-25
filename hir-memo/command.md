```
# AWSアカウントIDの抽出
AWS_ACCOUNT_ID=$(aws sts get-caller-identity --query 'Account' --output text)
```

```
# ECR認証
aws ecr --region ap-northeast-1 get-login-password | docker login --username AWS \
--password-stdin https://${AWS_ACCOUNT_ID}.dkr.ecr.ap-northeast-1.amazonaws.com/[リポジトリ名]
```