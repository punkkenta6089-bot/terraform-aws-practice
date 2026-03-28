# 📘 Terraform AWS構築ポートフォリオ

## 📌 概要
Terraformを使用して、AWS上に基本的なインフラ構成を構築しました。

本ポートフォリオでは、以下の構成をコードで作成し、Terraformによるインフラ管理の基礎を学ぶことを目的としています。

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group
- EC2

---

## 🏗️ 構成

```text
VPC
└─ Public Subnet
   ├─ Internet Gateway
   ├─ Route Table
   ├─ Security Group
   └─ EC2
---

## 🚀 実施内容

- TerraformでAWS環境を構築
- `terraform plan` で差分確認
- `terraform apply` でリソース作成
- EC2インスタンス起動まで確認
- `terraform destroy` で作成したリソースを削除

---

## ⚠️ 苦労した点

### 1. AMI指定エラー
EC2作成時に、AMIの指定でエラーが発生しました。

**発生したエラー**
```text
InvalidAMIID.Malformed
