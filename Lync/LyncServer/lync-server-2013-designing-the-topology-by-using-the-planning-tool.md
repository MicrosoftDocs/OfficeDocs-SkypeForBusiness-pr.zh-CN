---
title: Lync Server 2013：使用计划工具设计拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="17428-102">使用规划工具设计 Lync Server 2013 的拓扑</span><span class="sxs-lookup"><span data-stu-id="17428-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17428-103">_**主题上次修改时间：** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="17428-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="17428-104">Microsoft Lync Server 2013、计划工具是一个向导驱动的工具，该工具会询问有关你正在设计的 Lync Server 2013 拓扑的问题。</span><span class="sxs-lookup"><span data-stu-id="17428-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="17428-105">规划工具使用所提供的信息和拓扑设计和容量的首选做法，根据提供的答案演示推荐的拓扑。</span><span class="sxs-lookup"><span data-stu-id="17428-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="17428-106">您可以从 Microsoft 下载中心下载计划工具（[http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)）。</span><span class="sxs-lookup"><span data-stu-id="17428-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="17428-107">最终，规划工具的目标是减轻设计完整 Lync Server 2013 拓扑的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="17428-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="17428-108">如果可以通过 Internet 连接来连接到 Microsoft TechNet 网站，该工具还会提供对工具内规划文档和部署文档的上下文引用。</span><span class="sxs-lookup"><span data-stu-id="17428-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="17428-109">使用基础结构的 TCP/IP 地址和完全限定的域名（Fqdn）自定义拓扑后，规划工具会提供一系列涵盖域名系统（DNS）命名、防火墙规则、证书等的报告。</span><span class="sxs-lookup"><span data-stu-id="17428-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="17428-110">规划工具还提供了以两种格式导出信息的功能：</span><span class="sxs-lookup"><span data-stu-id="17428-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="17428-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="17428-111">Microsoft Excel</span></span>

  - <span data-ttu-id="17428-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="17428-112">Microsoft Visio</span></span>

<span data-ttu-id="17428-113">以下主题介绍并详细介绍规划工具。</span><span class="sxs-lookup"><span data-stu-id="17428-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="17428-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="17428-114">In This Section</span></span>

  - [<span data-ttu-id="17428-115">在 Lync Server 2013 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="17428-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="17428-116">在 Lync Server 2013 中安装可选软件</span><span class="sxs-lookup"><span data-stu-id="17428-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="17428-117">在 Lync Server 2013 中导航规划工具</span><span class="sxs-lookup"><span data-stu-id="17428-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="17428-118">创建 Lync Server 2013 的初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="17428-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="17428-119">在 Lync Server 2013 中查看管理员报告</span><span class="sxs-lookup"><span data-stu-id="17428-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17428-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17428-120">See Also</span></span>


[<span data-ttu-id="17428-121">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17428-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="17428-122">在 Lync Server 2013 中规划前端服务器、即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="17428-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

