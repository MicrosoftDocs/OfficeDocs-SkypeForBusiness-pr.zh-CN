---
title: Microsoft Teams 来宾访问清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单可帮助设置 Microsoft 团队中的来宾访问。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 833d79d16365a1b90e8cd35e88e43468f0e25fa8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280922"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="e0d1f-103">团队来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="e0d1f-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="e0d1f-104">使用此清单可帮助你根据你的组织的首选项, 在 Microsoft 团队中启用和配置来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="e0d1f-105">了解对来宾的限制</span><span class="sxs-lookup"><span data-stu-id="e0d1f-105">Understand the limitations for guests</span></span>

<span data-ttu-id="e0d1f-106">来宾体验由设计限制。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="e0d1f-107">请确保你了解来宾体验, 这样就不会尝试修复不存在问题的内容。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="e0d1f-108">例如, 下面列出了 Microsoft 团队中的来宾无法使用的一些功能:</span><span class="sxs-lookup"><span data-stu-id="e0d1f-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="e0d1f-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e0d1f-109">OneDrive for Business</span></span>
- <span data-ttu-id="e0d1f-110">在团队外搜索的人员</span><span class="sxs-lookup"><span data-stu-id="e0d1f-110">People search outside of Teams</span></span>
- <span data-ttu-id="e0d1f-111">日历、计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="e0d1f-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="e0d1f-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="e0d1f-112">PSTN</span></span>
- <span data-ttu-id="e0d1f-113">组织结构图</span><span class="sxs-lookup"><span data-stu-id="e0d1f-113">Organization chart</span></span>
- <span data-ttu-id="e0d1f-114">创建或修订团队</span><span class="sxs-lookup"><span data-stu-id="e0d1f-114">Create or revise a team</span></span>
- <span data-ttu-id="e0d1f-115">浏览团队</span><span class="sxs-lookup"><span data-stu-id="e0d1f-115">Browse for a team</span></span>
- <span data-ttu-id="e0d1f-116">将文件上传到人员间聊天</span><span class="sxs-lookup"><span data-stu-id="e0d1f-116">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="e0d1f-117">如果用户知道他们的完整电子邮件 ID, 则来宾仍可搜索和查找其团队外的用户。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-117">Guests can still search and find users, outside their team, if they know their full email ID.</span></span> <span data-ttu-id="e0d1f-118">为避免这种情况, IT 管理员可以使用具有[范围的目录搜索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)的模式, 这些模式能够将来宾限制在自己的虚拟 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-118">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="e0d1f-119">有关更多详细信息, 请参阅[来宾体验](guest-experience.md)和[Office 365 组中的来宾访问](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-119">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="e0d1f-120">来宾访问与外部访问（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="e0d1f-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="e0d1f-121">如果您的客人看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="e0d1f-121">If your guests are seeing license errors</span></span>

<span data-ttu-id="e0d1f-122">Microsoft 团队中的来宾访问使用 Azure Active Directory 商业版 (B2B) 和其许可模型。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-122">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="e0d1f-123">如果您看到授权错误, 请确保阅读 B2B 授权指南以了解您的组织拥有的授权要求, 以便用户能够邀请来宾加入您的组织。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-123">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="e0d1f-124">需要注意的一些事项:</span><span class="sxs-lookup"><span data-stu-id="e0d1f-124">A few things to remember:</span></span>

- <span data-ttu-id="e0d1f-125">对于分配给用户的每个付费 Azure AD 许可证, 你的用户可以在外部用户津贴下邀请最多五个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-125">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="e0d1f-126">来宾是您的组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-126">Guests are users outside your organization.</span></span> <span data-ttu-id="e0d1f-127">您的员工、现场承包商、现场工程师等不能添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-127">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="e0d1f-128">这同样适用于您的会员。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-128">The same applies to your affiliates.</span></span>
- <span data-ttu-id="e0d1f-129">来宾许可证按邀请的组织计入。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-129">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="e0d1f-130">当你计算所需的许可证数量时, 请考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-130">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="e0d1f-131">根据您的组织统计许可证, 无论受邀的来宾来自其他 Office 365 租户还是使用其个人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-131">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="e0d1f-132">□步骤 1: 在 Azure AD 企业到企业中配置设置</span><span class="sxs-lookup"><span data-stu-id="e0d1f-132">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="e0d1f-133">登录到https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="e0d1f-133">Sign in to https://portal.azure.com</span></span>
2. <span data-ttu-id="e0d1f-134">在左窗格中单击 " **Azure Active directory** "。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-134">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="e0d1f-135">在 "**管理**" 下, 单击 "**用户设置**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-135">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="e0d1f-136">在 "**外部用户**" 下, 单击 "**管理外部协作设置**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-136">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="e0d1f-137">在 "**外部协作设置**" 页面上, 确保 "**成员可邀请**" 设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-137">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="e0d1f-138">屏幕截图显示 AAD 设置切换的示例。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-138">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="e0d1f-139">若要支持来宾, "**成员可以邀请**" 必须设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-139">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="e0d1f-140">如果您设置的**成员可以邀请**"**否**", 然后在 Office 365 组和 Microsoft 团队中启用来宾访问, 则管理员可以控制您的目录的来宾邀请。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-140">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="e0d1f-141">来宾位于目录中后, 可通过非管理员成员的团队所有者将其添加到团队。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-141">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="e0d1f-142">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-142">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="e0d1f-143">□步骤 2: 配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="e0d1f-143">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="e0d1f-144">在 Microsoft 365 管理中心, 转到 "**设置** > **服务 &" 加载项** > **Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-144">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="e0d1f-145">确保将 **"组织" 访问组内容外的组成员**设置为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-145">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="e0d1f-146">如果此设置处于关闭状态, 则来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-146">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="e0d1f-147">确保**组所有者将组织外部的人员添加到 "组**" 设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-147">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="e0d1f-148">如果此设置处于关闭状态, 则团队所有者将无法添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-148">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="e0d1f-149">此设置至少必须启用才能支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-149">At a minimum, this setting must be On to support guest access.</span></span>

     ![屏幕截图显示 Office 365 组的切换](media/guest-access-checklist-office365.png)

<span data-ttu-id="e0d1f-151">有关配置这些设置的详细说明, 请参阅在[Office 365 组中管理来宾访问](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和在[Microsoft 团队中授权来宾访问](Teams-dependencies.md)部分中的 "Office 365 组" 部分。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-151">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="e0d1f-152">□步骤 3: 在租户级别启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="e0d1f-152">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="e0d1f-153">至少, 你必须在**Microsoft 团队管理中心**下为 microsoft 团队启用来宾访问。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-153">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="e0d1f-154">在 "团队管理中心" 中, 选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-154">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="e0d1f-155">将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-155">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="e0d1f-157">在此同一页面上, 配置所需的任何其他来宾设置。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-157">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="e0d1f-158">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-158">Click **Save**.</span></span>

<span data-ttu-id="e0d1f-159">有关详细说明, 请参阅[打开或关闭对 Microsoft 团队的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-159">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="e0d1f-160">□步骤 4: 在 Office 365 中配置共享</span><span class="sxs-lookup"><span data-stu-id="e0d1f-160">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="e0d1f-161">请确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-161">Make sure that users can add guests.</span></span> <span data-ttu-id="e0d1f-162">操作方法如下:</span><span class="sxs-lookup"><span data-stu-id="e0d1f-162">Here's how:</span></span>

1. <span data-ttu-id="e0d1f-163">在 Microsoft 365 管理中心中, 转到 "**设置** > **安全 & 隐私**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-163">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="e0d1f-165">在 "**共享**" 中, 选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-165">In **Sharing**, select **Edit**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="e0d1f-167">设置 "**允许用户向此组织添加新来宾**", 然后单击 "**保存**"。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e0d1f-167">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="e0d1f-169">此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-169">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="e0d1f-170">□步骤 5: 验证 SharePoint 中的共享设置</span><span class="sxs-lookup"><span data-stu-id="e0d1f-170">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="e0d1f-171">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-171">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="e0d1f-172">单击 "**管理中心**", 然后选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-172">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="e0d1f-173">在 SharePoint 管理中心中, 选择 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-173">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="e0d1f-174">请确保*未*选中 "**不允许在组织外部共享**" 选项。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-174">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![屏幕截图显示 SparePoint 联机设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="e0d1f-176">□步骤 6: 启用频道的特定设置</span><span class="sxs-lookup"><span data-stu-id="e0d1f-176">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="e0d1f-177">在 "团队" 应用程序中, 在单个团队级别配置来宾权限, 以便来宾可以创建、更新和删除频道。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-177">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="e0d1f-178">除了管理员, 团队所有者还可以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-178">In addition to admins,  team owners can configure this setting.</span></span>

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="e0d1f-180">有关详细信息, 包括操作方法视频, 请参阅[Microsoft 团队中的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-180">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="e0d1f-181">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e0d1f-181">Troubleshooting</span></span>

<span data-ttu-id="e0d1f-182">如果您在 Microsoft 团队中添加来宾时遇到问题, 请参阅[来宾 Access 疑难解答指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="e0d1f-182">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


