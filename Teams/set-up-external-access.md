---
title: 允许用户与外部团队用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: '请参阅如何配置团队以使用户可以与其他组织中的用户或外部给他们的联系人 talk 允许。 '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863377"
---
# <a name="allow-users-to-contact-external-teams-users"></a><span data-ttu-id="c6c0a-103">允许用户与外部团队用户</span><span class="sxs-lookup"><span data-stu-id="c6c0a-103">Allow users to contact external Teams users</span></span>
  
<span data-ttu-id="c6c0a-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="c6c0a-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="c6c0a-p101">你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="c6c0a-107">在您的组织团队用于联系外部组织的特定企业中的人员，您希望他人。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="c6c0a-108">您希望任何其他人在世界上使用团队能够找到并与您联系，使用您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="c6c0a-109">如果您和它们使用的默认设置，这将自动工作。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-109">If you and they use the default settings, this will work automatically.</span></span> <span data-ttu-id="c6c0a-110">如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="c6c0a-111">为你的用户启用企业到企业通信</span><span class="sxs-lookup"><span data-stu-id="c6c0a-111">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="c6c0a-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c0a-112"></span></span>

<span data-ttu-id="c6c0a-113">在这两个组织为此，您必须在 Office 365 中具有[管理员权限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="c6c0a-114">![](media/teams-logo-30x30.png)**使用 Microsoft 团队和业务管理中心的 Skype**团队-徽标 30x30.png。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-114">![teams-logo-30x30.png](media/teams-logo-30x30.png)**Using the Microsoft Teams and Skype for Business Admin Center**.</span></span>
1. <span data-ttu-id="c6c0a-115">在左侧导航窗格中，转到**组织范围的设置** > **外部访问**。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-115">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

2. <span data-ttu-id="c6c0a-116">在**外部访问**页的顶部，启用**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-116">At the top of the **External access** page, turn on **External access**.</span></span> 

3. <span data-ttu-id="c6c0a-117">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-117">Click **Save**.</span></span> 

4. <span data-ttu-id="c6c0a-118">请确保其他组织中的管理遵循相同的步骤，并进入您的业务为允许域的域。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-118">Make sure the admin in the other organization follows the same steps and enters the domain for your business as an allowed domain.</span></span>
 
5. <span data-ttu-id="c6c0a-p103">**测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-p103">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="c6c0a-121">测试和故障排除</span><span class="sxs-lookup"><span data-stu-id="c6c0a-121">Test and troubleshoot</span></span>
<span data-ttu-id="c6c0a-122"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c0a-122"></span></span>

 <span data-ttu-id="c6c0a-123">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="c6c0a-123">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="c6c0a-124">若要测试您的安装程序，您需要在公司防火墙背后处于不是对团队的联系人。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-124">To test your setup, you need a contact on Teams who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="c6c0a-125">后更改您的外部访问设置，**等待达 24 小时到测试**。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-125">After you change your External Access settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="c6c0a-126">搜索团队中您联系人并发送一个请求聊天。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-126">Search for your contact in Teams, and send a request to chat.</span></span>
    
    <span data-ttu-id="c6c0a-127">如果您收到一条消息，无法将其发送由于公司策略，您需要仔细检查您的[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-127">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="c6c0a-128">让您的联系人向您发送请求聊天。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-128">Ask your contact to send you a request to chat.</span></span> <span data-ttu-id="c6c0a-129">如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="c6c0a-130">测试您的防火墙问题是否另一种方法是转到咖啡馆，如在防火墙背后不处于 wifi 位置并使用团队将请求发送到您的联系人聊天。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="c6c0a-131">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="c6c0a-132">在与其他企业连接时如何查找其他人以及如何被找到</span><span class="sxs-lookup"><span data-stu-id="c6c0a-132">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="c6c0a-133"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c0a-133"></span></span>

<span data-ttu-id="c6c0a-134">与其他团队用户启用外部访问后，用户可以通过搜索其登录名查找联盟的团队用户： 例如，Rob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-134">After you enable External Access with other Teams users, your users can find federated Teams users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="c6c0a-135">然后他们将需要将此人添加到他们的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-135">Then they will need to add the person to their list of contacts.</span></span>
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="c6c0a-136">设置联盟企业通信的提示</span><span class="sxs-lookup"><span data-stu-id="c6c0a-136">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="c6c0a-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c0a-137"></span></span>
    
- <span data-ttu-id="c6c0a-138">当两个团队用户与 Office 365 域与之通信彼此在单独的域时，只能使用两个组织中打开的团队功能 （例如，视频对话或桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-138">When two Teams users with Office 365 domains are communicating with each other on separate domains, they can only use Teams features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="c6c0a-139">如果您的组织中的团队用户置于就地或诉讼保留，该用户和其他 Skype 业务或 Skype 用户之间的 IM 对话将保存其邮箱中的**可恢复的项目**中。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-139">If Teams users in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="c6c0a-140">这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c6c0a-140">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
  
<span data-ttu-id="c6c0a-141"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c0a-141"></span></span>
 
