---
title: 迁移后更改简单 Url
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务服务器支持简单 Url。
ms.openlocfilehash: a67e9a8ef46b7809fdc8ce8b4eaadc2ca4720966
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028829"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="bb9ac-103">迁移后更改简单 Url</span><span class="sxs-lookup"><span data-stu-id="bb9ac-103">Change simple URLs after migration</span></span>

<span data-ttu-id="bb9ac-104">Skype 业务 server 支持三种简单 Url:</span><span class="sxs-lookup"><span data-stu-id="bb9ac-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="bb9ac-105">**满足**对站点或组织中的所有会议使用作为基 URL。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="bb9ac-106">与会议的简单 URL，加入会议的链接是易于理解，且轻松地进行通信和分发。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="bb9ac-107">**电话拨入式**允许访问电话拨入式会议设置网页。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="bb9ac-108">电话拨入式简单 URL 包含所有的会议邀请中，以便想要拨入会议的用户可以访问所需的电话号码和 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="bb9ac-109">**管理**业务 Server Control Panel 启用 Skype 快速访问。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="bb9ac-110">组织内部的管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="bb9ac-111">迁移到 Skype for Business Server 之后，您必须知道如何更改会影响您的 DNS 记录和证书的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="bb9ac-112">如果旧 Skype 的业务 Server Director 仍保留在拓扑中的使用，无需更改简单 Url 是必需的。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="bb9ac-113">如果 Skype 的业务 Server Director 从拓扑中删除迁移后，必须更新简单 URL 的 DNS 记录以指向业务服务器池的 Skype 之一。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="bb9ac-114">无论何时更改简单 URL 名称，但是，必须以注册该更改每台控制器和前端服务器上运行 Enable-cscomputer。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="bb9ac-115">更新会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="bb9ac-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="bb9ac-116">在拓扑生成器中，右键单击顶层节点**Skype 业务服务器**，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="bb9ac-117">然后下面选择左窗格中，**简单 Url** **会议 Url:** 选择会议 URL，然后单击**编辑 URL**。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="bb9ac-118">将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="bb9ac-119">更新管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="bb9ac-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="bb9ac-120">在拓扑生成器中，右键单击顶层节点**Skype 业务服务器**，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="bb9ac-121">选择**简单 Url**的左窗格，然后下方**管理访问 URL**框中输入所需的管理访问权限 Skype 业务 Server Control Panel 的简单 URL，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bb9ac-122">建议尽可能使用最简单的 URL 作为管理 URL。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="bb9ac-123">简单的选项是https://admin。_\<域\>_。</span><span class="sxs-lookup"><span data-stu-id="bb9ac-123">The simplest option is https://admin._\<domain\>_.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb9ac-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb9ac-124">See also</span></span>

[<span data-ttu-id="bb9ac-125">Skype 中的简单 url 的业务服务器的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="bb9ac-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
