# 📘 Terraform AWS構築ポートフォリオ

## 📌 概要
Terraformを使用して、AWS上に基本的なインフラ構成を構築しました。

本ポートフォリオでは、以下の構成をコードで作成し、Terraformによるインフラ管理（IaC）の基礎理解を目的としています。

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group
- EC2

---

## 🏗️ 構成

VPC  
└─ Public Subnet  
　├─ Internet Gateway  
　├─ Route Table  
　├─ Security Group  
　└─ EC2  

---

## 🚀 実施内容

- TerraformでAWS環境を構築
- terraform plan による差分確認
- terraform apply によるリソース作成
- EC2インスタンス起動まで確認
- terraform destroy による環境削除まで実施

---

## ⚠️ 苦労した点

### 1. AMI指定エラー

EC2作成時に、AMIの指定でエラーが発生しました。

■ 発生したエラー  
InvalidAMIID.Malformed  

■ 原因  
AMI IDの指定方法に問題があったため  

■ 対応  
固定のAMI ID指定ではなく、SSM Parameter Storeから最新AMIを取得する方法に変更して解決  

---

### 2. Terraformコマンドが動かなかった

Terraform実行時に、コマンドが認識されない問題が発生しました。

■ 発生したエラー  
terraform は認識されていません  

■ 原因  
terraform.exe があるフォルダ以外で実行していたため  

■ 対応  
実行ディレクトリを見直し、terraform.exe があるフォルダで実行して解決  

---

## 📚 学んだこと

- TerraformはコードでAWSリソースを管理できる
- plan → apply → destroy の流れが重要
- エラーは原因を切り分けることで解決できる
- 一度削除してもコードがあれば再構築できる

---

## 🎯 今後の課題

- EC2へのSSH接続
- Webサーバーの構築（Apache / Nginx）
- Terraformファイルの分割（vpc.tf / ec2.tf など）
- private subnet + NAT Gateway構成の理解

---

## 🛠️ 使用技術

- Terraform
- AWS
  - VPC
  - Subnet
  - Internet Gateway
  - Route Table
  - Security Group
  - EC2

---

## 🙌 補足
- AWS学習の一環として作成したポートフォリオです。  
今後も継続的に改善し、構築できる範囲を広げていきます。

---

## 🌐 Webサーバー動作確認

- EC2上にApacheを構築し、ブラウザからアクセス可能な状態を構築しました。
- Hello Terraform!!
- Terraformの user_data を使用し、EC2起動時にWebサーバーのインストール・起動・HTML配置まで自動化しています。
- ※現在はコスト削減のため、リソースは削除済みです。
