---
title: Lync Windows Store 应用程序要求
TOCTitle: Lync Windows Store 应用程序要求
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ823129(v=OCS.15)
ms:contentKeyID: 52061029
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Windows Store 应用程序要求

 

_**上一次修改主题：** 2016-12-08_

具有 Lync Server 内部部署的组织必须满足以下要求才能支持 Lync Windows 应用商店应用。

> [!NOTE]  
> 对于 Lync Server 2010，请在所有服务器上运行 Lync Server 2010 的 2012 年 2 月累积更新（可在 <a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</a> 上获得）或更高版本。为使用户能够加入会议，请在服务器上运行 Lync Server 2010 的 2012 年 10 月累积更新（可在 <a href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</a> 上获得）。



  - 在服务器上启用自动发现、Lync Web App 和 Web 票证服务。

  - 在前端服务器或前端池上启用证书身份验证。（前端服务器或前端池上的用户注册过程通常称为注册机构。）有关详细信息，请参阅[创建注册器配置设置](lync-server-2013-create-registrar-configuration-settings.md)。

  - 发布用于自动发现服务的 DNS 别名 (CNAME) 资源记录。

  - 不再要求确保颁发给 Lync 服务器的证书的证书吊销列表 (CRL) 分发点 (CDP) 指向 HTTP 资源，而不是 LDAP 资源。但是，请确保客户端计算机至少安装了最新的 Windows 更新。

  - 在企业中配置 HTTP 代理以允许与 HTTP 流量相关的 Lync 服务器。如有必要，请添加自动发现、Lync Web App 和 Web 票证服务例外。

  - 在客户端上，安装 Windows 8.1 和 Lync Windows 应用商店应用 的最新版本以解决当使用多个域时通常会发生的问题（例如，当 SIP URI 是 <strong>userA@domainZ.com</strong>，但是边缘服务器是 **sip.domainX.com** 时）。

如果您的组织订阅了 Lync Online 或 Office 365，并且您正在使用自己的域名，您必须执行一些额外步骤来为您的网络设置 Lync 服务器自动发现。移动设备上的 Lync Windows 应用商店应用和 Lync 的网络配置要求相同。请按照 Office 365 wiki 文章“设置 Lync 移动设备”中的说明“设置您的网络”进行操作，网址为：[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)。

## 另请参阅

#### 概念

[部署 Lync Windows 应用商店应用](lync-server-2013-deploying-lync-windows-store-app.md)

