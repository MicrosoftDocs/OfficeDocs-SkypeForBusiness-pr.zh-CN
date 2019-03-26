---
title: Microsoft 团队来宾访问清单
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单来帮助中的 Microsoft 团队的来宾访问设置。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68beeba403f6a64e194594d5bd40b985c8051dc6
ms.sourcegitcommit: fba1151c968aa2c43d0c5b42b889b2cdd8dba3cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "30795583"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="d5248-103">团队来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="d5248-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="d5248-104">使用此清单可帮助您启用和配置中的 Microsoft 团队的来宾访问功能，根据组织的首选项。</span><span class="sxs-lookup"><span data-stu-id="d5248-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="d5248-105">了解来宾的限制</span><span class="sxs-lookup"><span data-stu-id="d5248-105">Understand the limitations for guests</span></span>

<span data-ttu-id="d5248-106">来宾体验设计具有限制。</span><span class="sxs-lookup"><span data-stu-id="d5248-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="d5248-107">请确保您了解来宾体验，以便不尝试修复内容不是问题。</span><span class="sxs-lookup"><span data-stu-id="d5248-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="d5248-108">例如，下面是功能的一些不可来宾中的 Microsoft 团队列表：</span><span class="sxs-lookup"><span data-stu-id="d5248-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="d5248-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d5248-109">OneDrive for Business</span></span>
- <span data-ttu-id="d5248-110">团队之外人员搜索</span><span class="sxs-lookup"><span data-stu-id="d5248-110">People search outside of Teams</span></span>
- <span data-ttu-id="d5248-111">日历、 计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="d5248-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="d5248-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="d5248-112">PSTN</span></span>
- <span data-ttu-id="d5248-113">组织结构图</span><span class="sxs-lookup"><span data-stu-id="d5248-113">Organization chart</span></span>
- <span data-ttu-id="d5248-114">创建或修改团队</span><span class="sxs-lookup"><span data-stu-id="d5248-114">Create or revise a team</span></span>
- <span data-ttu-id="d5248-115">浏览团队</span><span class="sxs-lookup"><span data-stu-id="d5248-115">Browse for a team</span></span>
- <span data-ttu-id="d5248-116">将文件上载到个人到个人聊天</span><span class="sxs-lookup"><span data-stu-id="d5248-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="d5248-117">有关详细信息，请参阅[新增的来宾体验](guest-experience.md)和[来宾访问 Office 365 组中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="d5248-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="d5248-118">来宾访问与外部访问 （联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="d5248-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="d5248-119">如果您来宾看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="d5248-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="d5248-120">来宾访问中的 Microsoft 团队使用 Azure Active Directory 业务到企业 (B2B) 和其许可模型。</span><span class="sxs-lookup"><span data-stu-id="d5248-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="d5248-121">如果您看到许可错误，请务必阅读 B2B 许可指南以了解您的组织有以便用户能够邀请来宾到您的组织的许可要求。</span><span class="sxs-lookup"><span data-stu-id="d5248-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="d5248-122">要记住的几个事项：</span><span class="sxs-lookup"><span data-stu-id="d5248-122">A few things to remember:</span></span>

- <span data-ttu-id="d5248-123">为每个付费 Azure AD 许可证分配给用户，用户可以邀请外部用户宽限下的最多五个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d5248-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="d5248-124">来宾是组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="d5248-124">Guests are users outside your organization.</span></span> <span data-ttu-id="d5248-125">无法为来宾添加您的员工、 现场承包商、 现场代理，等等。</span><span class="sxs-lookup"><span data-stu-id="d5248-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="d5248-126">这同样适用于您子公司。</span><span class="sxs-lookup"><span data-stu-id="d5248-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="d5248-127">来宾许可证在内针对邀请的组织。</span><span class="sxs-lookup"><span data-stu-id="d5248-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="d5248-128">当计算所需的许可证数量，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="d5248-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="d5248-129">针对许可证计数针对您的组织是否受邀的来宾来自其他 Office 365 租户，或使用其个人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d5248-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="d5248-130">□ 步骤 1： 在 Azure AD 企业到企业中配置设置</span><span class="sxs-lookup"><span data-stu-id="d5248-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="d5248-131">登录到https://portal.azure.com。</span><span class="sxs-lookup"><span data-stu-id="d5248-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="d5248-132">单击左侧窗格中的**Azure Active directory** 。</span><span class="sxs-lookup"><span data-stu-id="d5248-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="d5248-133">在**管理**下单击**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="d5248-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="d5248-134">在**外部用户**，下单击**管理外部协作设置**。</span><span class="sxs-lookup"><span data-stu-id="d5248-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="d5248-135">在**外部协作设置**页中，确保**成员可以邀请**设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="d5248-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="d5248-136">屏幕快照显示了 AAD 设置切换的示例。</span><span class="sxs-lookup"><span data-stu-id="d5248-136">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="d5248-137">若要支持来宾，**可以邀请成员**必须设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="d5248-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="d5248-138">如果设置为**否**的**成员可以邀请**，然后启用来宾访问 Office 365 组和 Microsoft 团队中的，管理员可以控制来宾邀请到您的目录。</span><span class="sxs-lookup"><span data-stu-id="d5248-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="d5248-139">来宾目录中后，他们可以通过属于团队所有者非管理员成员添加到团队。</span><span class="sxs-lookup"><span data-stu-id="d5248-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="d5248-140">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="d5248-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="d5248-141">□ 步骤 2： 配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="d5248-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="d5248-142">在 Microsoft 365 管理中心，转到**设置** > **服务 & 加载** > **Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="d5248-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="d5248-143">请确保**让外部组织的访问组内容的组成员**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="d5248-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="d5248-144">如果此设置处于关闭，来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="d5248-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="d5248-145">请确保**让组添加到组组织外部的人员的所有者**设置为**上**。</span><span class="sxs-lookup"><span data-stu-id="d5248-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="d5248-146">如果此设置处于关闭，团队所有者将无法添加新的来宾。</span><span class="sxs-lookup"><span data-stu-id="d5248-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="d5248-147">至少，此设置必须登录到支持来宾访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5248-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![屏幕快照显示了 Office 365 组切换](media/guest-access-checklist-office365.png)

