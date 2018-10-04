---
title: 为用户分配、更改或删除电话号码
ms.author: tonysmit
author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 了解如何给 Skype for Business 用户分配、更改或删除工作电话号码，以便外部业务和客户能呼入。
ms.openlocfilehash: 40c067657132781d29b8f20a3738d6d28ce36331
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374655"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="0608f-103">为用户分配、更改或删除电话号码</span><span class="sxs-lookup"><span data-stu-id="0608f-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="0608f-104">时设置调用计划在 Office 365 中，您可以向用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="0608f-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="0608f-105">在 Microsoft Teams 客户端，当用户单击**呼叫**时，就会列出你分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0608f-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![显示在 Microsoft Teams 中的用户电话号码。](../images/teams-phone-number.png)

<span data-ttu-id="0608f-107">在业务客户端 Skype，分配的电话号码将列在**工作电话**框中，不能由用户更改。</span><span class="sxs-lookup"><span data-stu-id="0608f-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![Work Phone Number is Greyed Out.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="0608f-109">如果用户要[更改他/她的 Skype for Business 的电话号码](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e)和中的电话号码为业务应用程序 Skype 不能更改或灰显，则表示管理员已将其设置为它们，它不能更改它们。</span><span class="sxs-lookup"><span data-stu-id="0608f-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="0608f-110">当您要设置用户，以便他们可以发起和接收电话呼叫，您必须首先 Skype 用于业务管理中心和分配电话号码，但您可以更改或删除的电话号码，如果您需要。</span><span class="sxs-lookup"><span data-stu-id="0608f-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="0608f-111">若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="0608f-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0608f-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="0608f-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="0608f-115">为用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="0608f-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="0608f-116">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="0608f-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="0608f-117">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0608f-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0608f-118">转到**Microsoft 团队和业务管理中心的 Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-118">Go to **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0608f-119">在左侧导航窗格中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0608f-120">要查看的左侧导航中的业务管理中心 Skype 中的**语音**选项，您必须先购买一个**电话系统**加载项许可证或一个**音频会议**加载项许可证至少一个**企业 E5 许可证**。</span><span class="sxs-lookup"><span data-stu-id="0608f-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="0608f-121">在" **语音用户**"页面上，查找并选择要为其分配电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0608f-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="0608f-122">在"操作"窗格中，单击" **分配号码**"。</span><span class="sxs-lookup"><span data-stu-id="0608f-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="0608f-123">在**选择要分配的号码**列表中**分配号码**页上，选择用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0608f-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0608f-124">如果您看不到列出任何电话号码，您需要[获取电话号码为用户](getting-phone-numbers-for-your-users.md)首次。</span><span class="sxs-lookup"><span data-stu-id="0608f-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](getting-phone-numbers-for-your-users.md) first.</span></span> <span data-ttu-id="0608f-125">或者，如果使用 **Skype for Business 管理中心** > **语音** > **电话号码**页面，可单击**添加**，然后单击**新用户号码**。</span><span class="sxs-lookup"><span data-stu-id="0608f-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="0608f-126">分配或更改紧急关联的地址，在下，**选择验证紧急位置**，从列表中选择位置或者，如果您有多个定义的位置，在搜索框中输入市/县的名称并单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="0608f-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="0608f-127">在选择电话号码和紧急位置之后，请单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0608f-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0608f-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="0608f-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="0608f-131">更改用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="0608f-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="0608f-132">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="0608f-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="0608f-133">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0608f-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0608f-134">转到**Microsoft 团队和业务管理中心的 Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-134">Go to **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0608f-135">在左侧导航窗格中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="0608f-136">在" **语音用户**"页面上，查找并选择要更改其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0608f-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="0608f-137">在操作窗格中，在**已分配号码**下单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="0608f-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="0608f-138">在" **分配号码**"页面上，单击" **更改号码**"。</span><span class="sxs-lookup"><span data-stu-id="0608f-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="0608f-139">在" **分配号码**"页面上的" **选择要分配的号码**"下，使用列表选择新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0608f-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="0608f-140">要更改的相关联的紧急地址，请单击**更改位置**，然后下**更改紧急地址**，或者位置从列表中选择或者，如果您有多个定义的位置，在搜索框中输入市/县的名称，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="0608f-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="0608f-141">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0608f-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="0608f-142">删除用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="0608f-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="0608f-143">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="0608f-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="0608f-144">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0608f-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0608f-145">转到**Microsoft 团队和业务管理中心的 Skype** > **旧门户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-145">Go to **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="0608f-146">在左侧导航窗格中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="0608f-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="0608f-147">在" **语音用户**"页面上，查找并选择要删除其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="0608f-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="0608f-148">在操作窗格下**已分配的号码**，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="0608f-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="0608f-149">在" **要删除选定的已分配号码吗?**" 页面上，单击" **是**"。</span><span class="sxs-lookup"><span data-stu-id="0608f-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="0608f-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="0608f-150">Related topics</span></span>
[<span data-ttu-id="0608f-151">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="0608f-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="0608f-152">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="0608f-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="0608f-153">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="0608f-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="0608f-154">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0608f-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 