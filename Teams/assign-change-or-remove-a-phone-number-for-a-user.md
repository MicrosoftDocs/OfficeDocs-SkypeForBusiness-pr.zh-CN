---
title: 为用户分配、更改或删除电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 了解如何为你的团队或 Skype for business 用户分配、更改或删除工作电话号码, 以便外部企业和客户可以呼叫。
ms.openlocfilehash: ea2135a095a60d6da37ce4db0fb443f2e9a74154
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493895"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="db47a-103">为用户分配、更改或删除电话号码</span><span class="sxs-lookup"><span data-stu-id="db47a-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="db47a-104">在 Office 365 中设置呼叫计划时, 您可以为用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="db47a-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="db47a-105">在 Microsoft Teams 客户端，当用户单击**呼叫**时，就会列出你分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="db47a-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![显示在 Microsoft Teams 中的用户电话号码。](media/teams-phone-number.png)

<span data-ttu-id="db47a-107">在 Skype for Business 客户端中, 您分配的电话号码将在 "**工作电话**" 框中列出, 并且不能由用户更改。</span><span class="sxs-lookup"><span data-stu-id="db47a-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Work Phone Number is Greyed Out.](media/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="db47a-109">如果用户想要[更改其 skype for business 的电话号码](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e), 并且 Skype for business 应用中的电话号码不能更改或灰显, 这意味着管理员已为其设置了它, 并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="db47a-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="db47a-110">当您设置用户以使其可以拨打和接听电话时, 您必须首先使用 Skype for Business 管理中心并分配电话号码, 但您可以根据需要更改或删除电话号码。</span><span class="sxs-lookup"><span data-stu-id="db47a-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="db47a-111">若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="db47a-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
  
> [!NOTE]
> <span data-ttu-id="db47a-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="db47a-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="db47a-115">为用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="db47a-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="db47a-116">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="db47a-116">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="db47a-117">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="db47a-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="db47a-118">转到 " **Microsoft 团队管理中心** > **旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="db47a-119">在左侧导航中, 单击 "**语音** > **语音用户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="db47a-120">要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。</span><span class="sxs-lookup"><span data-stu-id="db47a-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="db47a-121">在" **语音用户**"页面上，查找并选择要为其分配电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="db47a-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="db47a-122">在"操作"窗格中，单击" **分配号码**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="db47a-123">在 "**分配**号码" 页面上的 "**选择要分配的号码**" 列表中, 选择用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="db47a-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="db47a-124">如果您未看到列出的任何电话号码, 您需要首先[为您的用户获取电话号码](/microsoftteams/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="db47a-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users) first.</span></span> <span data-ttu-id="db47a-125">或者，如果使用 **Skype for Business 管理中心** > **语音** > **电话号码**页面，可单击**添加**，然后单击**新用户号码**。</span><span class="sxs-lookup"><span data-stu-id="db47a-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="db47a-126">若要分配或更改关联的紧急地址, 请在 "**选择已验证的紧急位置**" 下, 从列表中选择位置, 或者, 如果定义了多个位置, 请在搜索框中输入城市的名称, 然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="db47a-127">在选择电话号码和紧急位置之后，请单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="db47a-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="db47a-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="db47a-131">更改用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="db47a-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="db47a-132">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="db47a-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="db47a-133">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="db47a-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="db47a-134">转到 " **Microsoft 团队管理中心** > **旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="db47a-135">在左侧导航中, 单击 "**语音** > **语音用户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="db47a-136">在" **语音用户**"页面上，查找并选择要更改其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="db47a-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="db47a-137">在操作窗格中的 "**分配的号码**" 下, 单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="db47a-138">在" **分配号码**"页面上，单击" **更改号码**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="db47a-139">在" **分配号码**"页面上的" **选择要分配的号码**"下，使用列表选择新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="db47a-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="db47a-140">若要更改关联的紧急地址, 请单击 "**更改位置**", 然后在 "**将紧急地址更改为**" 下, 从列表中选择位置, 或者, 如果定义了多个位置, 请在搜索框中输入城市的名称, 然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="db47a-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="db47a-141">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="db47a-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="db47a-142">删除用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="db47a-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="db47a-143">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="db47a-143">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="db47a-144">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="db47a-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="db47a-145">转到 " **Microsoft 团队管理中心** > **旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="db47a-146">在左侧导航中, 单击 "**语音** > **语音用户**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="db47a-147">在" **语音用户**"页面上，查找并选择要删除其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="db47a-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="db47a-148">在操作窗格中的 "**分配的号码**" 下, 单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="db47a-149">在" **要删除选定的已分配号码吗?**" 页面上，单击" **是**"。</span><span class="sxs-lookup"><span data-stu-id="db47a-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="db47a-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="db47a-150">Related topics</span></span>
[<span data-ttu-id="db47a-151">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="db47a-151">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="db47a-152">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="db47a-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="db47a-153">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="db47a-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="db47a-154">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="db47a-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 