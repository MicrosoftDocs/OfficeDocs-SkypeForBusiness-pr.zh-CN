---
title: 验证与旧版池共存的引导池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51709bba3f96f8761b9687387b78954c8840ff41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="ccc76-102">验证与旧版池共存的引导池</span><span class="sxs-lookup"><span data-stu-id="ccc76-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc76-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ccc76-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="ccc76-104">在 Office Communications Server 2007 R2 管理工具中验证池</span><span class="sxs-lookup"><span data-stu-id="ccc76-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="ccc76-105">打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="ccc76-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="ccc76-106">展开“林”\*\*\*\* 节点，展开“Standard Edition 服务器”\*\*\*\* 或“企业版池”\*\*\*\* 节点，然后展开池或服务器名称。</span><span class="sxs-lookup"><span data-stu-id="ccc76-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="ccc76-107">确保池上正在运行 Office 通信服务器 2007 R2 服务。</span><span class="sxs-lookup"><span data-stu-id="ccc76-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="ccc76-108">![Office 通信服务器 2007 R2 管理控制台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通信服务器 2007 R2 管理控制台")</span><span class="sxs-lookup"><span data-stu-id="ccc76-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="ccc76-109">验证 Lync Server 2013 控制面板中的引导池</span><span class="sxs-lookup"><span data-stu-id="ccc76-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="ccc76-110">从作为 CsAdministrator 角色成员的用户帐户，登录到 Lync Server 2013 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ccc76-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="ccc76-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ccc76-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ccc76-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="ccc76-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ccc76-113">单击“拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc76-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="ccc76-114">验证您部署的服务器是否在试点池中。</span><span class="sxs-lookup"><span data-stu-id="ccc76-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="ccc76-115">![Lync Server 控制面板拓扑页面](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server 控制面板拓扑页面")</span><span class="sxs-lookup"><span data-stu-id="ccc76-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="ccc76-116">验证 Lync Server 2013 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="ccc76-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="ccc76-117">在 Lync Server 2013 前端服务器上，从 "**管理工具**" 组中打开 "**服务**" 小程序。</span><span class="sxs-lookup"><span data-stu-id="ccc76-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="ccc76-118">验证列出的服务是否与下图中的列表匹配。</span><span class="sxs-lookup"><span data-stu-id="ccc76-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="ccc76-119">![显示 Lync services 的服务页面已启动](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "显示 Lync services 的服务页面已启动")</span><span class="sxs-lookup"><span data-stu-id="ccc76-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

