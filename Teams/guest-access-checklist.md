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
ms.openlocfilehash: e7f019f2260b1e86b422f8b4238439fbd2f1607a
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37563488"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="9a7be-103">团队来宾访问清单</span><span class="sxs-lookup"><span data-stu-id="9a7be-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="9a7be-104">使用此清单可帮助你根据你的组织的首选项，在 Microsoft 团队中启用和配置来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="9a7be-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="9a7be-105">有关协作限制，请参阅[启用 B2B 外部协作和管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="9a7be-106">了解对来宾的限制</span><span class="sxs-lookup"><span data-stu-id="9a7be-106">Understand the limitations for guests</span></span>

<span data-ttu-id="9a7be-107">来宾体验由设计限制。</span><span class="sxs-lookup"><span data-stu-id="9a7be-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="9a7be-108">请确保你了解来宾体验，这样就不会尝试修复不存在问题的内容。</span><span class="sxs-lookup"><span data-stu-id="9a7be-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="9a7be-109">例如，下面列出了 Microsoft 团队中的来宾无法使用的一些功能：</span><span class="sxs-lookup"><span data-stu-id="9a7be-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="9a7be-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9a7be-110">OneDrive for Business</span></span>
- <span data-ttu-id="9a7be-111">在团队外搜索的人员</span><span class="sxs-lookup"><span data-stu-id="9a7be-111">People search outside of Teams</span></span>
- <span data-ttu-id="9a7be-112">日历、计划的会议或会议详细信息</span><span class="sxs-lookup"><span data-stu-id="9a7be-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="9a7be-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="9a7be-113">PSTN</span></span>
- <span data-ttu-id="9a7be-114">组织结构图</span><span class="sxs-lookup"><span data-stu-id="9a7be-114">Organization chart</span></span>
- <span data-ttu-id="9a7be-115">创建或修订团队</span><span class="sxs-lookup"><span data-stu-id="9a7be-115">Create or revise a team</span></span>
- <span data-ttu-id="9a7be-116">浏览团队</span><span class="sxs-lookup"><span data-stu-id="9a7be-116">Browse for a team</span></span>
- <span data-ttu-id="9a7be-117">将文件上传到人员间聊天</span><span class="sxs-lookup"><span data-stu-id="9a7be-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="9a7be-118">如果用户知道用户的完整电子邮件 ID，则来宾仍可搜索和查找他们的团队外的用户。</span><span class="sxs-lookup"><span data-stu-id="9a7be-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="9a7be-119">为避免这种情况，IT 管理员可以使用具有[范围的目录搜索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)的模式，这些模式能够将来宾限制在自己的虚拟 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="9a7be-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="9a7be-120">有关更多详细信息，请参阅[来宾体验](guest-experience.md)和[Office 365 组中的来宾访问](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="9a7be-121">来宾访问与外部访问（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="9a7be-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="9a7be-122">目前，Microsoft 团队不支持来宾 inviter 角色。</span><span class="sxs-lookup"><span data-stu-id="9a7be-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="9a7be-123">至少，"成员可邀请" 开关必须设置为 "是"，才能使来宾 access 在 Microsoft 团队中工作。</span><span class="sxs-lookup"><span data-stu-id="9a7be-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="9a7be-124">如果将 "成员可以邀请" 设置为 "否"，然后在 Office 365 组和 Microsoft 团队中启用来宾访问，则管理员可以控制你的目录的来宾邀请。</span><span class="sxs-lookup"><span data-stu-id="9a7be-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="9a7be-125">来宾位于目录中后，可通过非管理员成员的团队所有者将其添加到团队。</span><span class="sxs-lookup"><span data-stu-id="9a7be-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="9a7be-126">如果您的客人看到许可证错误</span><span class="sxs-lookup"><span data-stu-id="9a7be-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="9a7be-127">Microsoft 团队中的来宾访问使用 Azure Active Directory （Azure AD）商业到企业（B2B）和其许可模型。</span><span class="sxs-lookup"><span data-stu-id="9a7be-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="9a7be-128">如果您看到授权错误，请确保阅读[B2B 授权指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)以了解您的组织拥有的授权要求，以便用户能够邀请来宾加入您的组织。</span><span class="sxs-lookup"><span data-stu-id="9a7be-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="9a7be-129">需要注意的一些事项：</span><span class="sxs-lookup"><span data-stu-id="9a7be-129">A few things to remember:</span></span>

