# k3s

#### 介绍
{**以下是 Gitee 平台说明，您可以替换此简介**
Gitee 是 OSCHINA 推出的基于 Git 的代码托管平台（同时支持 SVN）。专为开发者提供稳定、高效、安全的云端软件开发协作平台
无论是个人、团队、或是企业，都能够用 Gitee 实现代码托管、项目管理、协作开发。企业项目请看 [https://gitee.com/enterprises](https://gitee.com/enterprises)}

#### 软件架构
软件架构说明


#### 安装教程
 **步骤 1：分发资源到目标节点** 

解压离线包至对应目录：
```
tar xzvf k3s-offline-bundle.tar.gz -C /  
cd /var/lib/rancher/k3s/agent/images
unzip rancher_klipper-helm_v0.9.4-build20250113.tar.zip
unzip rancher_mirrored-library-traefik_3.3.2.tar.zip
```

 **步骤 2：安装 K3s Server** 
```
INSTALL_K3S_SKIP_DOWNLOAD=true \  
INSTALL_K3S_EXEC="server --docker --tls-san <节点IP>" \  
./install.sh  
```
关键参数说明：
- --docker：若使用 Docker 运行时（默认 Containerd）
- --tls-san：指定 TLS 证书的备用名称（如节点 IP 或域名）

 **步骤 3：加入 Agent 节点** 
```
INSTALL_K3S_SKIP_DOWNLOAD=true \  
K3S_URL=https://<Server_IP>:6443 \  
K3S_TOKEN=$(cat /var/lib/rancher/k3s/server/node-token) \  
./install.sh  
```

#### 使用说明

1.  xxxx
2.  xxxx
3.  xxxx

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