<span data-ttu-id="d5248-149">有关配置这些设置的详细说明，请参阅[管理 Office 365 组中的来宾访问](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和部分[中的 Microsoft 团队的授权来宾访问](Teams-dependencies.md)中的"Office 365 组"。</span><span class="sxs-lookup"><span data-stu-id="d5248-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="d5248-150">□ 步骤 3： 启用租户级别的来宾访问</span><span class="sxs-lookup"><span data-stu-id="d5248-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="d5248-151">至少，您必须启用来宾访问的**Microsoft 团队管理中心**下的 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="d5248-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="d5248-152">在团队管理中心中选择**组织范围设置** > **来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="d5248-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d5248-153">设置为**上**的**Microsoft 团队中的允许来宾访问**开关。</span><span class="sxs-lookup"><span data-stu-id="d5248-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕快照显示了工作组设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d5248-155">在此同一页上，配置所需的任何其他来宾设置。</span><span class="sxs-lookup"><span data-stu-id="d5248-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="d5248-156">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d5248-156">Click **Save**.</span></span>

<span data-ttu-id="d5248-157">有关详细说明，请参阅[打开或关闭向 Microsoft 工作组的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="d5248-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="d5248-158">□ 步骤 4： 配置 Office 365 中共享</span><span class="sxs-lookup"><span data-stu-id="d5248-158">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="d5248-159">确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="d5248-159">Make sure that users can add guests.</span></span> <span data-ttu-id="d5248-160">下面是如何：</span><span class="sxs-lookup"><span data-stu-id="d5248-160">Here's how:</span></span>

1. <span data-ttu-id="d5248-161">在 Microsoft 365 管理中心，转到**设置** > **安全 & 隐私**。</span><span class="sxs-lookup"><span data-stu-id="d5248-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![屏幕快照显示了服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="d5248-163">在**共享**，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d5248-163">In **Sharing**, select **Edit**.</span></span>

     ![屏幕快照显示了共享的设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="d5248-165">设置**让用户将添加到此组织的新来宾**为**上**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d5248-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![屏幕快照显示了共享的设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="d5248-167">此设置等同于在**用户设置**中的**成员可以邀请**设置 > Azure AD 中的**外部用户**。</span><span class="sxs-lookup"><span data-stu-id="d5248-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d5248-168">□ 步骤 5： 验证在 SharePoint 中的共享设置</span><span class="sxs-lookup"><span data-stu-id="d5248-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="d5248-169">登录 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d5248-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="d5248-170">单击**管理中心**，然后选择**SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="d5248-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="d5248-171">在 SharePoint 管理中心中，选择**共享**。</span><span class="sxs-lookup"><span data-stu-id="d5248-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="d5248-172">请确保选项*未*选中的**不允许共享您的组织外部**。</span><span class="sxs-lookup"><span data-stu-id="d5248-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![屏幕快照显示了 SparePoint 联机设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="d5248-174">□ 步骤 6： 启用渠道的特定设置</span><span class="sxs-lookup"><span data-stu-id="d5248-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="d5248-175">中的团队应用程序，在各个团队级别配置来宾权限，以便来宾可以创建、 更新和删除通道。</span><span class="sxs-lookup"><span data-stu-id="d5248-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="d5248-176">除了 admins 团队所有者可以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="d5248-176">In addition to admins,  team owners can configure this setting.</span></span>

![屏幕快照显示了工作组/通道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d5248-178">有关详细信息，包括操作方法视频，请参阅[中的 Microsoft 团队的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="d5248-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="d5248-179">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d5248-179">Troubleshooting</span></span>

<span data-ttu-id="d5248-180">如果您遇到的 Microsoft 团队中添加来宾问题，请参阅[来宾访问疑难解答指南 》](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="d5248-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


