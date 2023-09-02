# aws-rocketchat-cfn-template
CloudFormation template to build RocketChat on AWS

# README
AWS上でRocketChatを構築するためのCloudformation Templateです。

# 構築手順
テンプレート内のACMのARNを指定して、Cloudformationのコンソールにアップデートし、必要事項を記入してください。


## 前提
今回ドメイン(example.com)はCloudflare上で管理しており、そのドメイン名のパブリックホストゾーンをRoute53に設定済み。
また、事前にACMにて、利用予定のサブドメイン(xxx.example.com)でパブリック証明書を発行し、DNS検証としてCloudflareのDNSにNSを設定済み。

## 作成リソース
* VPC
  1VPC、2PublicSubnet、2PrivateSubnet、それぞれのRouteTable、1NATGWを内包
* ALB
  ACMを利用してHTTPS化
* EC2
  1台にスクリプトを指定してインストールを行う

## 構築後
DNSの伝播が終われば、ALB経由でアクセス可能。
その後はRocketChatの手順に従って設定を行う。

