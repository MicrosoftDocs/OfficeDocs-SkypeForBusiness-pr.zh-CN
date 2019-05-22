---
title: 与其他组织中的 Teams 用户通信
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: 了解如何配置团队以允许用户与其他组织中的用户进行通信。
ms.openlocfilehash: 5da04eec6b8ce643f32639a014237ffe118aeabe
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34343935"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="96f95-103">让你的团队用户与其他团队组织中的用户进行聊天和通信</span><span class="sxs-lookup"><span data-stu-id="96f95-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="96f95-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="96f95-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="96f95-105">您的企业中有不同域的用户。</span><span class="sxs-lookup"><span data-stu-id="96f95-105">You have users in different domains in your business.</span></span> <span data-ttu-id="96f95-106">例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="96f95-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="96f95-107">您希望组织中的人员可以使用团队与组织外部的特定企业中的人员联系。</span><span class="sxs-lookup"><span data-stu-id="96f95-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="96f95-108">您希望世界上任何其他使用团队的人都能够使用您的电子邮件地址查找和与您联系。</span><span class="sxs-lookup"><span data-stu-id="96f95-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="96f95-109">如果您和其他用户都启用了外部访问并允许彼此的域, 则这将起作用。</span><span class="sxs-lookup"><span data-stu-id="96f95-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="96f95-110">如果不起作用, 另一用户应确保他或她的配置不会阻止您的域。</span><span class="sxs-lookup"><span data-stu-id="96f95-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="96f95-111">这将允许用户查找、呼叫和发送即时消息, 以及设置会议。</span><span class="sxs-lookup"><span data-stu-id="96f95-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="96f95-112">如果希望外部用户有权访问团队和频道, 来宾访问可能是更好的途径。</span><span class="sxs-lookup"><span data-stu-id="96f95-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="96f95-113">按照本文中的步骤操作, 并确保[启用来宾访问](set-up-guests.md), 以便用户可以进行通信。</span><span class="sxs-lookup"><span data-stu-id="96f95-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96f95-114">若要当前将 Microsoft 团队客户端中的外部用户与你的组织外部的外部用户 (当前不是 AAD/租户的来宾) 联合, 则必须正确设置混合并将其移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="96f95-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="96f95-115">从2/25/2019 起, 团队尚不支持不带 SIP 档案的用户在 Skype for business Online 中托管的本机联合。</span><span class="sxs-lookup"><span data-stu-id="96f95-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="96f95-116">有关设置混合帐户和迁移到团队的详细信息, 请参阅将[Skype for Business 混合部署升级到团队](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。</span><span class="sxs-lookup"><span data-stu-id="96f95-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="96f95-117">让你的团队用户与其他团队组织中的用户进行聊天和通信</span><span class="sxs-lookup"><span data-stu-id="96f95-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="96f95-118">请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="96f95-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="96f95-119">步骤 1-确保设置所需的端口和 Url。</span><span class="sxs-lookup"><span data-stu-id="96f95-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="96f95-120">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="96f95-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="96f95-121">步骤 2-使你的组织能够与另一个团队组织通信</span><span class="sxs-lookup"><span data-stu-id="96f95-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="96f95-122">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="96f95-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="96f95-123">在左侧导航中, 转到 "**组织范围的设置** > **外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="96f95-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="96f95-124">在 "**外部访问**" 页面顶部, 单击 "**外部访问** **"**。</span><span class="sxs-lookup"><span data-stu-id="96f95-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="96f95-125">如果你希望允许所有团队组织与你的组织中的用户进行通信, 请跳至步骤5。</span><span class="sxs-lookup"><span data-stu-id="96f95-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="96f95-126">如果想要限制哪些组织可以与你的组织中的用户进行通信, 你可以允许除某些域之外的所有域, 或者仅允许特定组织。</span><span class="sxs-lookup"><span data-stu-id="96f95-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="96f95-127">若要允许除某些域之外的所有域, 请通过单击 "**添加域**" 来添加要阻止的域。</span><span class="sxs-lookup"><span data-stu-id="96f95-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="96f95-128">在 "**添加域**" 窗格中, 输入域名, 单击 "已**阻止**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="96f95-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="96f95-129">若要限制特定 organizatioins 的通信, 请将这些域添加到状态为**Alowed**的列表中。</span><span class="sxs-lookup"><span data-stu-id="96f95-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="96f95-130">将任何域添加到 "允许" 列表后, 与其他组织的通信将仅限于其域位于 "允许" 列表中的组织。</span><span class="sxs-lookup"><span data-stu-id="96f95-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="96f95-131">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="96f95-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="96f95-132">然后确保其他团队组织中的管理员执行这些相同步骤。</span><span class="sxs-lookup"><span data-stu-id="96f95-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="96f95-133">例如, 在 "**允许的域**" 列表中, 他们的管理员需要为你的企业输入域, 前提是这些组织可以与他们的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="96f95-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="96f95-134">步骤 3-测试</span><span class="sxs-lookup"><span data-stu-id="96f95-134">Step 3 - Test it</span></span>
<span data-ttu-id="96f95-135">若要测试你的设置, 你需要一个不在防火墙后面的团队用户。</span><span class="sxs-lookup"><span data-stu-id="96f95-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="96f95-136">当您和组织的管理员更改了**外部访问**设置后, 您应该可以继续。</span><span class="sxs-lookup"><span data-stu-id="96f95-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="96f95-137">在 "团队" 应用中, 按电子邮件地址搜索人员, 然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="96f95-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="96f95-138">让您的团队联系人向您发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="96f95-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="96f95-139">如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="96f95-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="96f95-140">测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 wifi 位置 (如咖啡店), 并使用团队向你的联系人发送有关聊天的请求。</span><span class="sxs-lookup"><span data-stu-id="96f95-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="96f95-141">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="96f95-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="96f95-142">与 Skype for Business Online 组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="96f95-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="96f95-143">如果你将其设置为让你的团队用户找到并联系 Skype for business 组织中的用户以限制谁可以联系他们的用户, 你将要求该组织中的管理员执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="96f95-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="96f95-144">![](media/sfb-logo-30x30.png) **使用 Skype for business 管理中心 sfb-logo-30x30 的**png</span><span class="sxs-lookup"><span data-stu-id="96f95-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="96f95-145">让该组织中的管理员执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="96f95-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="96f95-146">在 Office 365 管理中心中, 转到 "**管理中心** > "**团队 & Skype** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="96f95-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="96f95-147">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="96f95-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="96f95-148">若要设置与特定企业或与其他域中的用户的通信, 请在下拉框中选择 **"仅针对允许的域"**。</span><span class="sxs-lookup"><span data-stu-id="96f95-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="96f95-149">或者, 如果他们想要与世界上的所有其他人 (具有打开的 Skype for Business 策略) 进行通信, 请选择 **"开" (阻止的域除外**)。</span><span class="sxs-lookup"><span data-stu-id="96f95-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="96f95-150">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="96f95-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="96f95-151">在 "**被阻止或允许**的**+** 域" 下, 选择并添加您要允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="96f95-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="96f95-152">请确保其他组织中的管理员执行这些相同步骤。</span><span class="sxs-lookup"><span data-stu-id="96f95-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="96f95-153">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="96f95-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="96f95-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="96f95-154">Related topics</span></span>

<span data-ttu-id="96f95-155">[登录 Microsoft 团队](sign-in-teams.md)
[最终用户培训团队](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="96f95-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

