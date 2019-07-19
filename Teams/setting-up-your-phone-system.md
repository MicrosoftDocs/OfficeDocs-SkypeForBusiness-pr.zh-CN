---
title: 设置组织内的电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为你的组织设置电话系统 (云 PBX)。 '
ms.openlocfilehash: 73cae7507a7c9d4dc86ea24de51790d13a32cf27
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793165"
---
# <a name="setting-up-phone-system-in-your-organization"></a><span data-ttu-id="50bdf-103">设置组织内的电话系统</span><span class="sxs-lookup"><span data-stu-id="50bdf-103">Setting up Phone System in your organization</span></span>

<span data-ttu-id="50bdf-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p101">The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="50bdf-106">步骤 1： 请确保您的国家或地区可用使用电话系统</span><span class="sxs-lookup"><span data-stu-id="50bdf-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.  <span data-ttu-id="50bdf-107">首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="50bdf-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.  <span data-ttu-id="50bdf-108">在 **电话系统** ，下查看的功能和详细信息的列表。</span><span class="sxs-lookup"><span data-stu-id="50bdf-108">Under **Phone System**, review the list of features and details.</span></span> 
3.  <span data-ttu-id="50bdf-109">如果可用电话系统，转到步骤 2。</span><span class="sxs-lookup"><span data-stu-id="50bdf-109">If Phone System is available, go to step 2.</span></span> 

