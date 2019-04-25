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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: 请参阅如何配置团队以使用户可以与其他组织中的用户进行通信。
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222368"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="a57b1-103">让您的团队用户聊天并与其他团队组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="a57b1-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="a57b1-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="a57b1-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="a57b1-105">您有用户在不同域中您的业务。</span><span class="sxs-lookup"><span data-stu-id="a57b1-105">You have users in different domains in your business.</span></span> <span data-ttu-id="a57b1-106">例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="a57b1-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="a57b1-107">在您的组织团队用于联系外部组织的特定企业中的人员，您希望他人。</span><span class="sxs-lookup"><span data-stu-id="a57b1-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="a57b1-108">您希望任何其他人在世界上使用团队能够找到并与您联系，使用您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a57b1-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="a57b1-109">如果您和其他用户同时启用外部访问，并允许彼此的域，这将正常工作。</span><span class="sxs-lookup"><span data-stu-id="a57b1-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="a57b1-110">如果它不起作用，其他用户应确保他或她配置不阻止您的域。</span><span class="sxs-lookup"><span data-stu-id="a57b1-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="a57b1-111">这将使用户能够查找、 呼叫，并向您发送即时消息，以及设置与您的会议。</span><span class="sxs-lookup"><span data-stu-id="a57b1-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="a57b1-112">如果您希望外部用户有权访问工作组和通道，来宾访问可能转更好的方法。</span><span class="sxs-lookup"><span data-stu-id="a57b1-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="a57b1-113">请按照本文和确保到[启用来宾访问](set-up-guests.md)，以便用户可以进行通信。</span><span class="sxs-lookup"><span data-stu-id="a57b1-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a57b1-114">为了当前给外部用户的 Microsoft 团队客户端中联盟组织当前不是您的 AAD/租户的来宾之外，您必须是正确的混合的安装程序和业务 online 移至 Skype。</span><span class="sxs-lookup"><span data-stu-id="a57b1-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="a57b1-115">从 2/25/2019年团队尚未不支持本机联盟用户的情况下被业务 online 驻留在 Skype 的 SIP 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a57b1-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="a57b1-116">有关混合注册您的帐户，然后移到团队的其他设置，请参阅[升级业务混合部署到团队的 Skype](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。</span><span class="sxs-lookup"><span data-stu-id="a57b1-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="a57b1-117">让您的团队用户聊天并与其他团队组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="a57b1-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="a57b1-118">按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a57b1-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="a57b1-119">步骤 1-请务必设置的端口和所需的 Url。</span><span class="sxs-lookup"><span data-stu-id="a57b1-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="a57b1-120">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="a57b1-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="a57b1-121">步骤 2-启用组织与另一个团队组织进行通信</span><span class="sxs-lookup"><span data-stu-id="a57b1-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="a57b1-122">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="a57b1-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="a57b1-123">在左侧导航窗格中，转到**组织范围的设置** > **外部访问**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="a57b1-124">在**外部访问**页的顶部，单击对**上**的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="a57b1-125">如果您希望允许的所有工作组组织，与您的组织中的用户进行通信，请跳到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="a57b1-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="a57b1-126">如果您想要限制进行通信的组织可以与用户在组织中可以允许所有但某些域，或仅允许特定的部门。</span><span class="sxs-lookup"><span data-stu-id="a57b1-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="a57b1-127">若要允许所有但某些域，请添加您想要阻止通过单击**添加域**的域。</span><span class="sxs-lookup"><span data-stu-id="a57b1-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="a57b1-128">在**添加域**窗格置于域名，单击**已阻止**，然后**完成**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="a57b1-129">若要限制到特定 organizatioins 通信，请将这些域添加到**Alowed**状态的列表。</span><span class="sxs-lookup"><span data-stu-id="a57b1-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="a57b1-130">一旦您已添加到允许列表的任何域，与其他组织的通信将被限制为仅这些组织其域是允许列表中。</span><span class="sxs-lookup"><span data-stu-id="a57b1-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="a57b1-131">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a57b1-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="a57b1-132">然后确保其他团队组织中的管理员执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="a57b1-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="a57b1-133">例如，在其**允许域**列表中，其管理员需要为您的业务输入的域，如果这些限制的组织可以与他们的用户通信。</span><span class="sxs-lookup"><span data-stu-id="a57b1-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="a57b1-134">步骤 3-对其进行测试</span><span class="sxs-lookup"><span data-stu-id="a57b1-134">Step 3 - Test it</span></span>
<span data-ttu-id="a57b1-135">若要测试您的安装程序，您需要的团队用户在防火墙背后处于不是。</span><span class="sxs-lookup"><span data-stu-id="a57b1-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="a57b1-136">您和从组织管理员已更改的**外部访问**设置后，您应正确运行。</span><span class="sxs-lookup"><span data-stu-id="a57b1-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="a57b1-137">在工作组应用程序中，按电子邮件地址搜索人员并发送一个请求聊天。</span><span class="sxs-lookup"><span data-stu-id="a57b1-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="a57b1-138">让您的团队联系人向您发送请求聊天。</span><span class="sxs-lookup"><span data-stu-id="a57b1-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="a57b1-139">如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="a57b1-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="a57b1-140">测试您的防火墙问题是否另一种方法是转到咖啡馆，如在防火墙背后不处于 wifi 位置并使用团队将请求发送到您的联系人聊天。</span><span class="sxs-lookup"><span data-stu-id="a57b1-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="a57b1-141">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="a57b1-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="a57b1-142">与 Skype 的业务 Online 组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="a57b1-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="a57b1-143">如果您可以将其设置可以让您的团队用户查找和 Skype 限制可以联系的用户的业务组织中的联系人用户，您将询问要执行这些步骤的组织中的管理员。</span><span class="sxs-lookup"><span data-stu-id="a57b1-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="a57b1-144">![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **的业务管理中心使用 Skype**</span><span class="sxs-lookup"><span data-stu-id="a57b1-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="a57b1-145">具有管理员，组织执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a57b1-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="a57b1-146">在 Office 365 管理中心，转到**管理中心** > **团队 & Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="a57b1-147">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="a57b1-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="a57b1-148">若要设置通信与特定的企业或用户在另一个域中，在下拉列表框中，选择**在仅允许域**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="a57b1-149">或者，是否要启用世界上拥有打开与其他人进行通信的业务策略的 Skype 选择**上除外被阻止的域**。</span><span class="sxs-lookup"><span data-stu-id="a57b1-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="a57b1-150">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a57b1-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="a57b1-151">在**已阻止或允许的域**，下，选择**+**，添加您希望允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a57b1-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="a57b1-152">确保其他组织中的管理员执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="a57b1-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="a57b1-153">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="a57b1-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="a57b1-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="a57b1-154">Related topics</span></span>

<span data-ttu-id="a57b1-155">[登录到 Microsoft 团队](sign-in-teams.md)
[最终用户培训团队](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="a57b1-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

