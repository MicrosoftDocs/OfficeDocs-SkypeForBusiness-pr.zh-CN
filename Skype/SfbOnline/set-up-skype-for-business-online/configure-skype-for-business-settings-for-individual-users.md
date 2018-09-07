---
title: 管理员：为单个用户配置 Skype for Business 设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
ms.openlocfilehash: 1296ec96d194be80ae3c48a947a0398f0eefb4e3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860326"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="99d08-103">管理员：为单个用户配置 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="99d08-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="99d08-104">本文介绍了管理员如何为少量用户配置 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="99d08-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="99d08-105">为了执行这些步骤批量，我们提供了您可以使用 Windows PowerShell cmdlet 的链接。</span><span class="sxs-lookup"><span data-stu-id="99d08-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="99d08-106">要允许（或阻止）企业中的所有人与外部人员通信，请参阅：</span><span class="sxs-lookup"><span data-stu-id="99d08-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="99d08-107">[允许用户与外部业务用户的 Skype](allow-users-to-contact-external-skype-for-business-users.md)： 您可以让您的组织使用高级 Skype 业务功能 （共享桌面，外观 who is online 等） 与特定的人员通信受信任 （联盟） 的业务。</span><span class="sxs-lookup"><span data-stu-id="99d08-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="99d08-108">文章还说明了如何阻止与特定域进行通信。</span><span class="sxs-lookup"><span data-stu-id="99d08-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="99d08-109">[适用于业务用户允许 Skype 添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="99d08-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="99d08-110">可以让你的组织使用 Skype for Business 搜索使用 Skype 这一免费应用的用户，并向其发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="99d08-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="99d08-111">为一个用户配置常规设置</span><span class="sxs-lookup"><span data-stu-id="99d08-111">Configure general settings for one user</span></span>
<span data-ttu-id="99d08-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="99d08-112"></span></span>

