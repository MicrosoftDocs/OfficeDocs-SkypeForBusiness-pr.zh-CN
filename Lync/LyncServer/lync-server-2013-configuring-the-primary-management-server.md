---
title: Lync Server 2013：配置主管理服务器
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
ms.openlocfilehash: 68fc10ba0457b0ad29f6f3850c1d7056d27fd24d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="1ea3a-102">在 Lync Server 2013 中配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="1ea3a-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea3a-103">_**上次修改的主题：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="1ea3a-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="1ea3a-104">为了充分利用 Microsoft Lync Server 2013 中包含的新运行状况监视功能，管理员必须首先指定一台计算机作为你的主管理服务器;在该计算机上，必须安装 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="1ea3a-105">此外，还必须安装受支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="1ea3a-106">如果您使用的是 System Center Operations Manager 2012，则可以使用以下任一版本的 SQL Server 作为后端数据库：</span><span class="sxs-lookup"><span data-stu-id="1ea3a-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="1ea3a-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ea3a-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="1ea3a-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="1ea3a-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="1ea3a-109">如果您使用的是 System Center Operations Manager 2007 R2，建议您安装 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="1ea3a-110">您还可以使用 SQL Server 2008 R2 作为 System Center Operations Manager 2007 R2 的后端数据库。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="1ea3a-111">有关将 SQL Server 2008 R2 配置为与 System Center Operations Manager 2007 R2 一起使用的详细信息，请参阅本文档的附录1。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="1ea3a-112">当您安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，需要安装该产品的所有组件，包括：</span><span class="sxs-lookup"><span data-stu-id="1ea3a-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="1ea3a-113">操作数据库</span><span class="sxs-lookup"><span data-stu-id="1ea3a-113">Operational database</span></span>

  - <span data-ttu-id="1ea3a-114">服务器</span><span class="sxs-lookup"><span data-stu-id="1ea3a-114">Server</span></span>

  - <span data-ttu-id="1ea3a-115">控制台</span><span class="sxs-lookup"><span data-stu-id="1ea3a-115">Console</span></span>

  - <span data-ttu-id="1ea3a-116">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="1ea3a-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="1ea3a-117">Web 控制台</span><span class="sxs-lookup"><span data-stu-id="1ea3a-117">Web console</span></span>

  - <span data-ttu-id="1ea3a-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="1ea3a-118">Reporting</span></span>

  - <span data-ttu-id="1ea3a-119">数据仓库</span><span class="sxs-lookup"><span data-stu-id="1ea3a-119">Data warehouse</span></span>

<span data-ttu-id="1ea3a-120">本文档将不会详细讨论这些组件及其安装。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="1ea3a-121">有关 System Center Operations Manager 2007 R2 的详细信息，请参阅 Operations Manager 2007 R2 文档<https://go.microsoft.com/fwlink/p/?linkid=257526> （网址为）和 System Center operations manager <https://go.microsoft.com/fwlink/p/?linkid=257527>2012 文档（网址为）。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="1ea3a-122">如果要将 SQL Server 2005 或 SQL Server 2008 Service Pack 1 用作后端数据库，则应遵循这些说明。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="1ea3a-123">如果您使用的是 System Center Operations Manager 2012，则可以使用 SQL Server 2012 作为后端数据库。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="1ea3a-124">有关 SQL Server 2012 的详细信息，请参阅联机丛书 for SQL Server [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)2012。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="1ea3a-125">请注意，每个 Lync Server 部署中只能有一个主管理服务器。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="1ea3a-126">此外，虽然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您不能同时运行这两个应用程序，您必须选择其中一个。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="1ea3a-127">例如，如果您运行的是 System Center Operations Manager 2012，则所有 System Center agent 也必须运行 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="1ea3a-128">您不能有一些代理运行 System Center Operations Manager 2012 和其他运行 System Center Operations Manager 2007 R2 的代理。</span><span class="sxs-lookup"><span data-stu-id="1ea3a-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