- <span data-ttu-id="9a7be-130">来宾是您的组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="9a7be-130">Guests are users outside your organization.</span></span> <span data-ttu-id="9a7be-131">您的员工、现场承包商、现场工程师等不能添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="9a7be-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="9a7be-132">这同样适用于您的会员。</span><span class="sxs-lookup"><span data-stu-id="9a7be-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="9a7be-133">来宾许可证按邀请的组织计入。</span><span class="sxs-lookup"><span data-stu-id="9a7be-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="9a7be-134">当你计算所需的许可证数量时，请考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="9a7be-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="9a7be-135">根据您的组织统计许可证，无论受邀的来宾来自其他 Office 365 租户还是使用其个人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9a7be-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="9a7be-136">□步骤1：在 Azure AD 企业到企业中配置设置</span><span class="sxs-lookup"><span data-stu-id="9a7be-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="9a7be-137">以租户管理员身份登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="9a7be-138">选择 " **Azure Active Directory** > **用户** > "**用户设置**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="9a7be-139">在 "**外部用户**" 下，选择 "**管理外部协作设置**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9a7be-140">此外，还可从 "**组织关系**" 页面获取**外部协作设置**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="9a7be-141">在 Azure Active Directory 中的 "**管理**" 下，转到 "**组织关系** > "**设置**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="9a7be-142">在 "**外部协作设置**" 页面上，选择要启用的策略。</span><span class="sxs-lookup"><span data-stu-id="9a7be-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="9a7be-143">**来宾用户权限受到限制**：此策略确定你的目录中的来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="9a7be-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="9a7be-144">选择 **"是"** 阻止来自某些目录任务的来宾，例如枚举用户、组或其他目录资源。</span><span class="sxs-lookup"><span data-stu-id="9a7be-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="9a7be-145">选择 "**否**"，为来宾提供与目录中普通用户相同的访问目录数据。</span><span class="sxs-lookup"><span data-stu-id="9a7be-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="9a7be-146">**来宾 inviter 角色中的管理员和用户可以邀请**：要允许管理员和 "来宾 inviter" 角色中的用户邀请来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="9a7be-147">**成员可以邀请**：若要允许你的目录的非管理员成员邀请来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="9a7be-148">如果您设置的**成员可以邀请**"**否**"，然后在 Office 365 组和 Microsoft 团队中启用来宾访问，则管理员可以控制您的目录的来宾邀请。</span><span class="sxs-lookup"><span data-stu-id="9a7be-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="9a7be-149">来宾位于目录中后，可通过非管理员成员的团队所有者将其添加到团队。</span><span class="sxs-lookup"><span data-stu-id="9a7be-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="9a7be-150">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="9a7be-151">**来宾可以邀请**：要允许来宾邀请其他来宾，请将此策略设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="9a7be-152">**启用来宾电子邮件一次性密码（预览版）**：有关一次性密码功能的详细信息，请参阅[通过电子邮件发送一次性密码身份验证（预览版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>

   - <span data-ttu-id="9a7be-153">**协作限制**：有关允许或阻止特定域的邀请的详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
    
## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="9a7be-154">□步骤2：配置 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="9a7be-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="9a7be-155">在 Microsoft 365 管理中心，转到 "**设置** > **服务" & "加载项** > "**Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="9a7be-156">确保将 **"组织" 访问组内容外的组成员**设置为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="9a7be-157">如果此设置处于关闭状态，则来宾将无法访问任何组内容。</span><span class="sxs-lookup"><span data-stu-id="9a7be-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="9a7be-158">确保**组所有者将组织外部的人员添加到 "组**" 设置为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="9a7be-159">如果此设置处于关闭状态，则团队所有者将无法添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="9a7be-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="9a7be-160">此设置至少必须启用才能支持来宾访问。</span><span class="sxs-lookup"><span data-stu-id="9a7be-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![屏幕截图显示 Office 365 组的切换](media/guest-access-checklist-office365.png)

<span data-ttu-id="9a7be-162">有关配置这些设置的详细说明，请参阅[在 office 365 组中管理来宾访问](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="9a7be-163">□步骤3：在租户级别启用来宾访问</span><span class="sxs-lookup"><span data-stu-id="9a7be-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="9a7be-164">至少，你必须在**Microsoft 团队管理中心**下为 microsoft 团队启用来宾访问。</span><span class="sxs-lookup"><span data-stu-id="9a7be-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="9a7be-165">在 "团队管理中心" 中，选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="9a7be-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="9a7be-166">将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="9a7be-168">在此同一页面上，配置所需的任何其他来宾设置。</span><span class="sxs-lookup"><span data-stu-id="9a7be-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="9a7be-169">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9a7be-169">Click **Save**.</span></span>

<span data-ttu-id="9a7be-170">有关详细说明，请参阅[打开或关闭对 Microsoft 团队的来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="9a7be-171">□步骤4：在 Office 365 中配置共享</span><span class="sxs-lookup"><span data-stu-id="9a7be-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="9a7be-172">请确保用户可以添加来宾。</span><span class="sxs-lookup"><span data-stu-id="9a7be-172">Make sure that users can add guests.</span></span> <span data-ttu-id="9a7be-173">操作方法如下：</span><span class="sxs-lookup"><span data-stu-id="9a7be-173">Here's how:</span></span>

1. <span data-ttu-id="9a7be-174">在 Microsoft 365 管理中心中，转到 "**设置** > **安全 & 隐私**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="9a7be-176">在 "**共享**" 中，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-176">In **Sharing**, select **Edit**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="9a7be-178">设置 "**允许用户向此组织添加新来宾** **"，然后**单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="9a7be-180">此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。</span><span class="sxs-lookup"><span data-stu-id="9a7be-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="9a7be-181">□步骤5：验证 SharePoint 中的共享设置</span><span class="sxs-lookup"><span data-stu-id="9a7be-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="9a7be-182">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="9a7be-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="9a7be-183">单击 "**管理中心**"，然后选择 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="9a7be-184">在 SharePoint 管理中心中，选择 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="9a7be-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="9a7be-185">请确保*未*选中 "**不允许在组织外部共享**" 选项。</span><span class="sxs-lookup"><span data-stu-id="9a7be-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![屏幕截图显示 SparePoint 联机设置切换的示例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="9a7be-187">□步骤6：启用频道的特定设置</span><span class="sxs-lookup"><span data-stu-id="9a7be-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="9a7be-188">在 "团队" 应用程序中，在单个团队级别配置来宾权限，以便来宾可以创建、更新和删除频道。</span><span class="sxs-lookup"><span data-stu-id="9a7be-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="9a7be-189">除了管理员，团队所有者还可以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="9a7be-189">In addition to admins,  team owners can configure this setting.</span></span>

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="9a7be-191">有关详细信息，包括操作方法视频，请参阅[Microsoft 团队中的来宾访问](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="9a7be-192">疑难解答</span><span class="sxs-lookup"><span data-stu-id="9a7be-192">Troubleshooting</span></span>

<span data-ttu-id="9a7be-193">如果您在 Microsoft 团队中添加来宾时遇到问题，请参阅[来宾 Access 疑难解答指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="9a7be-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


