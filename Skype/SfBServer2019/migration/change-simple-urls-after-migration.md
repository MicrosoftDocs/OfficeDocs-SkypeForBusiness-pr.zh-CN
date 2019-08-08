---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business 服务器支持简单的 Url。
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239491"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="60bf4-103">迁移后更改简单 URL</span><span class="sxs-lookup"><span data-stu-id="60bf4-103">Change simple URLs after migration</span></span>

<span data-ttu-id="60bf4-104">Skype for Business 服务器支持三个简单的 Url:</span><span class="sxs-lookup"><span data-stu-id="60bf4-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="60bf4-105">"**开会**" 用作网站或组织中的所有会议的基本 URL。</span><span class="sxs-lookup"><span data-stu-id="60bf4-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="60bf4-106">通过 "满足简单 URL", 加入会议的链接易于理解, 并且易于沟通和分发。</span><span class="sxs-lookup"><span data-stu-id="60bf4-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="60bf4-107">通过**拨入功能**, 可以访问 "电话拨入式会议设置" 网页。</span><span class="sxs-lookup"><span data-stu-id="60bf4-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="60bf4-108">拨入式简单 URL 包含在所有会议邀请中, 以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="60bf4-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="60bf4-109">**管理员**可快速访问 Skype For Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="60bf4-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="60bf4-110">管理员简单的 URL 是您的组织内部的。</span><span class="sxs-lookup"><span data-stu-id="60bf4-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="60bf4-111">迁移到 Skype for business 服务器之后, 你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。</span><span class="sxs-lookup"><span data-stu-id="60bf4-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="60bf4-112">如果旧版 Skype for Business 服务器控制器仍在拓扑中使用, 则不需要对您的简单 Url 进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="60bf4-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="60bf4-113">如果迁移后从拓扑中删除了 Skype for Business 服务器主管, 则必须更新简单 URL DNS 记录以指向其中一个 Skype for Business 服务器池。</span><span class="sxs-lookup"><span data-stu-id="60bf4-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="60bf4-114">但是, 当您更改简单的 URL 名称时, 必须在每个 Director 和前端服务器上运行 Enable-CsComputer 以注册更改。</span><span class="sxs-lookup"><span data-stu-id="60bf4-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="60bf4-115">更新 "满足简单 URL"</span><span class="sxs-lookup"><span data-stu-id="60bf4-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="60bf4-116">在拓扑生成器中, 右键单击顶部节点 " **Skype for Business 服务器**", 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="60bf4-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="60bf4-117">在左窗格中选择 "**简单 url** ", 然后单击 "**会议 url":** 选择 "满足 url", 然后单击 "**编辑 URL**"。</span><span class="sxs-lookup"><span data-stu-id="60bf4-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="60bf4-118">将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="60bf4-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="60bf4-119">更新管理员简单 URL</span><span class="sxs-lookup"><span data-stu-id="60bf4-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="60bf4-120">在拓扑生成器中, 右键单击顶部节点 " **Skype for Business 服务器**", 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="60bf4-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="60bf4-121">在左窗格中选择 "**简单 url** ", 然后在 "**管理访问 URL** " 框下方输入要用于管理对 Skype for business 服务器控制面板的简单 URL, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="60bf4-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="60bf4-122">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="60bf4-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="60bf4-123">最简单的选项https://admin是。<em> \<域\></em>。</span><span class="sxs-lookup"><span data-stu-id="60bf4-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="60bf4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60bf4-124">See also</span></span>

[<span data-ttu-id="60bf4-125">Skype for Business 服务器中的简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="60bf4-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
