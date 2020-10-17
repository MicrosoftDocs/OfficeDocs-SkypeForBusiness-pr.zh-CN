---
title: Lync Server 2013：备份存档和监控数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08eea156d1b12f607270ea3b6d7472519128e472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523169"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="34e38-102">在 Lync Server 2013 中备份存档和监控数据库</span><span class="sxs-lookup"><span data-stu-id="34e38-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e38-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="34e38-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="34e38-104">如果部署了“存档”或“监控”，则需要根据组织的 SQL Server 备份策略对这些数据库进行备份。</span><span class="sxs-lookup"><span data-stu-id="34e38-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34e38-105">备份中央管理存储时，将备份存档和监视的设置。</span><span class="sxs-lookup"><span data-stu-id="34e38-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="34e38-106">有关详细信息，请参阅 <A href="lync-server-2013-backing-up-core-data-and-settings.md">在 Lync Server 2013 中备份核心数据和设置</A>。</span><span class="sxs-lookup"><span data-stu-id="34e38-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="34e38-107">对于“存档”和“监控”，可以使用 SQL Server 工具（如 SQL Server Management Studio）执行手动备份，也可以使用 SQL Server 管理工具安排定期进行自动备份。</span><span class="sxs-lookup"><span data-stu-id="34e38-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

