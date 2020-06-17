---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 支持简单 Url。
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753902"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="2b357-103">迁移后更改简单 URL</span><span class="sxs-lookup"><span data-stu-id="2b357-103">Change simple URLs after migration</span></span>

<span data-ttu-id="2b357-104">Skype for Business Server 支持三个简单的 Url：</span><span class="sxs-lookup"><span data-stu-id="2b357-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="2b357-105">\*\*\*\*“会议”用作站点或组织中所有会议的基 URL。</span><span class="sxs-lookup"><span data-stu-id="2b357-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="2b357-106">通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。</span><span class="sxs-lookup"><span data-stu-id="2b357-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="2b357-107">\*\*\*\*“拨入”允许访问“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="2b357-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="2b357-108">拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="2b357-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="2b357-109">**管理员**可以快速访问 Skype For Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2b357-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2b357-110">管理简单 URL 是组织内部的。</span><span class="sxs-lookup"><span data-stu-id="2b357-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="2b357-111">迁移到 Skype for business Server 后，必须了解更改如何影响简单 Url 的 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="2b357-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="2b357-112">如果旧版 Skype for Business Server 控制器在拓扑中仍处于使用中，则不需要对简单 Url 进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="2b357-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="2b357-113">如果迁移后从拓扑中删除了 Skype for Business Server 控制器，则必须将简单 URL DNS 记录更新为指向某个 Skype for Business Server 池。</span><span class="sxs-lookup"><span data-stu-id="2b357-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="2b357-114">但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，以注册该更改。</span><span class="sxs-lookup"><span data-stu-id="2b357-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="2b357-115">更新 "符合简单 URL"</span><span class="sxs-lookup"><span data-stu-id="2b357-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="2b357-116">在拓扑生成器中，右键单击顶部节点 " **Skype For Business Server**"，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2b357-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="2b357-117">在左窗格中选择 "**简单 url** "，然后单击 "**会议 url"：** 选择 "满足 url"，然后单击 "**编辑 URL**"。</span><span class="sxs-lookup"><span data-stu-id="2b357-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="2b357-118">将 URL 更新为所需的值，然后单击“确定”\*\*\*\* 保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="2b357-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="2b357-119">更新管理员简单 URL</span><span class="sxs-lookup"><span data-stu-id="2b357-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="2b357-120">在拓扑生成器中，右键单击顶部节点 " **Skype For Business Server**"，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2b357-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="2b357-121">在左窗格中选择 "**简单 url** "，然后在 "**管理访问 URL** " 框下，输入要用于对 Skype for business Server 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2b357-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="2b357-122">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2b357-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="2b357-123">最简单的方法是 https://admin ... <em>\<domain\></em></span><span class="sxs-lookup"><span data-stu-id="2b357-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2b357-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b357-124">See also</span></span>

[<span data-ttu-id="2b357-125">Skype for Business Server 中简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2b357-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
