---
title: 在 Lync Server 2013 中添加或删除前端服务器
TOCTitle: 在 Lync Server 2013 中添加或删除前端服务器
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205153(v=OCS.15)
ms:contentKeyID: 49313910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中添加或删除前端服务器

 

_**上一次修改主题：** 2016-01-21_

将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。为了防止对用户的服务造成任何中断，在添加或删除前端服务器时，请使用以下过程。

## 添加或删除前端服务器

1.  如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：
    
        Stop -CsWindowsServices -Graceful

2.  当所删除的服务器没有当前会话时，请停止这些服务器上的 Lync Server 服务。

3.  打开拓扑生成器，然后添加或删除所需的服务器。

4.  发布拓扑。

5.  如果池从具有两个前端服务器变为具有两个以上的服务器，或者从两个以上的服务器变为恰好有两个，则需要键入以下 cmdlet：
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果池具有三个或更多的服务器，则在键入此 cmdlet 时，其中必须至少有三个服务器正在运行。

6.  重新启动池中的所有前端服务器，一次启动一个。