<span data-ttu-id="50bdf-110">**若要了解有关电话系统和音频会议的区域可用性的详细信息，请参阅 [国家和地区音频会议和调用计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-110">**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**</span></span>

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="50bdf-111">步骤 2： 购买和分配电话系统和通话套餐许可证</span><span class="sxs-lookup"><span data-stu-id="50bdf-111">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="50bdf-112">若要将电话系统和通话套餐许可证分配给单个用户的步骤与分配 Office 365 许可证相同。</span><span class="sxs-lookup"><span data-stu-id="50bdf-112">To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="50bdf-113">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-113">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="50bdf-114">如果要批量分配多个用户, 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-114">If you want to assign multiple users in bulk, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="50bdf-115">步骤 3: 为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-115">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="50bdf-116">在您可以将组织中的用户设置为拨打和接收电话呼叫之前, 您必须为他们获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-116">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="50bdf-117">有三种方法可为用户获取号码:</span><span class="sxs-lookup"><span data-stu-id="50bdf-117">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="50bdf-118">使用 Skype for Business 管理中心获得新号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-118">Get new numbers using the Skype for Business admin center.</span></span>
- <span data-ttu-id="50bdf-119">获取在Skype for Business管理中心不可用的新号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-119">Get new numbers that aren't available in the Skype for Business admin center.</span></span>
- <span data-ttu-id="50bdf-120">将您的现有服务提供商或电话运营商中的现有号码移植或转移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-120">Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.</span></span>

<span data-ttu-id="50bdf-p103">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p103">You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers"></a><span data-ttu-id="50bdf-123">获取新的用户电话号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-123">Get new user phone numbers</span></span> 
 
<span data-ttu-id="50bdf-124">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="50bdf-124">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="50bdf-125">使用你的工作或学校帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="50bdf-126">转到**Microsoft 365 管理中心** > **Skype for business**。</span><span class="sxs-lookup"><span data-stu-id="50bdf-126">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50bdf-127">在左侧导航中, 转到 "**语音** > **电话号码**", 单击 "**添加新号码" 添加新号码** !["](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)添加" 按钮, 显示为加号, 然后单击 "**新用户号码**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![The Add button, displayed as a plus symbol](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="50bdf-128">获取在Skype for Business管理中心不可用的新号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-128">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="50bdf-p104">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p104">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="50bdf-132">将你的服务提供商或电话运营商提供的电话号码转网或转移</span><span class="sxs-lookup"><span data-stu-id="50bdf-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="50bdf-p105">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p105">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.</span></span>
    
- <span data-ttu-id="50bdf-135">如果您需要移植超过999的电话号码, 请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交 "订单订单服务请求" 或 "订单" 以获取所有这些电话号码均已移植到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365.</span></span> 

<span data-ttu-id="50bdf-136">**有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-136">**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="50bdf-137">步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="50bdf-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="50bdf-p106">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p106">In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers"></a><span data-ttu-id="50bdf-141">获取新服务号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-141">Get new service numbers</span></span>

<span data-ttu-id="50bdf-142">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="50bdf-142">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>


1. <span data-ttu-id="50bdf-143">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-143">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="50bdf-144">转到**Microsoft 365 管理中心** > **Skype for business**。</span><span class="sxs-lookup"><span data-stu-id="50bdf-144">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="50bdf-145">在左侧导航中, 转到 "**语音** > **电话号码** > " 以**添加新号码**, 然后单击 "**新的服务号码**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-145">In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="50bdf-146">要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项, 您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。</span><span class="sxs-lookup"><span data-stu-id="50bdf-146">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a><span data-ttu-id="50bdf-147">获取在Skype for Business管理中心不可用的新号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-147">Get new numbers that aren't available in the Skype for Business admin center</span></span>
  
<span data-ttu-id="50bdf-p107">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p107">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers.</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="50bdf-151">转网或转移现有服务号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-151">Port or transfer existing service numbers</span></span>

<span data-ttu-id="50bdf-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p108">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="50bdf-157">步骤 5： 如果您想要设置调用计划</span><span class="sxs-lookup"><span data-stu-id="50bdf-157">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="50bdf-p109">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p109">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.</span></span>

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a><span data-ttu-id="50bdf-160">为您的组织添加紧急地址和位置</span><span class="sxs-lookup"><span data-stu-id="50bdf-160">Add emergency addresses and locations for your organization</span></span>

1. <span data-ttu-id="50bdf-161">在 "**语音**" 页面上, 选择 "**紧急位置** > **添加新地址**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-161">On the **Voice** page, choose **Emergency locations** > **Add new address**.</span></span>

2. <span data-ttu-id="50bdf-162">在 "**新建地址**" 窗格中, 为您的地址输入一个名称, 然后填写其余的框。</span><span class="sxs-lookup"><span data-stu-id="50bdf-162">In the **New Address** pane, enter a name for your address, and then complete the remaining boxes.</span></span>
    
     ![新地址窗格的屏幕截图](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > <span data-ttu-id="50bdf-164">[!提示] 对于英语客户，如果街道名称是数字，请务必在结尾加上"st"或"th"，如上图所示。</span><span class="sxs-lookup"><span data-stu-id="50bdf-164">For English customers, if the street name is a number, be sure to include "st" or "th" at the end, as shown in the above picture.</span></span>

3. <span data-ttu-id="50bdf-165">选择" **验证**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-165">Choose **Validate**.</span></span>

    <span data-ttu-id="50bdf-166">如果需要，系统将提示你对地址进行更改。</span><span class="sxs-lookup"><span data-stu-id="50bdf-166">If needed, you'll be prompted to make corrections to the address.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="50bdf-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.</span></span>

    > [!TIP]
    > <span data-ttu-id="50bdf-170">[!提示] 如果地址需要更正才能处理紧急响应，系统将显示一个绿色横幅，通知你地址已更新。</span><span class="sxs-lookup"><span data-stu-id="50bdf-170">If the address needs to be corrected for emergency response, a green banner will appear notifying you that the address was updated.</span></span>

4. <span data-ttu-id="50bdf-171">验证地址之后，请选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-171">After the address is validated, choose **Save**.</span></span>

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a><span data-ttu-id="50bdf-172">为用户分配电话号码和紧急地址</span><span class="sxs-lookup"><span data-stu-id="50bdf-172">Assign phone numbers and emergency addresses to users</span></span>

> [!TIP]
> <span data-ttu-id="50bdf-p111">[!提示] 如果在执行此步骤前刚刚向企业添加了更多人员，这些人员可能需要 **几小时** 才会显示在" **语音用户**"页面。 系统存在延迟。</span><span class="sxs-lookup"><span data-stu-id="50bdf-p111">If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page. There's a latency.</span></span>

1. <span data-ttu-id="50bdf-175">在 "**语音用户**" 页面上, 选择要为其分配电话号码和紧急地址的人员。</span><span class="sxs-lookup"><span data-stu-id="50bdf-175">On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.</span></span>

2. <span data-ttu-id="50bdf-176">在"操作"窗格中，单击" **分配号码**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-176">In the Action pane, click **Assign number**.</span></span>

3. <span data-ttu-id="50bdf-177">在 "**分配号码**" 页面上的 "**选择要分配的号码**" 列表中, 选择用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-177">On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.</span></span>

4. <span data-ttu-id="50bdf-178">若要选择紧急地址, 请在框中输入城市的名称, 然后选择 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-178">To select an emergency address, enter name of the city in the box and choose **Search**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="50bdf-p112">If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p112">If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user).</span></span> 
  
5. <span data-ttu-id="50bdf-181">在分配电话号码和紧急地址之后，选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-181">After you assign both the phone number and emergency address, choose **Save**.</span></span>

### <a name="tell-your-users-about-their-new-phone-numbers"></a><span data-ttu-id="50bdf-182">告诉你的用户有关其新电话号码的信息</span><span class="sxs-lookup"><span data-stu-id="50bdf-182">Tell your users about their new phone numbers</span></span>


<span data-ttu-id="50bdf-183">我们建议通过发送邮件或使用企业的首选通信方式，将新电话号码告知用户。</span><span class="sxs-lookup"><span data-stu-id="50bdf-183">We recommend sending mail or using your business's preferred communication method to tell the people about their new phone numbers.</span></span>

<span data-ttu-id="50bdf-184">下面介绍了他们在**Skype For business**应用中可以看到的电话号码:</span><span class="sxs-lookup"><span data-stu-id="50bdf-184">Here's how they can see that phone number in their **Skype for Business** app:</span></span>

1. <span data-ttu-id="50bdf-185">登录到桌面上的 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="50bdf-185">Sign in to Skype for Business on your desktop.</span></span>
    
2. <span data-ttu-id="50bdf-186">选择 **设置** > **工具选项** > **选项**。</span><span class="sxs-lookup"><span data-stu-id="50bdf-186">Choose **Settings** > **Tools** > **Options**.</span></span> 
    
     !["工具" 菜单上选项的屏幕截图](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. <span data-ttu-id="50bdf-188">然后，选择" **电话**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-188">Then choose **Phones**.</span></span> 
    
    ![Skype for Business 电话选项的屏幕截图](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
<span data-ttu-id="50bdf-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p113">In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.</span></span>

![单击 "呼叫" 后可用选项的屏幕截图](media/teams-phone-number.png)

<span data-ttu-id="50bdf-193">**有关设置通话套餐所涉及的所有步骤的更详细信息，请参阅 [设置通话套餐](set-up-calling-plans.md) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-193">**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).**</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="50bdf-194">步骤 6： 如果您想要设置音频会议</span><span class="sxs-lookup"><span data-stu-id="50bdf-194">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="50bdf-p114">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p114">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span>

<span data-ttu-id="50bdf-p115">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p115">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="50bdf-200">有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。</span><span class="sxs-lookup"><span data-stu-id="50bdf-200">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
    
1. <span data-ttu-id="50bdf-201">如果购买了 **音频会议** 外接程序许可证和通信点数许可证，也要分配它们。</span><span class="sxs-lookup"><span data-stu-id="50bdf-201">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="50bdf-202">有关说明, 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-202">For instructions, see [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

    <span data-ttu-id="50bdf-p117">Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span><span class="sxs-lookup"><span data-stu-id="50bdf-p117">Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>

    > [!NOTE]
    > <span data-ttu-id="50bdf-207">Microsoft Teams 用户不能用户第三方音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="50bdf-207">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span>

    - <span data-ttu-id="50bdf-208">**Microsoft 作为您的音频会议提供商**： 如果您希望音频会议的最简单的解决方案，选择 Microsoft 作为您的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="50bdf-208">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
    - <span data-ttu-id="50bdf-p118">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p118">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
 
2. <span data-ttu-id="50bdf-p119">Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p119">Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

3. <span data-ttu-id="50bdf-p120">Set up meeting invitations. The following steps are optional, but a lot of admins like to do them:</span><span class="sxs-lookup"><span data-stu-id="50bdf-p120">Set up meeting invitations. The following steps are optional, but a lot of admins like to do them:</span></span> 
  
   1. <span data-ttu-id="50bdf-215">[在 Skype For business 中自定义会议邀请](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-215">[Customize meeting invitations in Skype for Business](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations).</span></span> <span data-ttu-id="50bdf-216">为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="50bdf-216">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="50bdf-217">但是，你也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。</span><span class="sxs-lookup"><span data-stu-id="50bdf-217">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
   2. <span data-ttu-id="50bdf-218">为在[Skype for](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) Business 或[Microsoft 团队中](set-the-phone-numbers-included-on-invites-in-teams.md)的邀请中包含的会议组织者设置音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-218">Set the Audio Conferencing phone numbers for meeting organizers that are included on invites [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) or [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span> <span data-ttu-id="50bdf-219">这是将在由用户安排的会议中显示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="50bdf-219">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
   3. <span data-ttu-id="50bdf-220">[在 Skype for](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) Business 或[Microsoft 团队](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中为音频会议设置自动助理语言, 音频会议自动助理在拨入音频会议电话号码时使用该功能问候呼叫者。</span><span class="sxs-lookup"><span data-stu-id="50bdf-220">Set auto attendant languages for Audio Conferencing [in Skype for Business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) or [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="50bdf-221">此步骤仅在使用 Microsoft 作为音频会议提供商时适用。</span><span class="sxs-lookup"><span data-stu-id="50bdf-221">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
   4. <span data-ttu-id="50bdf-222">为[Microsoft 团队中](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)的音频会议会议设置 PIN 长度。</span><span class="sxs-lookup"><span data-stu-id="50bdf-222">Set the length of the PIN for Audio Conferencing meetings [in Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="50bdf-p124">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p124">This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span>

<span data-ttu-id="50bdf-225">**有关音频会议的详细信息, 请参阅[设置 Microsoft 团队的音频会议](set-up-audio-conferencing-in-teams.md)。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-225">**For more information about Audio Conferencing, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).**</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="50bdf-226">步骤 7: 要设置云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="50bdf-226">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="50bdf-227">云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能, 以及搜索下一个可用的呼叫代理以处理呼叫, 而通话的人员在保持状态时收听音乐。</span><span class="sxs-lookup"><span data-stu-id="50bdf-227">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="50bdf-228">您可以为您的组织创建单个或多个通话队列。</span><span class="sxs-lookup"><span data-stu-id="50bdf-228">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="50bdf-p126">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p126">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="50bdf-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p127">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="50bdf-234">若要创建新的呼叫队列, 请在**Skype for business 管理中心**中, 单击 "**呼叫路由** > **呼叫队列**", 单击 "**新增**", 然后按照 "[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)" 的**步骤 3**中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="50bdf-234">To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).</span></span>

<span data-ttu-id="50bdf-235">**有关通话队列的详细信息, 请参阅[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-235">**For more details about call queues, see [Create a Cloud call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="50bdf-236">步骤 8: 如果要设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="50bdf-236">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="50bdf-p128">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p128">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.</span></span>

<span data-ttu-id="50bdf-239">若要创建新的自动助理, 请在 Skype for business 管理中心中, 单击 "**呼叫路由** > **自动助理**", 单击 "**添加新**", 然后按照创建云自动助理的**步骤 2**中的每个页面上的说明进行操作。 [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="50bdf-239">To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Create a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).</span></span>


<span data-ttu-id="50bdf-240">**有关云自动助理的更多详细信息, 请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-240">**For more details about Cloud auto attendants, see [Set up a Cloud auto attendant](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**</span></span>

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="50bdf-241">步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）</span><span class="sxs-lookup"><span data-stu-id="50bdf-241">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="50bdf-p129">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="50bdf-p129">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="50bdf-244">对于音频会议, 您可以通过转到**Microsoft 365 管理中心** > **管理中心** > **Skype for business** > **音频会议**, 将专用号码分配给会议网桥, 然后单击您也能[在您的音频会议网桥上更改收费电话号码或免费电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-244">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="50bdf-245">对于自动助理, 你可以通过转到**Microsoft 365 管理中心** > **管理中心** > 的**Skype for** > business**呼叫路由** > **自动助理, 将专用号码分配给自动助理**并单击 "自动助理"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-245">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant.</span></span> <span data-ttu-id="50bdf-246">在 **常规** 页上您已经拥有的服务号码将在 **电话号码** 中下拉列表中列出。</span><span class="sxs-lookup"><span data-stu-id="50bdf-246">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="50bdf-247">有关详细信息, 请参阅[设置云自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-247">For details, see [Set up a Cloud Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).</span></span>

- <span data-ttu-id="50bdf-248">对于呼叫队列, 您可以通过转到**Microsoft 365 管理中心** > **管理中心** > **Skype for** > business**呼叫路由** > **呼叫队列**, 将专用号码分配给呼叫队列, 然后单击通话队列。</span><span class="sxs-lookup"><span data-stu-id="50bdf-248">For Call Queues, you can assign a dedicated number to a call queue by going to **Microsoft 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue.</span></span> <span data-ttu-id="50bdf-249">在  **常规** 页上您已经拥有的服务号码将在 **电话号码** 中下拉列表中列出。</span><span class="sxs-lookup"><span data-stu-id="50bdf-249">On the **General** page the service number you already have will be listed in the **Phone number** drop down.</span></span> <span data-ttu-id="50bdf-250">有关详细信息, 请参阅[创建云呼叫队列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="50bdf-250">For details, see [Create a Cloud call queue](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).</span></span>

<span data-ttu-id="50bdf-251">**有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](/microsoftteams/getting-service-phone-numbers) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-251">**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).**</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="50bdf-252">步骤 10: 为你的组织设置通讯信用点数</span><span class="sxs-lookup"><span data-stu-id="50bdf-252">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="50bdf-p132">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="50bdf-p132">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="50bdf-258">若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。</span><span class="sxs-lookup"><span data-stu-id="50bdf-258">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span>

### <a name="to-set-up-communications-credits"></a><span data-ttu-id="50bdf-259">设置通信点数</span><span class="sxs-lookup"><span data-stu-id="50bdf-259">To set up Communications Credits</span></span>

1. <span data-ttu-id="50bdf-260">使用你的工作或学校帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-260">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="50bdf-261">在管理中心的左侧导航中, 转到 "**计费** > **订阅** > **加载项** > **购买加载项**", 然后选择 "**立即购买**的**通讯点数** > "。</span><span class="sxs-lookup"><span data-stu-id="50bdf-261">In the left navigation of the admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>

3. <span data-ttu-id="50bdf-262">在**通信点数**订阅页中，填写您的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="50bdf-262">On the **Communications Credits** subscription page, fill in your information, and then click **Next**.</span></span>

4. <span data-ttu-id="50bdf-263">输入您的付款信息并单击 **下订单** 。</span><span class="sxs-lookup"><span data-stu-id="50bdf-263">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="50bdf-p133">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span><span class="sxs-lookup"><span data-stu-id="50bdf-p133">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="50bdf-267">**有关通信点数设置的详细信息，请参阅 [为您的组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-267">**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>
  
### <a name="assign-a-communications-credits-license-to-users"></a><span data-ttu-id="50bdf-268">将通信点数许可证分配给用户</span><span class="sxs-lookup"><span data-stu-id="50bdf-268">Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="50bdf-269">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="50bdf-269">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="50bdf-270">在 Microsoft 365 管理中心的左侧导航中, 转到 "**用户** > **活动用户**", 然后从列表中选择一个或一个用户。</span><span class="sxs-lookup"><span data-stu-id="50bdf-270">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>

3. <span data-ttu-id="50bdf-271">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-271">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="50bdf-272">在 "**产品许可证**" 页面上, 将 "**通信信用点数**" 切换到 **"开"** 以分配此许可证, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="50bdf-272">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50bdf-273">即使你有分配了**企业版 E5**许可证的用户, 仍建议你执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50bdf-273">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

<span data-ttu-id="50bdf-274">**若要了解有关分配通信点数许可证的详细信息，请参阅 [为您的组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。**</span><span class="sxs-lookup"><span data-stu-id="50bdf-274">**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).**</span></span>

## <a name="related-topics"></a><span data-ttu-id="50bdf-275">相关主题</span><span class="sxs-lookup"><span data-stu-id="50bdf-275">Related topics</span></span>
[<span data-ttu-id="50bdf-276">以下是 Office 365 中的电话系统功能</span><span class="sxs-lookup"><span data-stu-id="50bdf-276">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="50bdf-277">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="50bdf-277">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="50bdf-278">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="50bdf-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
