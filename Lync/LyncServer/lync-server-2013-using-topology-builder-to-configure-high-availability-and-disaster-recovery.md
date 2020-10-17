---
title: 使用拓扑生成器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21e240e8fd597f1fe8a2669df45d674be7a7bef1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508649"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>使用拓扑生成器在 Lync Server 2013 中配置高可用性和灾难恢复

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

在拓扑生成器中执行以下步骤，为持久聊天服务器配置高可用性和灾难恢复。

1.  添加镜像数据库和日志传送辅助数据库 SQL Server 存储。

2.  将持久聊天服务器服务属性编辑为：
    
    1.  为主数据库启用镜像。
    
    2.  添加主镜像 SQL Server 存储。
    
    3.  启用 SQL Server 日志传送数据库。
    
    4.  添加 SQL Server 日志传送辅助 SQL Server 存储。
    
    5.  为辅助数据库添加 SQL Server 存储镜像。
    
    6.  发布拓扑。

</div>

<span> </span>

</div>

</div>

</div>

