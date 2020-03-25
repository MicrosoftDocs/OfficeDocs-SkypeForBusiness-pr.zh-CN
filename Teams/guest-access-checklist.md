---
title: Microsoft Teams 来宾访问清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 在 Microsoft Teams 中使用此清单帮助设置来宾访问。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5470d9ec2ec2d22d8f3b66bac09ba6c67b9982f
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951497"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="bb615-103">Microsoft Teams 来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="bb615-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="bb615-104">在 Microsoft Teams 中使用此清单来帮助您启用和配置来宾访问。</span><span class="sxs-lookup"><span data-stu-id="bb615-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="bb615-105">你需要成为全局管理员或 Teams 管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="bb615-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb615-106">可能需要等待长达 24 小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="bb615-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="bb615-107">观看此短视频（5 分 31 秒），了解如何通过 Microsoft 365（包括 Teams）启用来宾访问。</span><span class="sxs-lookup"><span data-stu-id="bb615-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="bb615-108">步骤 1：在 Teams 组织范围内级别启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="bb615-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="bb615-109">要启用来宾访问，请转至 **Microsoft Teams 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="bb615-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="bb615-110">在 Teams 管理中心中，选择“**组织范围的设置**” > “**来宾访问**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="bb615-111">将“**在 Microsoft Teams 中允许来宾访问**”开关设置为“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕截图显示 Teams 设置开关示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="bb615-113">在同一页面上，为来宾打开或关闭“**呼叫**”、“**会议**”和“**消息传递**”设置。</span><span class="sxs-lookup"><span data-stu-id="bb615-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="bb615-114">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="bb615-115">如果使用 Azure Active Directory、SharePoint Online 和 Office 365 组中的默认设置，则可能已完成来宾访问配置。</span><span class="sxs-lookup"><span data-stu-id="bb615-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="bb615-116">在此情况下，可以跳过其余步骤。</span><span class="sxs-lookup"><span data-stu-id="bb615-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="bb615-117">如果不确定，或者如果使用 AAD、SharePoint Online 或 Office 365 组的自定义设置，请继续完成此清单中的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="bb615-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="bb615-118">步骤 2：配置 Azure AD 企业对企业设置</span><span class="sxs-lookup"><span data-stu-id="bb615-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="bb615-119">这些是支持 Teams 中的来宾访问的 Azure AD 设置。</span><span class="sxs-lookup"><span data-stu-id="bb615-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="bb615-120">这些设置配置完成之后，可以在 Teams 中“[添加](add-guests.md)”和“[管理来宾](manage-guests.md)”。</span><span class="sxs-lookup"><span data-stu-id="bb615-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="bb615-121">以租户管理员身份登录 [Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="bb615-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="bb615-122">选择“**Azure Active Directory**” > “**用户** > ”“**用户设置**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="bb615-123">在“**外部用户**”下，选择“**管理外部协作设置**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bb615-124">“**外部协作设置**”也可从“**组织关系**”页面获取。</span><span class="sxs-lookup"><span data-stu-id="bb615-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="bb615-125">在 Azure Active Directory 中的“**管理**”下，转至“**组织关系**” > “**设置**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="bb615-126">在“**外部协作设置**”页面上，选择想要启用的策略。</span><span class="sxs-lookup"><span data-stu-id="bb615-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="bb615-127">**来宾用户权限受限**：此策略决定目录中来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="bb615-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="bb615-128">选择“**是**”阻止来宾执行特定目录任务，如枚举用户、组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="bb615-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="bb615-129">选择“**否**”为来宾授予与目录中的常规用户相同的目录数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="bb615-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="bb615-130">**来宾邀请者角色中的管理员和用户可进行邀请**：要允许“来宾邀请者”角色中的管理员和用户邀请来宾，请将此策略设置为“**是**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="bb615-131">**成员可邀请**：要允许目录的非管理员成员邀请来宾，请将此策略设置为**是**（建议设置）。</span><span class="sxs-lookup"><span data-stu-id="bb615-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="bb615-132">如果你希望仅管理员能够添加来宾，可以将此策略设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="bb615-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="bb615-133">请记住，设置为**否**将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="bb615-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="bb615-134">**来宾可进行邀请**：要允许来宾邀请其他来宾，请将此策略设置为“**是**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="bb615-135">目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。</span><span class="sxs-lookup"><span data-stu-id="bb615-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="bb615-136">**为来宾启用电子邮件一次性密码(预览)**：有关一次性密码功能的更多信息，请参阅[电子邮件一次性密码身份验证(预览)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="bb615-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="bb615-137">**协作限制**：有关允许或阻止对特定域的邀请的更多信息，请参阅[允许或阻止对特定组织中的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="bb615-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="bb615-138">对于协作限制，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="bb615-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="bb615-139">要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="bb615-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="bb615-140">步骤 3：配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="bb615-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="bb615-141">在 Microsoft 365 管理中心中，转至“**设置**” > “**设置**”，单击“**服务**”，然后选择“**Office 365 组**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="bb615-143">确保已选中“**允许组织外部的组成员访问组内容**”复选框。</span><span class="sxs-lookup"><span data-stu-id="bb615-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="bb615-144">如果未选中此设置，则来宾无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="bb615-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="bb615-146">确保已选中“**允许组拥有者将组织外部的人员添加到组**”复选框。</span><span class="sxs-lookup"><span data-stu-id="bb615-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="bb615-147">如果未选中此设置，则团队拥有者无法添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="bb615-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="bb615-148">作为最低条件，此设置必须启用才能支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="bb615-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="bb615-149">有关配置这些设置的详细说明，请参阅[管理 Office 365 组中的来宾访问](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 Office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="bb615-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="bb615-150">步骤 4：在 Office 365 中配置共享</span><span class="sxs-lookup"><span data-stu-id="bb615-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="bb615-151">确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="bb615-151">Make sure that users can add guests.</span></span> <span data-ttu-id="bb615-152">操作步骤如下：</span><span class="sxs-lookup"><span data-stu-id="bb615-152">Here's how:</span></span>

1. <span data-ttu-id="bb615-153">在 Microsoft 365 管理中心中，转至“**设置**” > “**设置**”，单击“**安全和隐私**”，然后选择“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![屏幕截图显示服务设置示例](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="bb615-155">选中“**允许用户向此组织添加新来宾**”复选框，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![屏幕截图显示共享设置开关示例](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="bb615-157">此设置的作用相当于 Azure AD 中的“**用户设置**” > “**外部用户**”中的“**成员可进行邀请**”设置。</span><span class="sxs-lookup"><span data-stu-id="bb615-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="bb615-158">步骤 5：在 SharePoint 中验证共享设置</span><span class="sxs-lookup"><span data-stu-id="bb615-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="bb615-159">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="bb615-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="bb615-160">在“**管理中心**”下，选择“**SharePoint**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="bb615-161">在新的 SharePoint 管理中心的“**网站**”下，选择“**活动网站**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 管理中心中的活动网站](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="bb615-163">选择“网站”，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="bb615-164">确保将选项设置为“**任何人**”或“**新来宾和现有来宾**”。</span><span class="sxs-lookup"><span data-stu-id="bb615-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![屏幕截图显示 SharePoint Online 设置开关示例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="bb615-166">步骤 6：设置来宾用户权限</span><span class="sxs-lookup"><span data-stu-id="bb615-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="bb615-167">在 Teams 应用程序中，在单个团队级别配置来宾权限，以控制来宾是否可以创建、更新或删除频道。</span><span class="sxs-lookup"><span data-stu-id="bb615-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="bb615-168">Teams 管理员和团队拥有者可以配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="bb615-168">Teams admins as well as team owners can configure these settings.</span></span>

![屏幕截图显示团队/频道设置开关示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="bb615-170">要了解与来宾访问相关的更多信息，请参阅 [Teams 中的来宾访问](guest-access.md)和[启用或禁用 Microsoft Teams 的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="bb615-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bb615-171">故障排除</span><span class="sxs-lookup"><span data-stu-id="bb615-171">Troubleshooting</span></span>

<span data-ttu-id="bb615-172">如果在设置来宾访问或在 Teams 中添加来宾时遇到问题，请使用以下资源来帮助你解决问题：</span><span class="sxs-lookup"><span data-stu-id="bb615-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="bb615-173">对 Microsoft Teams 中的来宾访问问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="bb615-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="bb615-174">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="bb615-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
