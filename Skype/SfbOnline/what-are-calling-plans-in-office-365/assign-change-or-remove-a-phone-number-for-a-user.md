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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 了解如何给 Skype for Business 用户分配、更改或删除工作电话号码，以便外部业务和客户能呼入。
ms.openlocfilehash: 8c80bf9da5471f1a7293a01ed9e2d56f6e1aa15b
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780936"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="2b2ea-103">为用户分配、更改或删除电话号码</span><span class="sxs-lookup"><span data-stu-id="2b2ea-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="2b2ea-104">在 Office 365 中设置呼叫套餐时，你可以给用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-104">When you set up Calling Plans in Office 365, you will need to assign a phone number and emergency address to each of your users.</span></span> 

<span data-ttu-id="2b2ea-105">在 Microsoft Teams 客户端，当用户单击**呼叫**时，就会列出你分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![显示在 Microsoft Teams 中的用户电话号码。](../images/teams-phone-number.png)

<span data-ttu-id="2b2ea-107">在 Skype for Business 客户端，你分配的电话号码将在**工作电话**框中列出，用户无法更改此号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-107">The phone number you assign will be listed in the **This Work Phone** box in their Skype for Business client and can't be changed by a user.</span></span>
  
![工作电话号码将处于灰显状态。](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="2b2ea-109">如果用户想要[更改其 Skype for Business 的电话号码](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e)，而 Skype for Business 应用中的电话号码无法更改或处于灰显状态，这表示该号码是由管理员为其设置的，用户无法更改。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-109">If they want to [Change my phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) ** and the phone number in the Skype for Business app can't be changed or is grayed out**, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="2b2ea-110">在设置用户以便他们拨打和接听电话呼叫时，你必须先使用 Skype for Business 管理中心并分配电话号码，但必要时，你可以更改或删除电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="2b2ea-111">若要了解如何获取 Office 365 中的通话套餐以及它们的价格，请参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b2ea-112">一种查看用户是否已分配许可证的方法是，转到 **Skype for Business 管理中心** > **语音** > **语音用户**，然后选择此用户。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-112">One way to see if a user has a license assigned is in the **Skype for Business admin center** > **Voice** > **Voice users** and select the user.</span></span> <span data-ttu-id="2b2ea-113">如果已分配许可证，则会在**分配的许可证**下面注明。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-113">If a license is assigned, it will be listed under the **Assigned license**.</span></span> <span data-ttu-id="2b2ea-114">你还可使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-114">You can use the Office 365 admin center though too.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="2b2ea-115">为用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="2b2ea-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="2b2ea-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2b2ea-117">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2b2ea-118">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-118">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="2b2ea-119">在左侧导航中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-119">In the left navigation, **Voice** > **Voice users**.</span></span>
   > [!NOTE]
 <span data-ttu-id="2b2ea-120">若要在 Skype for Business 管理中心的左侧导航中显示**语音**选项，必须先购买至少一个 **Enterprise E5 许可证**、一个**电话系统**附加许可证，或一个**音频会议**附加许可证。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-120">IMPORTANT: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="2b2ea-121">在**语音用户**页面上，查找并选择要为其分配电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="2b2ea-122">在操作窗格中，单击**分配号码**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="2b2ea-123">在**分配号码**页面上的**选择要分配的号码**列表中，为该用户选择电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-123">On the **Assign number** page in the **Select number to assign** list, then select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2b2ea-124">如果发现未列出任何电话号码，必须先[为用户获取电话号码](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-124">If you don't see any phone numbers listed, you need to go Getting Skype for Business phone numbers for your users first or If you use the Skype for Business admin center  Voice  Phone numbers page > click Add then New user numbers.</span></span> <span data-ttu-id="2b2ea-125">或者，如果使用 **Skype for Business 管理中心** > **语音** > **电话号码**页面，可单击**添加**，然后单击**新用户号码**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="2b2ea-126">要在**选择验证紧急位置**下分配或更改相关联的紧急地址，可从列表中选择该位置，或者，如果你拥有很多定义位置，可在搜索框中输入城市名称，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-126">To assign or change the associated emergency address under Select validated emergency location, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
8. <span data-ttu-id="2b2ea-127">在选择电话号码和紧急位置之后，请单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2b2ea-128">由于 Office 365 和 Skype for Business Online 之间的延迟，可能需要长达 24 小时才能为用户启用电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-128">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for user to be enabled.</span></span> <span data-ttu-id="2b2ea-129">如果 24 小时后未正确分配电话号码，请[联系商业产品支持 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-129">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="2b2ea-130">我们随时为你提供帮助！</span><span class="sxs-lookup"><span data-stu-id="2b2ea-130">We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="2b2ea-131">更改用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="2b2ea-131">To change a phone number for a user</span></span>
 
<span data-ttu-id="2b2ea-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2b2ea-133">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2b2ea-134">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-134">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="2b2ea-135">在左侧导航中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-135">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="2b2ea-136">在**语音用户**页面上，查找并选择要更改其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="2b2ea-137">在操作窗格中的**已分配号码**下，单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-137">In the Action pane, under **Assigned number** click **Change number**.</span></span> 
    
6. <span data-ttu-id="2b2ea-138">在**分配号码**页面上，单击**更改号码**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="2b2ea-139">在**分配号码**页面上的**选择要分配的号码**下，使用列表选择新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="2b2ea-140">要更改相关联的紧急地址，请单击**更改位置**，然后在**将紧急地址更改为**下，从列表中选择位置，或者，如果你拥有很多定义位置，请在搜索框中输入城市名称，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-140">To change the associated emergency address click Change location and under Change emergency address to, either select the location from the list or if you have many locations defined put the name of the city in the Search by city box and click Search.</span></span>
    
9. <span data-ttu-id="2b2ea-141">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="2b2ea-142">删除用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="2b2ea-142">To remove a phone number from a user</span></span>
 
<span data-ttu-id="2b2ea-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2b2ea-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="2b2ea-144">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2b2ea-145">转到 **Office 365 管理中心** > **管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-145">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business >Voice**.</span></span>
    
3. <span data-ttu-id="2b2ea-146">在左侧导航中，单击**语音** > **语音用户**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-146">In the left navigation, **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="2b2ea-147">在**语音用户**页面上，查找并选择要删除其电话号码的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="2b2ea-148">在操作窗格中的**分配号码**下，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-148">In the Action pane, under **Assigned number** click **Remove**.</span></span> 
    
6. <span data-ttu-id="2b2ea-149">在**要删除选定的已分配号码吗?** 页面上，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="2b2ea-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="2b2ea-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="2b2ea-150">Related topics</span></span>
[<span data-ttu-id="2b2ea-151">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="2b2ea-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="2b2ea-152">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="2b2ea-152">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="2b2ea-153">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="2b2ea-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="2b2ea-154">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2b2ea-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 