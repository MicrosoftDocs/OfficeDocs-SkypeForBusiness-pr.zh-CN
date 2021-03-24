---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093386"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="0a5f7-103">管理员：为单个用户配置 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="0a5f7-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a5f7-104">Microsoft Teams 管理中心已取代 Skype for Business 管理中心 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="0a5f7-105">管理 Skype for Business 的所有设置现在都位于 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="0a5f7-106">必须分配全局管理员或 Skype for Business 管理员 [的 Azure AD](/azure/active-directory/roles/permissions-reference) 管理员角色，才能在 Teams 管理中心管理 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="0a5f7-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="0a5f7-108">本文介绍了管理员如何为少量用户配置 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="0a5f7-109">为了批量执行这些步骤，我们包含了指向Windows PowerShell cmdlet 的链接。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="0a5f7-110">要允许（或阻止）企业中的所有人与外部人员通信，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0a5f7-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="0a5f7-111">允许用户联系外部[Skype for Business](allow-users-to-contact-external-skype-for-business-users.md)用户：你可以让你的组织使用高级 Skype for Business 功能 (共享桌面、查找在线人员等 ) 以与特定受信任的 (联合) 企业中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="0a5f7-112">本文还介绍了如何阻止与特定域的通信。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="0a5f7-113">[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="0a5f7-114">可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="0a5f7-115">为一个用户配置常规设置</span><span class="sxs-lookup"><span data-stu-id="0a5f7-115">Configure general settings for one user</span></span>
<span data-ttu-id="0a5f7-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5f7-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="0a5f7-117">必须具有管理员 [权限才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="0a5f7-118">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="0a5f7-119">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="0a5f7-120">选择 **管理中心** > **Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0a5f7-121">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="0a5f7-123">选择要编辑的用户。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="0a5f7-124">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="0a5f7-126">在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="0a5f7-127">**选项**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-127">**Option**</span></span>|<span data-ttu-id="0a5f7-128">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a5f7-129">音频和 HD 视频</span><span class="sxs-lookup"><span data-stu-id="0a5f7-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="0a5f7-130">允许此人录制音频会议、音频和视频会议，或不允许他们安排任何会议， (会议) 。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="0a5f7-131">录制对话和会议</span><span class="sxs-lookup"><span data-stu-id="0a5f7-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="0a5f7-132">选择此人可以记录的内容。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="0a5f7-133">此选项不适用于 Skype for Business Basic。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="0a5f7-134">为了符合规范，请禁用非存档功能</span><span class="sxs-lookup"><span data-stu-id="0a5f7-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="0a5f7-135">如果法律要求你以电子形式存储信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="0a5f7-136">选择此选项会关闭在 Exchange 管理中心设置就地保留时未捕获[](/exchange/security-and-compliance/in-place-and-litigation-holds)的功能。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="0a5f7-137">将关闭以下功能：</span><span class="sxs-lookup"><span data-stu-id="0a5f7-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="0a5f7-138">使用即时消息传输文件</span><span class="sxs-lookup"><span data-stu-id="0a5f7-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="0a5f7-139">共享 OneNote 页面</span><span class="sxs-lookup"><span data-stu-id="0a5f7-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="0a5f7-140">PowerPoint 批注</span><span class="sxs-lookup"><span data-stu-id="0a5f7-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="0a5f7-141">若要批量配置这些设置，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0a5f7-142">请参阅[为计算机设置 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0a5f7-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="0a5f7-143">阻止外部通信</span><span class="sxs-lookup"><span data-stu-id="0a5f7-143">Block external communications</span></span>
<span data-ttu-id="0a5f7-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5f7-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="0a5f7-145">为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="0a5f7-146">选择 **"** 用户"，选择要禁用其设置的用户，然后选择" **编辑编辑** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) "。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="0a5f7-147">选择" **外部通信**"，然后根据需要清除选项：</span><span class="sxs-lookup"><span data-stu-id="0a5f7-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="0a5f7-148">**外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="0a5f7-149">**外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="0a5f7-150">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-150">Click **Save**.</span></span>
    
<span data-ttu-id="0a5f7-151">若要批量配置这些设置，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0a5f7-152">请参阅[为计算机设置 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0a5f7-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="0a5f7-153">编辑一个用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="0a5f7-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="0a5f7-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="0a5f7-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="0a5f7-155">选择 **"** 用户"，选择要编辑其音频会议设置的用户，然后选择"编辑 **编辑** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) "。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="0a5f7-156">选择 **"音频会议"，** 选择音频会议提供商，键入或更改请求的信息，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="0a5f7-157">**音频会议设置**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="0a5f7-158">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a5f7-159">**提供程序名称**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-159">**Provider name**</span></span> <br/> |<span data-ttu-id="0a5f7-160">从列表中选择提供商。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="0a5f7-161">**长途电话号码**（必需）</span><span class="sxs-lookup"><span data-stu-id="0a5f7-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="0a5f7-162">对于第三方 ACP，这些电话号码是音频会议提供商提供的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="0a5f7-163">如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="0a5f7-164">设置号码的格式，因为您希望它们显示在 Skype for Business 和 Microsoft Teams 会议请求中。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="0a5f7-165">**免费电话号码**</span><span class="sxs-lookup"><span data-stu-id="0a5f7-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="0a5f7-166">对于第三方 ACP，这些电话号码是音频会议提供商提供的电话号码。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="0a5f7-167">如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="0a5f7-168">设置号码的格式，因为您希望它们显示在 Skype for Business 和 Microsoft Teams 会议请求中。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="0a5f7-169">**会议 ID 和 PIN** (必需) </span><span class="sxs-lookup"><span data-stu-id="0a5f7-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="0a5f7-170">参与者 PIN 或会议代码，用于加入由此用户安排并且由第三方音频会议提供商提供的会议。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="0a5f7-171">如果用户使用 Microsoft 作为音频会议提供商，则不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="0a5f7-172">若要批量配置这些设置，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0a5f7-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0a5f7-173">请参阅[设置邀请中包含的电话号码](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[设置计算机以Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0a5f7-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="0a5f7-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a5f7-174">Related topics</span></span> 

[<span data-ttu-id="0a5f7-175">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0a5f7-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0a5f7-176">Skype for Business 和 Microsoft Teams 加载项许可</span><span class="sxs-lookup"><span data-stu-id="0a5f7-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
