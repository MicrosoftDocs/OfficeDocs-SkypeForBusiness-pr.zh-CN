---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c9f46944e80c5eb7a2d81de6f164d19aab64d29
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="39c0f-102">迁移后更改简单 URL</span><span class="sxs-lookup"><span data-stu-id="39c0f-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c0f-103">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="39c0f-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="39c0f-104">Lync Server 支持三个简单的 Url：</span><span class="sxs-lookup"><span data-stu-id="39c0f-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="39c0f-105">\*\*\*\*“会议”用作站点或组织中所有会议的基 URL。</span><span class="sxs-lookup"><span data-stu-id="39c0f-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="39c0f-106">通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。</span><span class="sxs-lookup"><span data-stu-id="39c0f-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="39c0f-107">\*\*\*\*“拨入”允许访问“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="39c0f-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="39c0f-108">拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="39c0f-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="39c0f-109">**管理员**可以快速访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="39c0f-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="39c0f-110">管理简单 URL 是组织内部的。</span><span class="sxs-lookup"><span data-stu-id="39c0f-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="39c0f-111">在迁移到 Lync Server 2013 之后，您必须了解更改如何影响简单 Url 的 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="39c0f-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="39c0f-112">如果旧版 Lync Server 2010 控制器在拓扑中仍处于使用中，则不需要对简单 Url 进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="39c0f-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="39c0f-113">如果在迁移后从拓扑中删除了 Lync Server 2010 控制器，则必须将简单 URL DNS 记录更新为指向某个 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="39c0f-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="39c0f-114">但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，以注册该更改。</span><span class="sxs-lookup"><span data-stu-id="39c0f-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="39c0f-115">迁移后更改简单 Url</span><span class="sxs-lookup"><span data-stu-id="39c0f-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="39c0f-116">**更新 "符合简单 URL"**</span><span class="sxs-lookup"><span data-stu-id="39c0f-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="39c0f-117">在拓扑生成器中，右键单击顶部节点**Lync Server**，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="39c0f-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="39c0f-118">在左窗格中选择 "**简单 url** "，然后单击 "**会议 url"：** 选择 "满足 url"，然后单击 "**编辑 URL**"。</span><span class="sxs-lookup"><span data-stu-id="39c0f-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="39c0f-119">将 URL 更新为所需的值，然后单击“确定”\*\*\*\* 保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="39c0f-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="39c0f-120">**更新管理员简单 URL**</span><span class="sxs-lookup"><span data-stu-id="39c0f-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="39c0f-121">在拓扑生成器中，右键单击顶部节点**Lync Server**，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="39c0f-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="39c0f-122">在左窗格中选择 "**简单 url** "，然后在 "**管理访问 URL** " 框下，输入要用于对 Lync Server 2013 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="39c0f-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="39c0f-123">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="39c0f-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="39c0f-124">最简单的方法是<STRONG> https://admin 。</STRONG> &lt;域 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="39c0f-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39c0f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39c0f-125">See Also</span></span>


[<span data-ttu-id="39c0f-126">在 Lync Server 2013 中规划简单 Url</span><span class="sxs-lookup"><span data-stu-id="39c0f-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

