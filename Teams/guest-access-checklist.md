---
title: Microsoft 团队来宾访问清单
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: 使用此清单可帮助 Microsoft 团队来宾 Access 中的来宾访问设置。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a2ad3c2416e64334dddda6c09d3e8eed2be3763
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374247"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="6d86c-103">团队来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="6d86c-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="6d86c-104">使用此清单可帮助您启用和配置中的 Microsoft 团队的来宾访问功能，根据组织的首选项。</span><span class="sxs-lookup"><span data-stu-id="6d86c-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="6d86c-105">在租户级别的 □ 启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="6d86c-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="6d86c-106">至少，您必须打开的所有用户的许可证类型**来宾**Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="6d86c-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="6d86c-107">有关详细说明，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![屏幕快照显示了工作组设置切换的示例](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="6d86c-109">□ 启用渠道的特定设置</span><span class="sxs-lookup"><span data-stu-id="6d86c-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="6d86c-110">中的团队应用程序，在各个团队级别配置来宾权限，以便来宾可以创建、 更新和删除通道。</span><span class="sxs-lookup"><span data-stu-id="6d86c-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="6d86c-111">除了 admins 团队所有者可以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="6d86c-111">In addition to admins,  team owners can configure this setting.</span></span>

![屏幕快照显示了工作组/通道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="6d86c-113">有关详细信息，包括操作方法视频，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="6d86c-114">□ 配置 Office 365 中共享</span><span class="sxs-lookup"><span data-stu-id="6d86c-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="6d86c-115">□ 确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="6d86c-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="6d86c-116">下面是如何：</span><span class="sxs-lookup"><span data-stu-id="6d86c-116">Here's how:</span></span>

1. <span data-ttu-id="6d86c-117">在 Office 365 管理中心，转到**设置** > **安全性和隐私**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="6d86c-118">![屏幕快照显示了服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="6d86c-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="6d86c-119">在**共享**，选择**编辑**。![屏幕快照显示了共享设置编辑按钮的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="6d86c-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="6d86c-120">设置**让用户将添加到此组织的新来宾**为**上**，，然后单击**保存**。![屏幕快照显示了共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="6d86c-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="6d86c-121">此设置等同于在用户设置中的**成员可以邀请**设置 > Azure AD 中的外部用户。</span><span class="sxs-lookup"><span data-stu-id="6d86c-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="6d86c-122">□ 配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="6d86c-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="6d86c-123">在 Office 365 管理中心，转到**设置** > **服务和加载项** > **Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="6d86c-124">请确保**让外部组织的访问组内容的组成员**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="6d86c-125">如果此设置处于关闭，来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="6d86c-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="6d86c-126">请确保**让组添加到组组织外部的人员的所有者**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="6d86c-127">如果此设置处于关闭，团队所有者将无法添加新的来宾。</span><span class="sxs-lookup"><span data-stu-id="6d86c-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="6d86c-128">至少，此设置必须为"开"以支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="6d86c-128">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="6d86c-129">有关配置这些设置的详细说明，请参阅部分[中的 Microsoft 团队的授权来宾访问](Teams-dependencies.md)和[允许/阻止来宾访问到 Office 365 组](https://go.microsoft.com/fwlink/?linkid=869658)中的"Office 365 组"。</span><span class="sxs-lookup"><span data-stu-id="6d86c-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="6d86c-130">□ Azure AD 业务对企业 (B2B) 中的配置设置</span><span class="sxs-lookup"><span data-stu-id="6d86c-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="6d86c-131">登录到https://portal.azure.com。</span><span class="sxs-lookup"><span data-stu-id="6d86c-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="6d86c-132">单击左侧窗格中的**Azure Active directory** 。</span><span class="sxs-lookup"><span data-stu-id="6d86c-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="6d86c-133">在**管理**下单击**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="6d86c-134">在**外部用户**，下单击**管理外部协作设置**</span><span class="sxs-lookup"><span data-stu-id="6d86c-134">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="6d86c-135">在**外部协作设置**页中，确保**成员可以邀请**设置为**是**。![屏幕快照显示了 AAD 设置切换的示例。</span><span class="sxs-lookup"><span data-stu-id="6d86c-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="6d86c-136">至少支持来宾 ►，**可以邀请成员**必须设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-136">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> > <span data-ttu-id="6d86c-137">如果设置为**否**的**成员可以邀请**并启用来宾访问 Office 365 组和 Microsoft 团队中的，管理员可以控制来宾邀请到您的目录。</span><span class="sxs-lookup"><span data-stu-id="6d86c-137">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="6d86c-138">来宾目录中后，他们可以由非管理员成员 （团队所有者） 添加到团队。</span><span class="sxs-lookup"><span data-stu-id="6d86c-138">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="6d86c-139">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="6d86c-140">在 SharePoint 中的 □ 验证共享设置</span><span class="sxs-lookup"><span data-stu-id="6d86c-140">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="6d86c-141">登录 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6d86c-141">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="6d86c-142">单击**管理中心**，然后选择**SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-142">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="6d86c-143">在 SharePoint 管理中心中，选择**共享**。</span><span class="sxs-lookup"><span data-stu-id="6d86c-143">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="6d86c-144">请确保选项*未*选中的**不允许共享您的组织外部**。![屏幕快照显示了 Sparepoint 在线设置切换的示例。</span><span class="sxs-lookup"><span data-stu-id="6d86c-144">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="6d86c-145">□ 验证帐户许可证和类型</span><span class="sxs-lookup"><span data-stu-id="6d86c-145">□ Verify account licenses and types</span></span>

- <span data-ttu-id="6d86c-146">**帐户许可团队**： 根中一些其他 Office 365 租户中的实际用户帐户是"来宾"帐户，真实的用户帐户必须团队获得许可"来宾"。</span><span class="sxs-lookup"><span data-stu-id="6d86c-146">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="6d86c-147">**帐户必须是 Office 365 学校或工作帐户或 MSA 帐户**： 目前，可以作为来宾用户添加具有与 Azure Active Directory、 Office 365 工作或学校帐户或 Microsoft 帐户 (MSA) 对应的电子邮件地址的用户。</span><span class="sxs-lookup"><span data-stu-id="6d86c-147">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="6d86c-148">□ 配置环境</span><span class="sxs-lookup"><span data-stu-id="6d86c-148">□ Configure environment</span></span>


<span data-ttu-id="6d86c-149">如果宿主租户需要使用多因素身份验证 (MFA) 所需来宾。</span><span class="sxs-lookup"><span data-stu-id="6d86c-149">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="6d86c-150">有关详细信息，请参阅[标识模型和 Microsoft 团队中的身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-150">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="6d86c-151">来宾 □ 了解限制</span><span class="sxs-lookup"><span data-stu-id="6d86c-151">□ Understand limitations for guests</span></span>

<span data-ttu-id="6d86c-152">来宾体验设计具有限制。</span><span class="sxs-lookup"><span data-stu-id="6d86c-152">The guest experience has limitations by design.</span></span> <span data-ttu-id="6d86c-153">请确保您了解来宾体验，以便不尝试修复内容不是问题。</span><span class="sxs-lookup"><span data-stu-id="6d86c-153">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="6d86c-154">例如，下面是功能的一些不可来宾中的 Microsoft 团队列表：</span><span class="sxs-lookup"><span data-stu-id="6d86c-154">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="6d86c-155">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="6d86c-155">OneDrive for Business</span></span>
- <span data-ttu-id="6d86c-156">团队之外人员搜索</span><span class="sxs-lookup"><span data-stu-id="6d86c-156">People search outside of Teams</span></span>
- <span data-ttu-id="6d86c-157">日历、 计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="6d86c-157">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="6d86c-158">PSTN</span><span class="sxs-lookup"><span data-stu-id="6d86c-158">PSTN</span></span>
- <span data-ttu-id="6d86c-159">组织结构图</span><span class="sxs-lookup"><span data-stu-id="6d86c-159">Organization chart</span></span>
- <span data-ttu-id="6d86c-160">创建或修改团队</span><span class="sxs-lookup"><span data-stu-id="6d86c-160">Create or revise a team</span></span>
- <span data-ttu-id="6d86c-161">浏览团队</span><span class="sxs-lookup"><span data-stu-id="6d86c-161">Browse for a team</span></span>
- <span data-ttu-id="6d86c-162">将文件上载到个人到个人聊天</span><span class="sxs-lookup"><span data-stu-id="6d86c-162">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="6d86c-163">有关详细信息，请参阅[新增的来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-163">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="6d86c-164">疑难解答</span><span class="sxs-lookup"><span data-stu-id="6d86c-164">Troubleshooting</span></span>

<span data-ttu-id="6d86c-165">如果您遇到的 Microsoft 团队中添加来宾问题，请参阅[来宾访问疑难解答指南 》](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="6d86c-165">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


