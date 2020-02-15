---
title: Lync Server 2013：配置 SQL Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28ab80634e7aeb4c3385c1fb60f0290a9cfe14ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="2f4b2-102">在 Lync Server 2013 中配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f4b2-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f4b2-103">_**上次修改的主题：** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="2f4b2-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="2f4b2-104">对于您部署的每个数据库，您可以对您的 Lync Server 2013 部署（可在数据库服务器上并置的所有数据库）使用单个 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="2f4b2-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="2f4b2-105">有关数据库并置的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="2f4b2-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2f4b2-106">此外，在完成拓扑生成器中设置数据库的步骤之前，必须安装和使用每个 SQL Server 实例，或使用 Windows PowerShell cmdlet 手动创建数据库。</span><span class="sxs-lookup"><span data-stu-id="2f4b2-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2f4b2-107">有关 SQL Server 可支持性的详细信息，请参阅[Lync Server 2013 的硬件设置](lync-server-2013-hardware-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="2f4b2-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="2f4b2-108">安装 Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="2f4b2-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="2f4b2-109">请参阅 Microsoft SQL Server 2012 文档，网址<https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>为：。</span><span class="sxs-lookup"><span data-stu-id="2f4b2-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

