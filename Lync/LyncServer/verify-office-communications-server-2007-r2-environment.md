---
title: 验证 Office Communications Server 2007 R2 环境
TOCTitle: 验证 Office Communications Server 2007 R2 环境
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49888641
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证 Office Communications Server 2007 R2 环境

 

_**上一次修改主题：** 2012-10-16_

在将 Lync Server 2013 与 Office Communications Server 2007 R2 以共存方式部署之前，您需要确认已配置并启动 Office Communications Server 2007 R2 服务。

**使用 Office Communications Server 2007 R2 管理工具确认池是否已启动**

1.  打开 Office Communications Server 2007 R2 管理工具。

2.  展开**林**节点，再展开 **Standard Edition Server** 或**企业版池**节点，然后展开池或服务器名称。

3.  确保服务在 Standard Edition Server 或企业版池上运行。
    
    ![Office Communications Server 2007 R2 管理控制台](images/JJ204914.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理控制台")

**查看为 Office Communications Server 2007 R2 配置的用户**

1.  打开 Office Communications Server 2007 R2 管理工具。

2.  展开 **林**节点，再展开 **Standard Edition Server** 或 **企业版池**节点，然后展开池或服务器名称。

3.  单击“用户”。

4.  验证 Office Communications Server 2007 R2 用户列表。
    
    ![OCS 管理池中的用户列表](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理池中的用户列表")

**验证旧版 XMPP 联盟伙伴配置**

1.  从旧版 XMPP 服务器中，导航到“管理工具\\服务”小程序。

2.  确认 Office Communications Server XMPP 网关服务已启动。
    
    ![Office Communications Server XMPP 网关服务](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 网关服务")

