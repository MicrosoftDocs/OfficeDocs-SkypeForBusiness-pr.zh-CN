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
ms.openlocfilehash: 56f74465ecba83ec2d4f857a504952a1ed271fb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9229d-102">使用拓扑生成器在 Lync Server 2013 中配置高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="9229d-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9229d-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9229d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9229d-104">在拓扑生成器中执行以下步骤，为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="9229d-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="9229d-105">添加镜像数据库和日志传送辅助数据库 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="9229d-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="9229d-106">将持久聊天服务器服务属性编辑为：</span><span class="sxs-lookup"><span data-stu-id="9229d-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="9229d-107">为主数据库启用镜像。</span><span class="sxs-lookup"><span data-stu-id="9229d-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="9229d-108">添加主镜像 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="9229d-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="9229d-109">启用 SQL Server 日志传送数据库。</span><span class="sxs-lookup"><span data-stu-id="9229d-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="9229d-110">添加 SQL Server 日志传送辅助 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="9229d-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="9229d-111">为辅助数据库添加 SQL Server 存储镜像。</span><span class="sxs-lookup"><span data-stu-id="9229d-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="9229d-112">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="9229d-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

