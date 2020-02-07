---
title: Microsoft Teams 来宾访问清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单可帮助设置 Microsoft 团队中的来宾访问。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833252"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="16c30-103">Microsoft Teams 来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="16c30-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="16c30-104">使用此清单可帮助你打开和配置 Microsoft 团队中的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="16c30-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="16c30-105">您必须是全局管理员或团队管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="16c30-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16c30-106">您可能需要等待24小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="16c30-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="16c30-107">观看此简短视频（5:31 分钟），了解如何在整个 Microsoft 365 （包括团队）中打开来宾访问。</span><span class="sxs-lookup"><span data-stu-id="16c30-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="16c30-108">步骤1：在团队的组织范围级别启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="16c30-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="16c30-109">若要启用来宾访问，请转到**Microsoft 团队管理中心**。</span><span class="sxs-lookup"><span data-stu-id="16c30-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="16c30-110">在 "团队管理中心" 中，选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="16c30-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="16c30-111">将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="16c30-113">在此同一页面上，打开或关闭来宾的**呼叫**、**会议**和**消息**设置。</span><span class="sxs-lookup"><span data-stu-id="16c30-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="16c30-114">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="16c30-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="16c30-115">如果你使用的是 Azure Active Directory、SharePoint Online 和 Office 365 组中的默认设置，则可能会完成来宾访问配置。</span><span class="sxs-lookup"><span data-stu-id="16c30-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="16c30-116">在这种情况下，您可以跳过其余步骤。</span><span class="sxs-lookup"><span data-stu-id="16c30-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="16c30-117">如果不确定，或者如果你使用的是 AAD、SharePoint Online 或 Office 365 组的自定义设置，请继续执行此清单中的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="16c30-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="16c30-118">步骤2：配置 Azure AD 企业到企业版设置</span><span class="sxs-lookup"><span data-stu-id="16c30-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="16c30-119">这些是支持团队中的来宾访问的 Azure AD 设置。</span><span class="sxs-lookup"><span data-stu-id="16c30-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="16c30-120">配置这些设置后，您将能够在团队中[添加](add-guests.md)和[管理来宾](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="16c30-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="16c30-121">以租户管理员身份登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="16c30-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="16c30-122">选择 " **Azure Active Directory** > **用户** > "**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="16c30-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="16c30-123">在 "**外部用户**" 下，选择 "**管理外部协作设置**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="16c30-124">此外，还可从 "**组织关系**" 页面获取**外部协作设置**。</span><span class="sxs-lookup"><span data-stu-id="16c30-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="16c30-125">在 Azure Active Directory 中的 "**管理**" 下，转到 "**组织关系** > "**设置**。</span><span class="sxs-lookup"><span data-stu-id="16c30-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="16c30-126">在 "**外部协作设置**" 页面上，选择要启用的策略。</span><span class="sxs-lookup"><span data-stu-id="16c30-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="16c30-127">**来宾用户权限受到限制**：此策略确定你的目录中的来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="16c30-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="16c30-128">选择 **"是"** 阻止来自某些目录任务的来宾，例如枚举用户、组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="16c30-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="16c30-129">选择 "**否**"，为来宾提供与目录中普通用户相同的访问目录数据。</span><span class="sxs-lookup"><span data-stu-id="16c30-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="16c30-130">**来宾 inviter 角色中的管理员和用户可以邀请**：要允许管理员和 "来宾 inviter" 角色中的用户邀请来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="16c30-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="16c30-131">**成员可邀请**：要允许目录的非管理员成员邀请来宾，请将此策略设置为**是**（建议设置）。</span><span class="sxs-lookup"><span data-stu-id="16c30-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="16c30-132">如果你希望仅管理员能够添加来宾，可以将此策略设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="16c30-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="16c30-133">请记住，设置为**否**将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。</span><span class="sxs-lookup"><span data-stu-id="16c30-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="16c30-134">**来宾可以邀请**：要允许来宾邀请其他来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="16c30-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="16c30-135">目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。</span><span class="sxs-lookup"><span data-stu-id="16c30-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="16c30-136">**启用来宾电子邮件一次性密码（预览版）**：有关一次性密码功能的详细信息，请参阅[通过电子邮件发送一次性密码身份验证（预览版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="16c30-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="16c30-137">**协作限制**：有关允许或阻止特定域的邀请的详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="16c30-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="16c30-138">有关协作限制，请参阅[启用 B2B 外部协作和管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="16c30-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="16c30-139">要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="16c30-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="16c30-140">步骤3：配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="16c30-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="16c30-141">在 Microsoft 365 管理中心，转到 "**设置** > "**设置**，单击 "**服务**"，然后选择 " **Office 365 组**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="16c30-143">确保选中 "**允许组织访问组内容之外的成员进行分组**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="16c30-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="16c30-144">如果未选择此设置，来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="16c30-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="16c30-146">确保已选中 "**允许组所有者将组织外部人员添加到组**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="16c30-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="16c30-147">如果未选择此设置，则团队所有者将无法添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="16c30-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="16c30-148">此设置至少必须启用才能支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="16c30-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="16c30-149">有关配置这些设置的详细说明，请参阅[在 office 365 组中管理来宾访问](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="16c30-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="16c30-150">步骤4：在 Office 365 中配置共享</span><span class="sxs-lookup"><span data-stu-id="16c30-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="16c30-151">请确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="16c30-151">Make sure that users can add guests.</span></span> <span data-ttu-id="16c30-152">操作方法如下：</span><span class="sxs-lookup"><span data-stu-id="16c30-152">Here's how:</span></span>

1. <span data-ttu-id="16c30-153">在 Microsoft 365 管理中心中，转到 "**设置** > **设置**"，单击 "**安全 & 隐私**"，然后选择 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="16c30-155">选中 "**允许用户向此组织添加新来宾**" 复选框，然后单击 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="16c30-157">此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。</span><span class="sxs-lookup"><span data-stu-id="16c30-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="16c30-158">步骤5：验证 SharePoint 中的共享设置</span><span class="sxs-lookup"><span data-stu-id="16c30-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="16c30-159">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="16c30-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="16c30-160">在 "**管理中心**" 下，选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="16c30-161">在新的 SharePoint 管理中心的 "**网站**" 下，选择 "**活动网站**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 管理中心中的活动网站](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="16c30-163">选择 "网站"，然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="16c30-164">请确保已将该选项设置为 "**任何人**" 或 "**现有来宾**"。</span><span class="sxs-lookup"><span data-stu-id="16c30-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![屏幕截图显示 SharePoint Online 设置切换的示例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="16c30-166">步骤6：设置来宾用户权限</span><span class="sxs-lookup"><span data-stu-id="16c30-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="16c30-167">在 "团队" 应用程序中，在单个团队级别配置用于控制来宾是否可以创建、更新或删除频道的来宾权限。</span><span class="sxs-lookup"><span data-stu-id="16c30-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="16c30-168">团队管理员和团队所有者可以配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="16c30-168">Teams admins as well as team owners can configure these settings.</span></span>

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="16c30-170">若要了解有关来宾访问的详细信息，请参阅[团队中的来宾访问](guest-access.md)和[打开或关闭 Microsoft 团队的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="16c30-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="16c30-171">疑难解答</span><span class="sxs-lookup"><span data-stu-id="16c30-171">Troubleshooting</span></span>

<span data-ttu-id="16c30-172">如果您在设置来宾访问或在团队中添加来宾时遇到问题，请使用以下资源帮助您：</span><span class="sxs-lookup"><span data-stu-id="16c30-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="16c30-173">解决 Microsoft 团队中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="16c30-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="16c30-174">团队疑难解答</span><span class="sxs-lookup"><span data-stu-id="16c30-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
