---
title: 还原 Enterprise Edition 成员服务器
TOCTitle: 还原 Enterprise Edition 成员服务器
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202191(v=OCS.15)
ms:contentKeyID: 52061144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原 Enterprise Edition 成员服务器

 

_**上一次修改主题：** 2013-02-18_

如果运行下列服务器角色之一的服务器出现故障，可按照本主题中的过程还原该服务器。如果多台服务器出现故障，可针对每台服务器单独执行该过程。

  - 前端服务器

  - 中介服务器

  - 控制器

  - 持久聊天服务器

  - 边缘服务器

> [!TIP]
> 建议在开始还原之前制作系统的映像副本。在还原过程中出现问题时可将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。


## 还原成员服务器

1.  首先准备与出现故障的服务器具有相同完全限定域名 (FQDN) 的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。
    
    > [!NOTE]  
	> 按照您组织的服务器部署过程来执行该步骤。
    


2.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到要还原的服务器。

3.  浏览到 Lync Server 安装文件夹或介质，并启动位于 \\setup\\amd64\\Setup.exe 中的 Lync Server 部署向导。

4.  按照部署向导执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”以安装本地配置文件。
    
    2.  运行“步骤 2: 安装或删除 Lync Server 组件”以安装 Lync Server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”以分配证书。
    
    4.  运行“步骤 4: 启动服务”以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅适用于您要还原的服务器角色的部署文档。

