---
title: Microsoft 的团队来宾访问清单
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: 使用此检查表来帮助设置在 Microsoft 小组来宾访问来宾访问权限。
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="0762f-103">团队来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="0762f-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="0762f-104">使用此检查表可帮助您启用和配置 Microsoft 小组在来宾访问功能，根据您的组织的首选项。</span><span class="sxs-lookup"><span data-stu-id="0762f-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="0762f-105">在组织级别 □ 启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="0762f-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="0762f-106">至少，您必须打开所有用户的许可证类型**来宾**Microsoft 小组。</span><span class="sxs-lookup"><span data-stu-id="0762f-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="0762f-107">有关详细说明，请参阅[启用或禁用来宾访问 Microsoft 小组](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="0762f-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![屏幕抓图显示了示例团队设置切换](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="0762f-109">□ 启用特定频道设置</span><span class="sxs-lookup"><span data-stu-id="0762f-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="0762f-110">在团队的应用程序，各个团队级别配置来宾权限以便客人可以创建、 更新和删除频道。</span><span class="sxs-lookup"><span data-stu-id="0762f-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="0762f-111">除了管理员、 团队所有者可以配置该设置。</span><span class="sxs-lookup"><span data-stu-id="0762f-111">In addition to admins,  team owners can configure this setting.</span></span>

![屏幕抓图显示了示例团队/通道设置切换](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="0762f-113">有关详细信息，包括操作方法视频，请参阅[Microsoft 小组中的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0762f-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="0762f-114">□ 配置 Office 365 中共享</span><span class="sxs-lookup"><span data-stu-id="0762f-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="0762f-115">□ 请确保用户可以添加的客人。</span><span class="sxs-lookup"><span data-stu-id="0762f-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="0762f-116">下面是如何：</span><span class="sxs-lookup"><span data-stu-id="0762f-116">Here's how:</span></span>

1. <span data-ttu-id="0762f-117">在 Office 365 管理中心，转到**设置** > **安全和保密**。</span><span class="sxs-lookup"><span data-stu-id="0762f-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="0762f-118">![屏幕抓图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="0762f-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="0762f-119">在**共享**，选择**编辑**。![屏幕抓图显示共享设置编辑按钮的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="0762f-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="0762f-120">设置**允许用户添加为该组织新的来宾**为**上**，，然后单击**保存**。![屏幕抓图显示了一种共享设置切换](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="0762f-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="0762f-121">此设置相当于在用户设置中的**成员可以邀请**设置 > Azure AD 中的外部用户。</span><span class="sxs-lookup"><span data-stu-id="0762f-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="0762f-122">□ 配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="0762f-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="0762f-123">在 Office 365 管理中心，转到**设置** > **服务和加载** > **Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="0762f-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="0762f-124">请确保**让组织访问组内容之外的组成员**被设置为**On**。</span><span class="sxs-lookup"><span data-stu-id="0762f-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="0762f-125">如果此设置处于禁用状态，来宾不能访问组中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="0762f-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="0762f-126">请确保**让组添加到组组织外人员的所有者**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="0762f-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="0762f-127">如果关闭了此设置，则团队所有者将无法添加新的客人。</span><span class="sxs-lookup"><span data-stu-id="0762f-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="0762f-128">（但是，如果管理员已经到 Azure AD 添加来宾用户，然后团队所有者能够将该用户添加到团队。）至少，此设置必须为"on"支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="0762f-128">(However, if an admin had added a guest user to Azure AD, then the Team owner would be able to add that user to the Team.) At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="0762f-129">有关配置这些设置的详细说明，请参阅[Microsoft 小组授权来宾访问](Teams-dependencies.md)和[允许/阻止来宾访问 Office 365 组](https://go.microsoft.com/fwlink/?linkid=869658)中的"Office 365 组"一节。</span><span class="sxs-lookup"><span data-stu-id="0762f-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="0762f-130">□ 在 Azure 广告企业到企业 (B2B) 中的配置设置</span><span class="sxs-lookup"><span data-stu-id="0762f-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="0762f-131">登录到 https://portal.azure.com。</span><span class="sxs-lookup"><span data-stu-id="0762f-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="0762f-132">在左窗格中单击**Azure 活动目录**。</span><span class="sxs-lookup"><span data-stu-id="0762f-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="0762f-133">在**管理**下单击**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="0762f-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="0762f-134">在**外部用户**，请确保**可以邀请成员**设置为**是**。![屏幕抓图显示了 AAD 设置切换的示例。</span><span class="sxs-lookup"><span data-stu-id="0762f-134">In **External users**, make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="0762f-135">► 最少支持的客人，**可以邀请成员**必须设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="0762f-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="0762f-136">如果设置为**否**的**成员可以邀请**并启用 guest 访问 Office 365 组和 Microsoft 小组中的，管理员可以控制来宾邀请到您的目录。</span><span class="sxs-lookup"><span data-stu-id="0762f-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="0762f-137">客人在目录中后，它们可以由非管理员成员 （团队所有者） 添加到团队。</span><span class="sxs-lookup"><span data-stu-id="0762f-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="0762f-138">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="0762f-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="0762f-139">□ 在 SharePoint 中验证共享设置</span><span class="sxs-lookup"><span data-stu-id="0762f-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="0762f-140">登录 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0762f-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="0762f-141">单击**管理中心**，然后选择**SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="0762f-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="0762f-142">在 SharePoint 管理中心中，选择**共享**。</span><span class="sxs-lookup"><span data-stu-id="0762f-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="0762f-143">请确保选择*未*选中的**不允许在您的组织之外共享**。![的屏幕快照演示的 Sparepoint 在线设置切换示例。</span><span class="sxs-lookup"><span data-stu-id="0762f-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="0762f-144">□ 验证帐户许可证和类型</span><span class="sxs-lookup"><span data-stu-id="0762f-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="0762f-145">**帐户工作组授权**： 植根于真实的用户帐户在某些其他 Office 365 租户"Guest"帐户，真实的用户帐户必须授权工作组有关"来宾"。</span><span class="sxs-lookup"><span data-stu-id="0762f-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="0762f-146">**帐户必须是 Office 365 学校或者工作帐户或 MSA 帐户**： 目前，可以作为访客用户添加具有对应于 Azure Active Directory、 Office 365 的工作或学校的帐户，或者 Microsoft 帐户 (MSA) 的电子邮件地址的用户。</span><span class="sxs-lookup"><span data-stu-id="0762f-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="0762f-147">□ 配置环境</span><span class="sxs-lookup"><span data-stu-id="0762f-147">□ Configure environment</span></span>


<span data-ttu-id="0762f-148">客人需要使用多因素身份验证 (MFA) 承载租户的要求。</span><span class="sxs-lookup"><span data-stu-id="0762f-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="0762f-149">有关详细信息，请参阅[标识模型和 Microsoft 小组中的身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="0762f-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="0762f-150">□ 客人了解限制</span><span class="sxs-lookup"><span data-stu-id="0762f-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="0762f-151">访客体验设计上有一定局限性。</span><span class="sxs-lookup"><span data-stu-id="0762f-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="0762f-152">确保您了解访客的经验，所以不要尝试修复不是问题。</span><span class="sxs-lookup"><span data-stu-id="0762f-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="0762f-153">例如，下面是功能的一些来宾在 Microsoft 小组中没有的列表：</span><span class="sxs-lookup"><span data-stu-id="0762f-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="0762f-154">OneDrive 为公司的</span><span class="sxs-lookup"><span data-stu-id="0762f-154">OneDrive for Business</span></span>
- <span data-ttu-id="0762f-155">在团队之外的人搜索</span><span class="sxs-lookup"><span data-stu-id="0762f-155">People search outside of Teams</span></span>
- <span data-ttu-id="0762f-156">日历、 计划的会议或会议的详细信息</span><span class="sxs-lookup"><span data-stu-id="0762f-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="0762f-157">PSTN</span><span class="sxs-lookup"><span data-stu-id="0762f-157">PSTN</span></span>
- <span data-ttu-id="0762f-158">组织结构图</span><span class="sxs-lookup"><span data-stu-id="0762f-158">Organization chart</span></span>
- <span data-ttu-id="0762f-159">创建或修改团队</span><span class="sxs-lookup"><span data-stu-id="0762f-159">Create or revise a team</span></span>
- <span data-ttu-id="0762f-160">浏览一个团队</span><span class="sxs-lookup"><span data-stu-id="0762f-160">Browse for a team</span></span>
- <span data-ttu-id="0762f-161">将文件上载到人际交谈</span><span class="sxs-lookup"><span data-stu-id="0762f-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="0762f-162">有关详细信息，请参阅[何谓来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="0762f-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="0762f-163">疑难解答</span><span class="sxs-lookup"><span data-stu-id="0762f-163">Troubleshooting</span></span>

<span data-ttu-id="0762f-164">如果必须添加在 Microsoft 团队客人的问题，请参阅[来宾访问故障排除指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="0762f-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


