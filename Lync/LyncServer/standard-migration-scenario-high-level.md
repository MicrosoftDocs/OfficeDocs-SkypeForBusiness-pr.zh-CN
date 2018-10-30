---
title: 标准迁移方案 - 高级别
TOCTitle: 标准迁移方案 - 高级别
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205354(v=OCS.15)
ms:contentKeyID: 49314585
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 标准迁移方案 - 高级别

 

_**上一次修改主题：** 2013-01-30_

当将 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊迁移到 Lync Server 2013 和 持久聊天服务器时，请将下列项目用作起点。标准 Lync Server 2013 迁移路径如下所示：

  - 您的组织先前已部署了 Lync Server 2010 群聊或 Office Communications Server 2007 R2群聊，而您想部署 Lync Server 2013 和 持久聊天服务器。

  - 部署 Lync Server 2013，然后部署 持久聊天服务器池。

  - 准备和规则迁移您的 持久聊天聊天室，然后确定相应的时间关闭用于迁移的系统。

  - 运行用于迁移的 Windows PowerShell cmdlet（**Export-CsPersistentChatData** 和 **Import-CsPersistentChatData**）以将内容移动到 持久聊天服务器。

  - 验证该迁移是否成功。

  - 停用旧版部署。

  - 配置 持久聊天服务器，以便旧版客户端可连接到 Lync Server 2013 和 持久聊天服务器。这是必需的，因为部署新的客户端需要一些时间，且您想使用旧版客户端支持现有用户来尽快取得对其聊天室的访问权限。

  - 部署新的客户端，同时继续确保使用旧版 群聊（客户端）的工作者能够到达其聊天室。

