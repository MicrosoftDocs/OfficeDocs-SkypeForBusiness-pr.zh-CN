---
title: Microsoft Teams 来宾访问清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此清单可帮助设置 Microsoft 团队中的来宾访问。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753317"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="acdbc-103">Microsoft Teams 来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="acdbc-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="acdbc-104">使用此清单可帮助你打开和配置 Microsoft 团队中的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="acdbc-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acdbc-105">您可能需要等待24小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="acdbc-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="acdbc-106">步骤1：在团队的组织范围级别启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="acdbc-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="acdbc-107">若要启用来宾访问，请转到**Microsoft 团队管理中心**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="acdbc-108">在 "团队管理中心" 中，选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="acdbc-109">将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="acdbc-111">在此同一页面上，打开或关闭来宾的**呼叫**、**会议**和**消息**设置。</span><span class="sxs-lookup"><span data-stu-id="acdbc-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="acdbc-112">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="acdbc-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="acdbc-113">如果你使用的是 Azure Active Directory、SharePoint Online 和 Office 365 组中的默认设置，则可能会完成来宾访问配置。</span><span class="sxs-lookup"><span data-stu-id="acdbc-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="acdbc-114">在这种情况下，您可以跳过其余步骤。</span><span class="sxs-lookup"><span data-stu-id="acdbc-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="acdbc-115">如果不确定，或者如果你使用的是 AAD、SharePoint Online 或 Office 365 组的自定义设置，请继续执行此清单中的其余步骤。</span><span class="sxs-lookup"><span data-stu-id="acdbc-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="acdbc-116">步骤2：配置 Azure AD 企业到企业版设置</span><span class="sxs-lookup"><span data-stu-id="acdbc-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="acdbc-117">以租户管理员身份登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="acdbc-118">选择 " **Azure Active Directory** > **用户** > "**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="acdbc-119">在 "**外部用户**" 下，选择 "**管理外部协作设置**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="acdbc-120">此外，还可从 "**组织关系**" 页面获取**外部协作设置**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="acdbc-121">在 Azure Active Directory 中的 "**管理**" 下，转到 "**组织关系** > "**设置**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="acdbc-122">在 "**外部协作设置**" 页面上，选择要启用的策略。</span><span class="sxs-lookup"><span data-stu-id="acdbc-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="acdbc-123">**来宾用户权限受到限制**：此策略确定你的目录中的来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="acdbc-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="acdbc-124">选择 **"是"** 阻止来自某些目录任务的来宾，例如枚举用户、组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="acdbc-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="acdbc-125">选择 "**否**"，为来宾提供与目录中普通用户相同的访问目录数据。</span><span class="sxs-lookup"><span data-stu-id="acdbc-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="acdbc-126">**来宾 inviter 角色中的管理员和用户可以邀请**：要允许管理员和 "来宾 inviter" 角色中的用户邀请来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="acdbc-127">**成员可以邀请**：若要允许你的目录的非管理员成员邀请来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="acdbc-128">如果您设置的**成员可以邀请**"**否**"，然后在 Office 365 组和 Microsoft 团队中启用来宾访问，则管理员可以控制您的目录的来宾邀请。</span><span class="sxs-lookup"><span data-stu-id="acdbc-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="acdbc-129">来宾位于目录中后，可通过非管理员成员的团队所有者将其添加到团队。</span><span class="sxs-lookup"><span data-stu-id="acdbc-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="acdbc-130">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="acdbc-131">若要使来宾访问完全在团队中工作，您必须将**成员**设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="acdbc-132">**来宾可以邀请**：要允许来宾邀请其他来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="acdbc-133">当前，团队不支持来宾 inviter 角色，因此即使你将来宾设置为 "**邀请" 可以邀请**为 **"是**"，来宾也无法邀请团队中的其他来宾。</span><span class="sxs-lookup"><span data-stu-id="acdbc-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="acdbc-134">**启用来宾电子邮件一次性密码（预览版）**：有关一次性密码功能的详细信息，请参阅[通过电子邮件发送一次性密码身份验证（预览版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="acdbc-135">**协作限制**：有关允许或阻止特定域的邀请的详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="acdbc-136">有关协作限制，请参阅[启用 B2B 外部协作和管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="acdbc-137">要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="acdbc-138">步骤3：配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="acdbc-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="acdbc-139">在 Microsoft 365 管理中心，转到 "**设置** > **服务" & "加载项** > "**Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="acdbc-140">确保将 **"组织" 访问组内容外的组成员**设置为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="acdbc-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="acdbc-141">如果此设置处于关闭状态，则来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="acdbc-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="acdbc-142">确保**组所有者将组织外部的人员添加到 "组**" 设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="acdbc-143">如果此设置处于关闭状态，则团队所有者将无法添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="acdbc-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="acdbc-144">此设置至少必须启用才能支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="acdbc-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![屏幕截图显示 Office 365 组的切换](media/guest-access-checklist-office365.png)

<span data-ttu-id="acdbc-146">有关配置这些设置的详细说明，请参阅[在 office 365 组中管理来宾访问](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="acdbc-147">步骤4：在 Office 365 中配置共享</span><span class="sxs-lookup"><span data-stu-id="acdbc-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="acdbc-148">请确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="acdbc-148">Make sure that users can add guests.</span></span> <span data-ttu-id="acdbc-149">操作方法如下：</span><span class="sxs-lookup"><span data-stu-id="acdbc-149">Here's how:</span></span>

1. <span data-ttu-id="acdbc-150">在 Microsoft 365 管理中心中，转到 "**设置** > **安全 & 隐私**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="acdbc-152">在 "**共享**" 中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-152">In **Sharing**, select **Edit**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="acdbc-154">设置 "**允许用户向此组织添加新来宾** **"，然后**单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="acdbc-156">此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。</span><span class="sxs-lookup"><span data-stu-id="acdbc-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="acdbc-157">步骤5：验证 SharePoint 中的共享设置</span><span class="sxs-lookup"><span data-stu-id="acdbc-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="acdbc-158">这一点是大脑 teaser。</span><span class="sxs-lookup"><span data-stu-id="acdbc-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="acdbc-159">如果在 SharePoint 管理中心内选中 "**不允许在组织外共享**" 设置，则团队中的来宾访问将不起作用。</span><span class="sxs-lookup"><span data-stu-id="acdbc-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="acdbc-160">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="acdbc-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="acdbc-161">单击 "**管理中心**"，然后选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="acdbc-162">在 SharePoint 管理中心中，选择 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="acdbc-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="acdbc-163">请确保*未*选中 "**不允许在组织外部共享**" 选项。</span><span class="sxs-lookup"><span data-stu-id="acdbc-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![屏幕截图显示 SparePoint 联机设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="acdbc-165">步骤6：设置来宾用户权限</span><span class="sxs-lookup"><span data-stu-id="acdbc-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="acdbc-166">在 "团队" 应用程序中，在单个团队级别配置用于控制来宾是否可以创建、更新或删除频道的来宾权限。</span><span class="sxs-lookup"><span data-stu-id="acdbc-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="acdbc-167">团队管理员和团队所有者可以配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="acdbc-167">Teams admins as well as team owners can configure these settings.</span></span>

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="acdbc-169">若要了解有关来宾访问的详细信息，请参阅[团队中的来宾访问](guest-access.md)和[打开或关闭 Microsoft 团队的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="acdbc-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="acdbc-170">疑难解答</span><span class="sxs-lookup"><span data-stu-id="acdbc-170">Troubleshooting</span></span>

<span data-ttu-id="acdbc-171">如果您在设置来宾访问或在团队中添加来宾时遇到问题，请使用以下资源帮助您：</span><span class="sxs-lookup"><span data-stu-id="acdbc-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="acdbc-172">解决 Microsoft 团队中的来宾访问问题</span><span class="sxs-lookup"><span data-stu-id="acdbc-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="acdbc-173">团队疑难解答</span><span class="sxs-lookup"><span data-stu-id="acdbc-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



