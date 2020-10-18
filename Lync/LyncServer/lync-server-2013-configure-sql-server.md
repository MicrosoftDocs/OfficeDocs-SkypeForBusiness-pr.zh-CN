---
title: Lync Server 2013：配置 SQL Server
description: Lync Server 2013：配置 SQL Server。
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
ms.openlocfilehash: 2330dc4548e5157b7f29567551df4c89ee15998b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576708"
---
# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="0624e-103">在 Lync Server 2013 中配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="0624e-103">Configure SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0624e-104">_**上次修改的主题：** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="0624e-104">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="0624e-105">对于您部署的每个数据库，您可以对您的 Lync Server 2013 部署（可在数据库服务器上并置的所有数据库）使用单个 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="0624e-105">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="0624e-106">有关数据库并置的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="0624e-106">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0624e-107">此外，在完成拓扑生成器中设置数据库的步骤之前，必须安装和使用每个 SQL Server 实例，或使用 Windows PowerShell cmdlet 手动创建数据库。</span><span class="sxs-lookup"><span data-stu-id="0624e-107">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0624e-108">有关 SQL Server 可支持性的详细信息，请参阅 [Lync Server 2013 的硬件设置](lync-server-2013-hardware-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="0624e-108">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="0624e-109">安装 Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0624e-109">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="0624e-110">请参阅 Microsoft SQL Server 2012 文档，网址为： <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="0624e-110">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

