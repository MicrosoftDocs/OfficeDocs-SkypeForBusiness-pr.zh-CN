---
title: Lync Server 2013：备份存档和监视数据库
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
ms.openlocfilehash: 4092ddc3c86496053cc0ebbb367188490096de4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="01521-102">在 Lync Server 2013 中备份存档和监视数据库</span><span class="sxs-lookup"><span data-stu-id="01521-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01521-103">_**主题上次修改时间：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="01521-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="01521-104">如果你已部署存档或监视，你需要根据你的组织的 SQL Server 备份策略备份这些数据库。</span><span class="sxs-lookup"><span data-stu-id="01521-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01521-105">备份中央管理存储时，将备份存档和监视的设置。</span><span class="sxs-lookup"><span data-stu-id="01521-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="01521-106">有关详细信息，请参阅<A href="lync-server-2013-backing-up-core-data-and-settings.md">在 Lync Server 2013 中备份核心数据和设置</A>。</span><span class="sxs-lookup"><span data-stu-id="01521-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="01521-107">对于存档和监视，可以使用 sql server 工具（如 SQL Server Management Studio）执行手动备份，也可以使用 SQL Server 管理工具安排定期自动备份。</span><span class="sxs-lookup"><span data-stu-id="01521-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

