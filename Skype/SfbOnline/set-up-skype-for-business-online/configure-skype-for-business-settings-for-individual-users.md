---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 930960117a46639e86ed2d24c286a5270b21acb9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="66133-103">管理员：为单个用户配置 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="66133-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="66133-104">本文介绍了管理员如何为少量用户配置 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="66133-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="66133-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span><span class="sxs-lookup"><span data-stu-id="66133-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="66133-106">要允许（或阻止）企业中的所有人与外部人员通信，请参阅：</span><span class="sxs-lookup"><span data-stu-id="66133-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="66133-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span><span class="sxs-lookup"><span data-stu-id="66133-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="66133-108">The article also explains how to block communication with specific domains.</span><span class="sxs-lookup"><span data-stu-id="66133-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="66133-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="66133-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="66133-110">可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="66133-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="66133-111">为一个用户配置常规设置</span><span class="sxs-lookup"><span data-stu-id="66133-111">Configure general settings for one user</span></span>
<span data-ttu-id="66133-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="66133-112"></span></span>

<span data-ttu-id="66133-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span><span class="sxs-lookup"><span data-stu-id="66133-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="66133-114">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="66133-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="66133-115">Choose **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="66133-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="66133-116">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="66133-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="66133-118">选择要编辑的用户。</span><span class="sxs-lookup"><span data-stu-id="66133-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="66133-119">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="66133-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="66133-121">在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="66133-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="66133-122">**选项**</span><span class="sxs-lookup"><span data-stu-id="66133-122">**Option**</span></span>|<span data-ttu-id="66133-123">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="66133-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66133-124">音频和 HD 视频</span><span class="sxs-lookup"><span data-stu-id="66133-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="66133-125">允许此人记录音频会议、音频和视频会议或不允许他们安排任何会议（无）。</span><span class="sxs-lookup"><span data-stu-id="66133-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="66133-126">录制对话和会议</span><span class="sxs-lookup"><span data-stu-id="66133-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="66133-127">选择此人可以记录的内容。</span><span class="sxs-lookup"><span data-stu-id="66133-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="66133-128">This option is not available with Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="66133-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="66133-129">为了符合规范，请禁用非存档功能</span><span class="sxs-lookup"><span data-stu-id="66133-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="66133-130">如果法律要求你以电子形式存储信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="66133-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="66133-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="66133-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="66133-132">将关闭以下功能：</span><span class="sxs-lookup"><span data-stu-id="66133-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="66133-133">使用即时消息传输文件</span><span class="sxs-lookup"><span data-stu-id="66133-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="66133-134">共享 OneNote 页面</span><span class="sxs-lookup"><span data-stu-id="66133-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="66133-135">PowerPoint 批注</span><span class="sxs-lookup"><span data-stu-id="66133-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="66133-136">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66133-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="66133-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="66133-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="66133-138">阻止外部通信</span><span class="sxs-lookup"><span data-stu-id="66133-138">Block external communications</span></span>
<span data-ttu-id="66133-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="66133-139"></span></span>

<span data-ttu-id="66133-140">为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。</span><span class="sxs-lookup"><span data-stu-id="66133-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="66133-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="66133-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="66133-142">选择" **外部通信**"，然后根据需要清除选项：</span><span class="sxs-lookup"><span data-stu-id="66133-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="66133-143">**外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="66133-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="66133-144">**外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="66133-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="66133-145">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="66133-145">Click **Save**.</span></span>
    
<span data-ttu-id="66133-146">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66133-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="66133-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="66133-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="66133-148">Edit audio conferencing settings for one user</span><span class="sxs-lookup"><span data-stu-id="66133-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="66133-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="66133-149"></span></span>

1. <span data-ttu-id="66133-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="66133-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="66133-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="66133-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="66133-152">**音频会议设置**</span><span class="sxs-lookup"><span data-stu-id="66133-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="66133-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="66133-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66133-154">**Provider name**</span><span class="sxs-lookup"><span data-stu-id="66133-154">**Provider name**</span></span> <br/> |<span data-ttu-id="66133-155">Choose your provider from the list.</span><span class="sxs-lookup"><span data-stu-id="66133-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="66133-156">**长途电话号码**（必需）</span><span class="sxs-lookup"><span data-stu-id="66133-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="66133-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="66133-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="66133-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="66133-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="66133-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span><span class="sxs-lookup"><span data-stu-id="66133-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="66133-160">**免费电话号码**</span><span class="sxs-lookup"><span data-stu-id="66133-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="66133-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="66133-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="66133-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="66133-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="66133-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span><span class="sxs-lookup"><span data-stu-id="66133-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="66133-164">**Conference ID and PIN** (required)</span><span class="sxs-lookup"><span data-stu-id="66133-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="66133-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="66133-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="66133-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span><span class="sxs-lookup"><span data-stu-id="66133-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="66133-167">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66133-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="66133-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="66133-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="66133-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="66133-169">Related topics</span></span> 

[<span data-ttu-id="66133-170">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="66133-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="66133-171">Skype for Business 和 Microsoft Teams 外接程序许可</span><span class="sxs-lookup"><span data-stu-id="66133-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 