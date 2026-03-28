# 📘 Terraform AWS構築ポートフォリオ

## 📌 概要
Terraformを使用してAWS上に以下の構成を構築しました。

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group
- EC2

インフラをコードで管理する（IaC）の基礎理解を目的としています。

---

## 🏗️ 構成

VPC
└─ Public Subnet
├─ IGW
├─ Route Table
├─ Security Group
└─ EC2


---

## 🚀 実施内容
- TerraformでAWS環境を構築
- `terraform apply` によりリソース作成
- EC2インスタンス起動まで確認
- `terraform destroy` により全リソース削除まで実施

---

## ⚠️ 苦労した点

### ■ AMIエラー
EC2作成時に以下のエラーが発生

InvalidAMIID.Malformed

**原因**
- AMI IDの指定が不適切

**対応**
- SSM Parameter Storeから最新AMIを取得する方式に変更し解決

---

### ■ Terraformコマンドが動かない

terraform は認識されていません


**原因**
- PATHが通っていなかった

**対応**
- terraform.exeがあるフォルダで実行して解決

---

## 📚 学んだこと
- Terraformはstateファイルでインフラを管理する
- `plan → apply → destroy` の流れが重要
- エラーは原因を切り分ければ解決できる
- AWSリソースはコードで再現可能

---

## 🎯 今後の課題
- EC2へのSSH接続
- Webサーバー構築（Apache / Nginx）
- private subnet + NAT Gateway
- Terraformの変数化（variables）
