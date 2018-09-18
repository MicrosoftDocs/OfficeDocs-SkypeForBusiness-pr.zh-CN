---
title: 与其他组织中的团队用户通信
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 请参阅如何配置团队以使用户可以与其他组织中的用户进行通信。
ms.openlocfilehash: d7423109d4fba01ca85c1602bfcf92190b539abf
ms.sourcegitcommit: 116d17befc17503968e00e45be338834aa2185b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998624"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="fc5ba-103">让您的团队用户聊天并与其他团队组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="fc5ba-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="fc5ba-104">在下列情况下，请按照本文的步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="fc5ba-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="fc5ba-105">您有用户在不同域中您的业务。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-105">You have users in different domains in your business.</span></span> <span data-ttu-id="fc5ba-106">例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="fc5ba-107">在您的组织团队用于联系外部组织的特定企业中的人员，您希望他人。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="fc5ba-108">您希望任何其他人在世界上使用团队能够找到并与您联系，使用您的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="fc5ba-109">如果您和其他用户同时启用外部访问，并允许彼此的域，这将正常工作。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="fc5ba-110">如果它不起作用，其他用户应确保他或她配置不阻止您的域。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="fc5ba-111">这将使用户能够查找、 呼叫，并向您发送即时消息，以及设置与您的会议。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="fc5ba-112">如果您希望外部用户有权访问工作组和通道，来宾访问可能转更好的方法。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="fc5ba-113">请按照本文和确保到[启用来宾访问](set-up-guests.md)，以便用户可以进行通信。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="fc5ba-114">让您的团队用户聊天并与其他团队组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="fc5ba-114">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="fc5ba-115">按照以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-115">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="fc5ba-116">步骤 1-请务必设置的端口和所需的 Url。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-116">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="fc5ba-117">**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**</span><span class="sxs-lookup"><span data-stu-id="fc5ba-117">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="fc5ba-118">步骤 2-启用组织与另一个团队组织进行通信</span><span class="sxs-lookup"><span data-stu-id="fc5ba-118">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="fc5ba-119">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="fc5ba-119">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="fc5ba-120">在左侧导航窗格中，转到**组织范围的设置** > **外部访问**。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-120">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="fc5ba-121">在**外部访问**页的顶部，单击对**上**的**外部访问**。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-121">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="fc5ba-122">如果您希望允许的所有工作组组织，与您的组织中的用户进行通信，请跳到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-122">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="fc5ba-123">如果您希望限制哪些通信组织可以与用户在组织中，通过单击**域添加**到允许列表添加其他组织的域名。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-123">If you want to limit which organizations can communicate with users in your organization, add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="fc5ba-124">在**添加域**窗格中，**允许**，然后**完成**将在域名称单击。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-124">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="fc5ba-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-125">Click **Save**.</span></span> 

   5. <span data-ttu-id="fc5ba-126">然后确保其他团队组织中的管理员执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-126">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="fc5ba-127">例如，在其**允许域**列表中，其管理员需要为您的业务输入的域，如果这些限制的组织可以与他们的用户通信。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-127">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="fc5ba-128">步骤 3-对其进行测试</span><span class="sxs-lookup"><span data-stu-id="fc5ba-128">Step 3 - Test it</span></span>
<span data-ttu-id="fc5ba-129">若要测试您的安装程序，您需要的团队用户在防火墙背后处于不是。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-129">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="fc5ba-130">您和从组织管理员已更改的**外部访问**设置后，您应正确运行。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-130">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="fc5ba-131">在工作组应用程序中，按电子邮件地址搜索人员并发送一个请求聊天。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-131">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="fc5ba-132">让您的团队联系人向您发送请求聊天。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-132">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="fc5ba-133">如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-133">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="fc5ba-134">测试您的防火墙问题是否另一种方法是转到咖啡馆，如在防火墙背后不处于 wifi 位置并使用团队将请求发送到您的联系人聊天。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-134">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="fc5ba-135">如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-135">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="fc5ba-136">与 Skype 的业务 Online 组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="fc5ba-136">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="fc5ba-137">如果您可以将其设置可以让您的团队用户查找和 Skype 限制可以联系的用户的业务组织中的联系人用户，您将询问要执行这些步骤的组织中的管理员。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-137">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="fc5ba-138">![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **的业务管理中心使用 Skype**</span><span class="sxs-lookup"><span data-stu-id="fc5ba-138">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="fc5ba-139">具有管理员，组织执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fc5ba-139">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="fc5ba-140">在 Office 365 管理中心，转到**管理中心** > **团队和 Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-140">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="fc5ba-141">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-141">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="fc5ba-142">若要设置通信与特定的企业或用户在另一个域中，在下拉列表框中，选择**在仅允许域**。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-142">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="fc5ba-143">或者，是否要启用世界上拥有打开与其他人进行通信的业务策略的 Skype 选择**上除外被阻止的域**。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-143">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="fc5ba-144">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-144">This is the default setting.</span></span>
    
4. <span data-ttu-id="fc5ba-145">在**已阻止或允许的域**，下，选择**+**，添加您希望允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-145">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="fc5ba-146">确保其他组织中的管理员执行相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-146">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="fc5ba-147">例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。</span><span class="sxs-lookup"><span data-stu-id="fc5ba-147">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="fc5ba-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="fc5ba-148">Related topics</span></span>

<span data-ttu-id="fc5ba-149">[登录到 Microsoft 团队](sign-in-teams.md)
[最终用户培训团队](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="fc5ba-149">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