<span data-ttu-id="99d08-113">您必须具有[管理员权限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="99d08-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="99d08-114">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="99d08-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="99d08-115">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="99d08-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="99d08-116">Choose **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="99d08-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="99d08-117">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="99d08-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="99d08-119">选择要编辑的用户。</span><span class="sxs-lookup"><span data-stu-id="99d08-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="99d08-120">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="99d08-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="99d08-122">在" **常规**"选项页面上，选中或清除想要更改的功能旁边的复选框，然后选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="99d08-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="99d08-123">**选项**</span><span class="sxs-lookup"><span data-stu-id="99d08-123">**Option**</span></span>|<span data-ttu-id="99d08-124">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="99d08-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99d08-125">音频和 HD 视频</span><span class="sxs-lookup"><span data-stu-id="99d08-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="99d08-126">允许此人记录音频会议、音频和视频会议或不允许他们安排任何会议（无）。</span><span class="sxs-lookup"><span data-stu-id="99d08-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="99d08-127">录制对话和会议</span><span class="sxs-lookup"><span data-stu-id="99d08-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="99d08-128">选择此人可以记录的内容。</span><span class="sxs-lookup"><span data-stu-id="99d08-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="99d08-129">此选项不可用的业务基本 Skype。</span><span class="sxs-lookup"><span data-stu-id="99d08-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="99d08-130">为了符合规范，请禁用非存档功能</span><span class="sxs-lookup"><span data-stu-id="99d08-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="99d08-131">如果法律要求你以电子形式存储信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="99d08-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="99d08-132">选择此选项会关闭后[就地保留](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)在 Exchange 管理中心设置不会捕获的功能。</span><span class="sxs-lookup"><span data-stu-id="99d08-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="99d08-133">将关闭以下功能：</span><span class="sxs-lookup"><span data-stu-id="99d08-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="99d08-134">使用即时消息传输文件</span><span class="sxs-lookup"><span data-stu-id="99d08-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="99d08-135">共享 OneNote 页面</span><span class="sxs-lookup"><span data-stu-id="99d08-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="99d08-136">PowerPoint 批注</span><span class="sxs-lookup"><span data-stu-id="99d08-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="99d08-p105">要批量配置这些设置，请使用 PowerShell。请参阅[在 Skype for Business Online 中管理策略](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="99d08-p105">To configure these settings in bulk, use PowerShell. See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="99d08-139">阻止外部通信</span><span class="sxs-lookup"><span data-stu-id="99d08-139">Block external communications</span></span>
<span data-ttu-id="99d08-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="99d08-140"></span></span>

<span data-ttu-id="99d08-141">为公司中的所有人[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)后，你可以使用这些步骤选择性地阻止指定个人与外部的通信。</span><span class="sxs-lookup"><span data-stu-id="99d08-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="99d08-142">选择**用户**，选择您想要禁用，其设置的用户，然后选择**编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。</span><span class="sxs-lookup"><span data-stu-id="99d08-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="99d08-143">选择" **外部通信**"，然后根据需要清除选项：</span><span class="sxs-lookup"><span data-stu-id="99d08-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="99d08-144">**外部 Skype for Business 用户**：如果不希望这些用户与联盟域中的 Skype for Business 用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="99d08-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="99d08-145">**外部 Skype 用户**：如果不希望这些用户与使用免费 Skype 应用的用户通信，请清除此框。</span><span class="sxs-lookup"><span data-stu-id="99d08-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="99d08-146">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="99d08-146">Click **Save**.</span></span>
    
<span data-ttu-id="99d08-p106">要批量配置这些设置，请使用 PowerShell。请参阅[在 Skype for Business Online 中管理与外部用户和组织的通信](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="99d08-p106">To configure these settings in bulk, use PowerShell. See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="99d08-149">编辑一个用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="99d08-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="99d08-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="99d08-150"></span></span>

1. <span data-ttu-id="99d08-151">选择**用户**中，选择想要编辑其音频会议设置的用户，再选择**编辑**![编辑](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)。</span><span class="sxs-lookup"><span data-stu-id="99d08-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="99d08-152">选择**音频会议**，选择您的音频会议提供商，键入或更改请求的信息，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="99d08-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="99d08-153">**音频会议设置**</span><span class="sxs-lookup"><span data-stu-id="99d08-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="99d08-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="99d08-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99d08-155">**提供程序名称**</span><span class="sxs-lookup"><span data-stu-id="99d08-155">**Provider name**</span></span> <br/> |<span data-ttu-id="99d08-156">从列表中选择您的提供商。</span><span class="sxs-lookup"><span data-stu-id="99d08-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="99d08-157">**长途电话号码**（必需）</span><span class="sxs-lookup"><span data-stu-id="99d08-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="99d08-158">对于第三方 ACP，这些电话号码是从音频会议提供商那里收到的起来。</span><span class="sxs-lookup"><span data-stu-id="99d08-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="99d08-159">如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。</span><span class="sxs-lookup"><span data-stu-id="99d08-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="99d08-160">设置的数字格式如您所愿 Skype 中显示的业务和 Microsoft 团队会议请求。</span><span class="sxs-lookup"><span data-stu-id="99d08-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="99d08-161">**免费电话号码**</span><span class="sxs-lookup"><span data-stu-id="99d08-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="99d08-162">对于第三方 ACP，这些电话号码是从音频会议提供商那里收到的起来。</span><span class="sxs-lookup"><span data-stu-id="99d08-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="99d08-163">如果用户正在使用 Microsoft 作为音频会议提供商，则这些将是在音频会议桥上设置的数字。</span><span class="sxs-lookup"><span data-stu-id="99d08-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="99d08-164">设置的数字格式如您所愿 Skype 中显示的业务和 Microsoft 团队会议请求。</span><span class="sxs-lookup"><span data-stu-id="99d08-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="99d08-165">**会议 ID 和 PIN**（必需）</span><span class="sxs-lookup"><span data-stu-id="99d08-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="99d08-166">参与者的 PIN 或会议使用的代码，加入由此用户计划和从第三方音频会议提供商提供的会议。</span><span class="sxs-lookup"><span data-stu-id="99d08-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="99d08-167">如果用户正在使用 Microsoft 作为音频会议提供商，这不是必需。</span><span class="sxs-lookup"><span data-stu-id="99d08-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="99d08-168">若要在批量中配置这些设置，使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="99d08-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="99d08-169">请参阅[设置的电话号码包含在邀请](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="99d08-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="99d08-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="99d08-170">Related topics</span></span> 

[<span data-ttu-id="99d08-171">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="99d08-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="99d08-172">Skype for Business 和 Microsoft Teams 外接程序许可</span><span class="sxs-lookup"><span data-stu-id="99d08-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 