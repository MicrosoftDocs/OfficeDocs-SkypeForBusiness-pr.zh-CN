---
title: Lync Server 2013：配置主管理服务器
description: Lync Server 2013：配置主管理服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43f986f4f03e96cafa27dfdd302bb98a00d8b2ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544158"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="8740e-103">在 Lync Server 2013 中配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="8740e-103">Configuring the primary management server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8740e-104">_**上次修改的主题：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="8740e-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="8740e-105">为了充分利用 Microsoft Lync Server 2013 中包含的新运行状况监视功能，管理员必须首先指定一台计算机作为你的主管理服务器;在该计算机上，必须安装 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="8740e-105">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="8740e-106">此外，还必须安装受支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8740e-106">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="8740e-107">如果您使用的是 System Center Operations Manager 2012，则可以使用以下任一版本的 SQL Server 作为后端数据库：</span><span class="sxs-lookup"><span data-stu-id="8740e-107">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="8740e-108">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="8740e-108">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="8740e-109">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="8740e-109">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="8740e-110">如果您使用的是 System Center Operations Manager 2007 R2，建议您安装 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。</span><span class="sxs-lookup"><span data-stu-id="8740e-110">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="8740e-111">您还可以使用 SQL Server 2008 R2 作为 System Center Operations Manager 2007 R2 的后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8740e-111">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="8740e-112">有关将 SQL Server 2008 R2 配置为与 System Center Operations Manager 2007 R2 一起使用的详细信息，请参阅本文档的附录1。</span><span class="sxs-lookup"><span data-stu-id="8740e-112">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="8740e-113">当您安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，需要安装该产品的所有组件，包括：</span><span class="sxs-lookup"><span data-stu-id="8740e-113">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="8740e-114">操作数据库</span><span class="sxs-lookup"><span data-stu-id="8740e-114">Operational database</span></span>

  - <span data-ttu-id="8740e-115">服务器</span><span class="sxs-lookup"><span data-stu-id="8740e-115">Server</span></span>

  - <span data-ttu-id="8740e-116">控制台</span><span class="sxs-lookup"><span data-stu-id="8740e-116">Console</span></span>

  - <span data-ttu-id="8740e-117">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="8740e-117">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="8740e-118">Web 控制台</span><span class="sxs-lookup"><span data-stu-id="8740e-118">Web console</span></span>

  - <span data-ttu-id="8740e-119">Reporting</span><span class="sxs-lookup"><span data-stu-id="8740e-119">Reporting</span></span>

  - <span data-ttu-id="8740e-120">数据仓库</span><span class="sxs-lookup"><span data-stu-id="8740e-120">Data warehouse</span></span>

<span data-ttu-id="8740e-121">本文档将不会详细讨论这些组件及其安装。</span><span class="sxs-lookup"><span data-stu-id="8740e-121">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="8740e-122">有关 System Center Operations Manager 2007 R2 的详细信息，请参阅 Operations Manager 2007 R2 文档（网址为） <https://go.microsoft.com/fwlink/p/?linkid=257526> 和 System Center Operations manager 2012 文档（网址为） <https://go.microsoft.com/fwlink/p/?linkid=257527> 。</span><span class="sxs-lookup"><span data-stu-id="8740e-122">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="8740e-123">如果要将 SQL Server 2005 或 SQL Server 2008 Service Pack 1 用作后端数据库，则应遵循这些说明。</span><span class="sxs-lookup"><span data-stu-id="8740e-123">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="8740e-124">如果您使用的是 System Center Operations Manager 2012，则可以使用 SQL Server 2012 作为后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8740e-124">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="8740e-125">有关 SQL Server 2012 的详细信息，请参阅联机丛书 for SQL Server 2012 [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) 。</span><span class="sxs-lookup"><span data-stu-id="8740e-125">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="8740e-126">请注意，每个 Lync Server 部署中只能有一个主管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8740e-126">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="8740e-127">此外，虽然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您不能同时运行这两个应用程序，您必须选择其中一个。</span><span class="sxs-lookup"><span data-stu-id="8740e-127">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="8740e-128">例如，如果您运行的是 System Center Operations Manager 2012，则所有 System Center agent 也必须运行 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="8740e-128">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="8740e-129">您不能有一些代理运行 System Center Operations Manager 2012 和其他运行 System Center Operations Manager 2007 R2 的代理。</span><span class="sxs-lookup"><span data-stu-id="8740e-129">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

