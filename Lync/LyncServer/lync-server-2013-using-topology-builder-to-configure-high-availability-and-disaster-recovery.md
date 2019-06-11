---
title: 使用拓扑生成器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="f1a21-102">在 Lync Server 2013 中使用拓扑生成器配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="f1a21-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1a21-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f1a21-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f1a21-104">在拓扑生成器中执行以下步骤, 以配置持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="f1a21-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="f1a21-105">添加镜像数据库和日志传送辅助数据库 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="f1a21-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="f1a21-106">将持久聊天服务器服务属性编辑为:</span><span class="sxs-lookup"><span data-stu-id="f1a21-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="f1a21-107">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="f1a21-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="f1a21-108">添加主镜像 SQL Server 应用商店。</span><span class="sxs-lookup"><span data-stu-id="f1a21-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="f1a21-109">启用 SQL Server 日志传送数据库。</span><span class="sxs-lookup"><span data-stu-id="f1a21-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="f1a21-110">添加 SQL Server 日志传送辅助 SQL Server 应用商店。</span><span class="sxs-lookup"><span data-stu-id="f1a21-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="f1a21-111">为辅助数据库添加 SQL Server 应用商店镜像。</span><span class="sxs-lookup"><span data-stu-id="f1a21-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="f1a21-112">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="f1a21-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

