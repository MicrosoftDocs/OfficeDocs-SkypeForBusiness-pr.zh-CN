---
title: 验证 Office Communications Server 2007 R2 环境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb67868c9f7eddfe2b11b4238c5fdd1bd14d8e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="4cfad-102">验证 Office Communications Server 2007 R2 环境</span><span class="sxs-lookup"><span data-stu-id="4cfad-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cfad-103">_**主题上次修改时间：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4cfad-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4cfad-104">在使用 Office 通信服务器 2007 R2 在共存状态中部署 Lync Server 2013 之前，需要验证 Office 通信服务器是否已配置和启动 2007 R2 服务。</span><span class="sxs-lookup"><span data-stu-id="4cfad-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="4cfad-105">**验证池是否已使用 Office 通信服务器 2007 R2 管理工具启动**</span><span class="sxs-lookup"><span data-stu-id="4cfad-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="4cfad-106">打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="4cfad-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4cfad-107">展开 "**林**" 节点，展开 "**标准版服务器**" 或 "**企业版池**" 节点，然后展开 "池" 或 "服务器名称"。</span><span class="sxs-lookup"><span data-stu-id="4cfad-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4cfad-108">确保服务在标准版服务器或企业版池上运行。</span><span class="sxs-lookup"><span data-stu-id="4cfad-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="4cfad-109">![Office 通信服务器 2007 R2 管理控制台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通信服务器 2007 R2 管理控制台")</span><span class="sxs-lookup"><span data-stu-id="4cfad-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="4cfad-110">**查看针对 Office 通信服务器 2007 R2 配置的用户**</span><span class="sxs-lookup"><span data-stu-id="4cfad-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="4cfad-111">打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="4cfad-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4cfad-112">展开 "**林**" 节点，展开 "**标准版服务器**" 或 "**企业版池**" 节点，然后展开 "池" 或 "服务器名称"。</span><span class="sxs-lookup"><span data-stu-id="4cfad-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4cfad-113">单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="4cfad-113">Click **Users**.</span></span>

4.  <span data-ttu-id="4cfad-114">验证 Office 通信服务器 2007 R2 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="4cfad-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="4cfad-115">![OCS 管理工具中的用户列表](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "OCS 管理工具中的用户列表")</span><span class="sxs-lookup"><span data-stu-id="4cfad-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="4cfad-116">**验证旧版 XMPP 联盟合作伙伴配置**</span><span class="sxs-lookup"><span data-stu-id="4cfad-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="4cfad-117">从旧的 XMPP 服务器中，导航到 "管理\\工具服务" 小程序。</span><span class="sxs-lookup"><span data-stu-id="4cfad-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="4cfad-118">验证是否已启动 Office 通信服务器 XMPP 网关服务。</span><span class="sxs-lookup"><span data-stu-id="4cfad-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="4cfad-119">![Office 通信服务器 XMPP 网关服务](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通信服务器 XMPP 网关服务")</span><span class="sxs-lookup"><span data-stu-id="4cfad-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

