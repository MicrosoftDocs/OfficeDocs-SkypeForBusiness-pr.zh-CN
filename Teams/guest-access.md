---
title: "在 Microsoft Teams 中管理来宾访问"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: f440e1d67166931365a24cb18e855a179fc532ef
ms.sourcegitcommit: 34abc255257716ab135e8eda7b07f8abb55a6bc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2017
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="80a42-103">在 Microsoft Teams 中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="80a42-103">Manage guest access in Microsoft Teams</span></span>
======================================


<span data-ttu-id="80a42-104">利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。</span><span class="sxs-lookup"><span data-stu-id="80a42-104">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="80a42-105">来宾是贵组织的员工、学生和成员以外的任何人。</span><span class="sxs-lookup"><span data-stu-id="80a42-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="80a42-106">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="80a42-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="80a42-107">例如，来宾可以包括合作伙伴、供应商、提供商或顾问。</span><span class="sxs-lookup"><span data-stu-id="80a42-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span>
  
    
    

<span data-ttu-id="80a42-108">使用 Teams 的组织可以向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。</span><span class="sxs-lookup"><span data-stu-id="80a42-108">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="80a42-109">Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。</span><span class="sxs-lookup"><span data-stu-id="80a42-109">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="80a42-110">Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="80a42-110">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="80a42-111">Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。</span><span class="sxs-lookup"><span data-stu-id="80a42-111">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>
  
    
    

## <a name="how-a-guest-joins-a-team"></a><span data-ttu-id="80a42-112">来宾加入团队的方式</span><span class="sxs-lookup"><span data-stu-id="80a42-112">How a guest joins a team</span></span>


  
    
    
<span data-ttu-id="80a42-113">Teams 中的团队所有者可以通过 Web 或桌面在其团队中添加和管理来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-113">A team owner in Teams can add and manage guests in their teams via the web or desktop.</span></span> <span data-ttu-id="80a42-114">仅拥有与 Azure Active Directory 或 Office 365 工作或学校帐户对应的电子邮件地址的用户可以添加为来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-114">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="80a42-115">管理员必须在 Teams 中启用来宾访问，来宾才可以加入团队。</span><span class="sxs-lookup"><span data-stu-id="80a42-115">Before guests can join a team, an admin must enable guest access in Teams.</span></span> <span data-ttu-id="80a42-116">为此，请使用你的 Office 365 全局管理员帐户[登录](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="80a42-116">To do that,  [sign in](https://portal.office.com/adminportal/home) with your Office 365 global admin account.</span></span> <span data-ttu-id="80a42-117">然后选择**“设置”** > **“服务&amp;和外接程序”** > **“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-117">Then, choose **Settings** > **Services &amp; add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="80a42-118">在**“选择要配置的用户/许可证类型”**中选择**“来宾”**，然后在**“对此类型的所有用户开启或关闭 Microsoft Teams”**中选择**“开启”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-118">Select **Guest** in **Select the user/license type you want to configure**, and select **On** in **Turn Microsoft Teams on or off for all users of this type**.</span></span> <span data-ttu-id="80a42-119">最长可能需要一个小时，设置将会生效。</span><span class="sxs-lookup"><span data-stu-id="80a42-119">It can take up to an hour for the settings to take effect.</span></span> <span data-ttu-id="80a42-120">有关更多详细信息，请参阅本文的“管理”选项卡中的“开启或关闭 Microsoft Teams 的来宾访问”。</span><span class="sxs-lookup"><span data-stu-id="80a42-120">For more details, see "Turn on or off guest access for Microsoft Teams" on this article's Manage tab.</span></span> 
  
    
    

<span data-ttu-id="80a42-121">下面介绍来宾如何成为团队成员：</span><span class="sxs-lookup"><span data-stu-id="80a42-121">Here's how a guest becomes a member of a team:</span></span>
  
    
    

- <span data-ttu-id="80a42-122">**第 1 步** 团队所有者或 Office 365 管理员[向团队添加来宾](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)。</span><span class="sxs-lookup"><span data-stu-id="80a42-122">**Step 1** A team owner or an Office 365 admin [adds a guest to a team](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests).</span></span>
    
  
- <span data-ttu-id="80a42-123">**第 2 步** Office 365 管理员或团队所有者可以根据需要管理来宾的权限。</span><span class="sxs-lookup"><span data-stu-id="80a42-123">**Step 2** The Office 365 admin or the team owner can manage a guest's capabilities as necessary.</span></span> <span data-ttu-id="80a42-124">例如，允许来宾添加或删除频道，或者禁用对文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="80a42-124">For example, allowing a guest to add or delete channels or disabling access to files.</span></span>
    
  
- <span data-ttu-id="80a42-125">**第 3 步** 来宾收到来自团队所有者的欢迎电子邮件，邀请其加入团队。</span><span class="sxs-lookup"><span data-stu-id="80a42-125">**Step 3** The guest receives a welcome email from the team owner, inviting them to join the team.</span></span> <span data-ttu-id="80a42-126">来宾接受邀请后，可以[参与团队和频道](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels)、接收和响应频道消息、[访问频道中的文件](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)以及参与聊天。</span><span class="sxs-lookup"><span data-stu-id="80a42-126">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels), receive and respond to channel messages, [access files in channels](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), and participate in chat.</span></span> <span data-ttu-id="80a42-127">使用 Teams 时，文本和图标相结合为所有团队成员提供了来宾参与团队情况的清晰说明。</span><span class="sxs-lookup"><span data-stu-id="80a42-127">While using Teams, a combination of text and icons gives all team members clear indication of guest participation in a team.</span></span> <span data-ttu-id="80a42-128">有关更多详细信息，请参阅[来宾体验介绍](#guestexp)</span><span class="sxs-lookup"><span data-stu-id="80a42-128">For more details, see [what the guest experience is like](#guestexp)</span></span>
    
  
<span data-ttu-id="80a42-129">来宾随时可以通过 Teams Web 和桌面客户端离开团队。</span><span class="sxs-lookup"><span data-stu-id="80a42-129">Guests can leave the team at any time via Teams web and desktop clients.</span></span> <span data-ttu-id="80a42-130">有关详细信息，请参阅[如何离开团队？](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)</span><span class="sxs-lookup"><span data-stu-id="80a42-130">For details, see  [How do I leave a team?](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="80a42-131">仅贵组织外部的人员（例如，合作伙伴或顾问）可以添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-131">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="80a42-132">贵组织中的人员可以作为常规团队成员加入。</span><span class="sxs-lookup"><span data-stu-id="80a42-132">People from within your organization can join as regular team members.</span></span> 
  
    
    

<a name="guestexp"></a>
## <a name="what-the-guest-experience-is-like"></a><span data-ttu-id="80a42-133">来宾体验介绍</span><span class="sxs-lookup"><span data-stu-id="80a42-133">What the guest experience is like</span></span>

<span data-ttu-id="80a42-134">来宾受邀加入团队时，会收到欢迎电子邮件，其中包括有关团队的一些信息以及成为成员后应做些什么。</span><span class="sxs-lookup"><span data-stu-id="80a42-134">When a guest is invited to join a team, they receive a welcome email message that includes some information about the team and what to expect now that they're a member.</span></span> <span data-ttu-id="80a42-135">来宾必须接受电子邮件中的邀请才能访问团队及其频道。</span><span class="sxs-lookup"><span data-stu-id="80a42-135">The guest must redeem the invitation in the email message before they can access the team and its channels.</span></span>
  
    
    

  
    
    
![此屏幕截图显示了 Microsoft Teams 中的一个团队所有者向一个来宾用户发送的欢迎电子邮件。](media/bc0deb82-6394-4280-8fed-312645c8fefe.png)
  
    
    
<span data-ttu-id="80a42-138">所有团队成员将在频道线索中看到一条消息，告知团队所有者添加了来宾并提供该来宾的姓名。</span><span class="sxs-lookup"><span data-stu-id="80a42-138">All team members see a message in the channel thread announcing that the team owner has added a guest and providing the guest's name.</span></span> <span data-ttu-id="80a42-139">团队中的所有人都可以轻松识别谁是来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-139">Everyone on the team can identify easily who is a guest.</span></span> <span data-ttu-id="80a42-140">如以下示例团队屏幕截图中所示，横幅显示“This team has guests”，每个来宾的姓名旁边显示“GUEST”标签。</span><span class="sxs-lookup"><span data-stu-id="80a42-140">As shown in the following screenshot of a sample team, a banner indicates "This team has guests" and a "GUEST" label appears next to each guest's name.</span></span>
  
    
    

  
    
    
![此屏幕截图显示了 Northwind Traders 的 Marketing 频道的一部分，顶部横幅中的通知显示“This team has guests”，身为来宾的用户通过其姓名旁边的词语“GUEST”标识。](media/33394a31-7d10-4950-8b39-b7d9953397c3.png)
  
    
    
<span data-ttu-id="80a42-142">下表比较了组织的团队成员可用的 Microsoft Teams 功能和团队的来宾用户可用的功能。</span><span class="sxs-lookup"><span data-stu-id="80a42-142">The following table compares the Microsoft Teams functionality available for an organization's team members to the functionality available for a guest user on the team.</span></span>
  
    
    


|<span data-ttu-id="80a42-143">**Teams 中的功能**</span><span class="sxs-lookup"><span data-stu-id="80a42-143">**Capability in Teams**</span></span>|<span data-ttu-id="80a42-144">**组织中的 Teams 用户**</span><span class="sxs-lookup"><span data-stu-id="80a42-144">**Teams user in the organization**</span></span>|<span data-ttu-id="80a42-145">**来宾用户**</span><span class="sxs-lookup"><span data-stu-id="80a42-145">**Guest user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80a42-146">创建频道</span><span class="sxs-lookup"><span data-stu-id="80a42-146">Create a channel</span></span>  <br/>  <span data-ttu-id="80a42-147">*团队所有者控制此设置。*</span><span class="sxs-lookup"><span data-stu-id="80a42-147">*Team owners control this setting.*</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-150">参与私人聊天</span><span class="sxs-lookup"><span data-stu-id="80a42-150">Participate in a private chat</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-153">参与频道对话</span><span class="sxs-lookup"><span data-stu-id="80a42-153">Participate in a channel conversation</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-156">发布、删除和编辑消息</span><span class="sxs-lookup"><span data-stu-id="80a42-156">Post, delete, and edit messages</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-159">共享频道文件</span><span class="sxs-lookup"><span data-stu-id="80a42-159">Share a channel file</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-162">共享聊天文件</span><span class="sxs-lookup"><span data-stu-id="80a42-162">Share a chat file</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="80a42-164">添加应用（选项卡、聊天机器人或连接器）</span><span class="sxs-lookup"><span data-stu-id="80a42-164">Add apps (tabs, bots, or connectors)</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="80a42-166">创建租户范围和团队/频道来宾访问策略</span><span class="sxs-lookup"><span data-stu-id="80a42-166">Create tenant-wide and teams/channels guest access policies</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="80a42-168">邀请 Office 365 租户的域外部的用户</span><span class="sxs-lookup"><span data-stu-id="80a42-168">Invite a user outside the Office 365 tenant's domain</span></span>  <br/> ||![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="80a42-170">创建团队</span><span class="sxs-lookup"><span data-stu-id="80a42-170">Create a team</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="80a42-172">发现和加入公用团队</span><span class="sxs-lookup"><span data-stu-id="80a42-172">Discover and join a public team</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="80a42-174">查看组织结构图</span><span class="sxs-lookup"><span data-stu-id="80a42-174">View organization chart</span></span>  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
   

    
> [!NOTE]
> <span data-ttu-id="80a42-176">Office 365 管理员控制来宾可用的功能。</span><span class="sxs-lookup"><span data-stu-id="80a42-176">Office 365 admins control the features available to guests.</span></span> 
  
    
## <a name="manage-guests"></a><span data-ttu-id="80a42-177">管理来宾</span><span class="sxs-lookup"><span data-stu-id="80a42-177">Manage guests</span></span>


<span data-ttu-id="80a42-178">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="80a42-178">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="80a42-179">无需额外的 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="80a42-179">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="80a42-180">Teams 来宾访问是租户级别设置，默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="80a42-180">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="80a42-181">管理员可以通过 Office 365 管理中心管理来宾访问。</span><span class="sxs-lookup"><span data-stu-id="80a42-181">Admins can manage guest access via the Office 365 admin center.</span></span> <span data-ttu-id="80a42-182">有关更多详细信息，请参阅[管理对 Microsoft Teams 的来宾访问](#manageguest)和[控制对 Microsoft Teams 的来宾访问](#controlguest)。</span><span class="sxs-lookup"><span data-stu-id="80a42-182">For more details, see [Manage guest access to Microsoft Teams](#manageguest) and [Control guest access to Microsoft Teams](#controlguest).</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="80a42-183">Teams 来宾访问租户设置仅阻止来宾登录。</span><span class="sxs-lookup"><span data-stu-id="80a42-183">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="80a42-184">团队所有者将能够邀请新来宾以及向其各自团队添加现有目录来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-184">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="80a42-185">请注意，Teams 始终支持 Azure Active Directory 外部设置以允许或阻止向租户添加来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-185">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="80a42-186">此外，你还可以使用 Azure Active Directory 门户管理来宾及其对 Office 365 和 Teams 资源的访问。</span><span class="sxs-lookup"><span data-stu-id="80a42-186">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="80a42-187">Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="80a42-187">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="80a42-188">要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="80a42-188">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  
    
    

#### <a name="related-key-services-and-dependencies"></a><span data-ttu-id="80a42-189">相关关键服务和相依性</span><span class="sxs-lookup"><span data-stu-id="80a42-189">Related key services and dependencies</span></span>

<span data-ttu-id="80a42-190">Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。</span><span class="sxs-lookup"><span data-stu-id="80a42-190">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="80a42-191">此外，Teams 还依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。</span><span class="sxs-lookup"><span data-stu-id="80a42-191">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span>
  
    
    
<span data-ttu-id="80a42-192">为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择**“开启”**：</span><span class="sxs-lookup"><span data-stu-id="80a42-192">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="80a42-193">在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**</span><span class="sxs-lookup"><span data-stu-id="80a42-193">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="80a42-194">有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。</span><span class="sxs-lookup"><span data-stu-id="80a42-194">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="80a42-195">在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**</span><span class="sxs-lookup"><span data-stu-id="80a42-195">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="80a42-196">有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。</span><span class="sxs-lookup"><span data-stu-id="80a42-196">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
    
  

#### <a name="turn-on-or-off-guest-access-for-microsoft-teams"></a><span data-ttu-id="80a42-197">为 Microsoft Teams 开启或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="80a42-197">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="80a42-198"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-198"></span></span>


1. <span data-ttu-id="80a42-199">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="80a42-199">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="80a42-200">在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-200">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![登录 Office 365，访问 Office 365 管理中心，转到“设置”，然后选择“服务&amp;和外接程序”](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="80a42-202">选择**“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-202">Select **Microsoft Teams**.</span></span>
    
     ![此屏幕截图显示了在 Office 365 管理中心中选择的 Microsoft Teams 外接程序对应的选项。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="80a42-204">在**“选择要配置的用户/许可证类型”**中，选择**“来宾”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-204">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
    
  
![Microsoft Teams 外接程序的屏幕截图显示选择了“来宾”许可证且 Microsoft Teams 选项设置为“开启”。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
  
  
5. <span data-ttu-id="80a42-206">单击或点击**“对此类型的所有用户开启或关闭 Microsoft Teams”**旁边的切换将其设置为**“开启”**为贵组织开启 Teams 和来宾访问，然后选择**“保存”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-206">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  
> [!NOTE]
> <span data-ttu-id="80a42-207">最长可能需要一个小时，设置将会生效。</span><span class="sxs-lookup"><span data-stu-id="80a42-207">It can take up to an hour for the settings to take effect.</span></span> 
  
    
## <a name="control-adding-guest-users-to-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="80a42-208">控制向 Microsoft Teams 和 Office 365 组添加来宾用户</span><span class="sxs-lookup"><span data-stu-id="80a42-208">Control adding guest users to Microsoft Teams and Office 365 Groups</span></span>
<span data-ttu-id="80a42-209"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-209"></span></span>


1. <span data-ttu-id="80a42-210">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="80a42-210">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="80a42-211">在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-211">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="80a42-212">选择**“Office 365 组”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-212">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="80a42-214">在“Office 365 组”页面上，将切换设置为**“开启”**或**“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="80a42-214">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="80a42-215">单击或点击**“允许组所有者将组织外部的人员添加到组”**旁边的切换将其设置为**“开启”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-215">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>
    
    
  
    
    
![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
  
  
  
<span data-ttu-id="80a42-217"><a name="controlguest"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-217"></span></span>
## <a name="turn-on-or-off-the-sharing-option-for-office-365"></a><span data-ttu-id="80a42-218">为 Office 365 开启或关闭“共享”选项。</span><span class="sxs-lookup"><span data-stu-id="80a42-218">Turn on or off the Sharing option for Office 365</span></span>


<span data-ttu-id="80a42-219">“共享”选项用于允许将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="80a42-219">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="80a42-220">默认情况下，启用“共享”选项。</span><span class="sxs-lookup"><span data-stu-id="80a42-220">By default, neither option is enabled.</span></span> <span data-ttu-id="80a42-221">有关如何关闭“共享”选项的信息，请参阅[开启或关闭“共享”选项](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)。</span><span class="sxs-lookup"><span data-stu-id="80a42-221">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
    
    

> [!IMPORTANT]
> <span data-ttu-id="80a42-222">如果你关闭“共享”选项，则来宾访问不可用。</span><span class="sxs-lookup"><span data-stu-id="80a42-222">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="use-powershell-to-control-guest-access"></a><span data-ttu-id="80a42-223">使用 PowerShell 控制来宾访问</span><span class="sxs-lookup"><span data-stu-id="80a42-223">Use PowerShell to control guest access</span></span>
<span data-ttu-id="80a42-224"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-224"></span></span>

<span data-ttu-id="80a42-225">除了使用 Office 365 管理中心和 Azure Active Directory 门户外，你还可以使用 Windows PowerShell 控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="80a42-225">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="80a42-226">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80a42-226">With PowerShell, you can do the following:</span></span>
  
    
    

- <span data-ttu-id="80a42-227">允许或阻止来宾访问所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="80a42-227">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="80a42-228">允许将来宾添加到所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="80a42-228">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="80a42-229">在特定团队或 Office 365 组中允许或阻止来宾用户</span><span class="sxs-lookup"><span data-stu-id="80a42-229">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="80a42-230">有关更多详细信息，请参阅[使用 PowerShell 控制来宾访问](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)。</span><span class="sxs-lookup"><span data-stu-id="80a42-230">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="80a42-231">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-231">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="80a42-232">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="80a42-232">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="80a42-233">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="80a42-233">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="80a42-234">有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="80a42-234">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
    
    
<span data-ttu-id="80a42-235"><a name="manageguest"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-235"></span></span>
### <a name="view-guest-users"></a><span data-ttu-id="80a42-236">查看来宾用户</span><span class="sxs-lookup"><span data-stu-id="80a42-236">View guest users</span></span>



1. <span data-ttu-id="80a42-237">在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="80a42-237">Sign in with your Office 365 global admin account at  [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="80a42-238">转到**“用户”** > **“来宾用户”**。</span><span class="sxs-lookup"><span data-stu-id="80a42-238">Go to **Users** > **Guest users**.</span></span>
    
    
  
    
    
![此屏幕截图显示了在 Office 365 管理中心的“用户”部分中选择了“来宾用户”选项。](media/95b83ff5-72ef-4668-b541-4e25b767620a.png)
  
    

## <a name="invite-guest-users"></a><span data-ttu-id="80a42-240">邀请来宾用户</span><span class="sxs-lookup"><span data-stu-id="80a42-240">Invite guest users</span></span>
<span data-ttu-id="80a42-241"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-241"></span></span>

<span data-ttu-id="80a42-242">团队所有者或 Office 365 管理员可以单个[邀请来宾加入团队](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)。</span><span class="sxs-lookup"><span data-stu-id="80a42-242">A team owner or an Office 365 admin can [invite a guest to a team](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) on an individual basis.</span></span> <span data-ttu-id="80a42-243">但是，管理员无法使用 Office 365 管理中心或 Azure Active Directory 门户一次邀请多个来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-243">However, admins can't use the Office 365 admin center or the Azure Active Directory portal to invite multiple guests in one action.</span></span> <span data-ttu-id="80a42-244">要集中邀请来宾，请考虑使用 Azure Active Directory B2B 协作预览版。</span><span class="sxs-lookup"><span data-stu-id="80a42-244">To invite guests centrally, consider using the Azure Active Directory B2B collaboration preview.</span></span> <span data-ttu-id="80a42-245">有关详细信息，请参阅[关于 Azure AD B2B 协作预览](https://go.microsoft.com/fwlink/p/?linkid=853011)。</span><span class="sxs-lookup"><span data-stu-id="80a42-245">For more information, see [About the Azure AD B2B collaboration preview](https://go.microsoft.com/fwlink/p/?linkid=853011).</span></span>
  
    
    

## <a name="edit-guest-user-information"></a><span data-ttu-id="80a42-246">编辑来宾用户信息</span><span class="sxs-lookup"><span data-stu-id="80a42-246">Edit guest user information</span></span>
<span data-ttu-id="80a42-247"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-247"></span></span>

<span data-ttu-id="80a42-248">当前，无法在 Office 365 管理中心或 Exchange 管理中心中编辑来宾信息。</span><span class="sxs-lookup"><span data-stu-id="80a42-248">Currently, you can't edit guest information from the Office 365 admin center or the Exchange admin center.</span></span> <span data-ttu-id="80a42-249">要编辑来宾帐户（例如，显示名称或个人资料照片），请访问 Azure Active Directory 门户。</span><span class="sxs-lookup"><span data-stu-id="80a42-249">To edit guest accounts (such as display name or profile photo), go to your Azure Active Directory portal.</span></span> <span data-ttu-id="80a42-250">有关详细信息，请参阅[了解 Office 365 标识和 Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)。</span><span class="sxs-lookup"><span data-stu-id="80a42-250">For more information, see [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span></span>
  
    
    
## <a name="frequently-asked-questions-for-admins"></a><span data-ttu-id="80a42-251">管理员的常见问题</span><span class="sxs-lookup"><span data-stu-id="80a42-251">Frequently asked questions for admins</span></span>
<span data-ttu-id="80a42-252"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="80a42-252"></span></span>

<span data-ttu-id="80a42-253">下面是 Office 365 管理员面临的有关在 Microsoft Teams 中邀请来宾加入团队的常见问题。</span><span class="sxs-lookup"><span data-stu-id="80a42-253">Here are common questions Office 365 admins have about inviting guests to join a team in Microsoft Teams.</span></span>
  
    
    

#### <a name="what-is-a-guest"></a><span data-ttu-id="80a42-254">来宾是什么？</span><span class="sxs-lookup"><span data-stu-id="80a42-254">What is a template?</span></span>


  
    
    
<span data-ttu-id="80a42-255">来宾不是贵组织的员工、学生和成员。</span><span class="sxs-lookup"><span data-stu-id="80a42-255">A guest is not an employee, student, or member of your organization.</span></span> <span data-ttu-id="80a42-256">他们在贵组织没有学校或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="80a42-256">They don't have a school or work account with your organization.</span></span>
  
    
    

  
    
    

#### <a name="who-can-be-added-as-a-guest-user"></a><span data-ttu-id="80a42-257">哪些人可以添加为来宾用户？</span><span class="sxs-lookup"><span data-stu-id="80a42-257">Who can be added as a guest user?</span></span>

<span data-ttu-id="80a42-258">仅拥有与 Azure Active Directory 或 Office 365 工作或学校帐户对应的电子邮件地址的用户可以添加为来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-258">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

#### <a name="can-users-add-people-within-my-organization-who-are-not-part-of-the-team-as-a-guest"></a><span data-ttu-id="80a42-259">用户是否可以将我的组织中不属于团队的人员添加为来宾？</span><span class="sxs-lookup"><span data-stu-id="80a42-259">Can users add people within my organization who are not part of the team as a guest?</span></span>

<span data-ttu-id="80a42-260">仅贵组织外部的人员（例如，合作伙伴或顾问）可以添加为来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-260">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="80a42-261">用户可以将贵组织中的人员作为常规团队成员或订阅者邀请加入。</span><span class="sxs-lookup"><span data-stu-id="80a42-261">Users can invite people from within your organization to join as regular team members or subscribers.</span></span>
  
    
    

#### <a name="why-does-a-user-get-the-message-contact-your-administrator-when-they-try-to-add-a-guest-to-their-team"></a><span data-ttu-id="80a42-262">为什么用户尝试将来宾添加到其团队时收到消息“请与管理员联系。”？</span><span class="sxs-lookup"><span data-stu-id="80a42-262">Why does a user get the message "Contact your administrator" when they try to add a guest to their team?</span></span>

<span data-ttu-id="80a42-263">作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-263">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> <span data-ttu-id="80a42-264">用户看到该消息时，可能是未启用来宾功能。</span><span class="sxs-lookup"><span data-stu-id="80a42-264">When a user sees that message, it's likely that the guest feature hasn't been enabled.</span></span>
  
    
    

#### <a name="how-can-a-global-admin-add-a-new-guest-user-to-the-organization"></a><span data-ttu-id="80a42-265">全局管理员如何将新来宾用户添加到组织？</span><span class="sxs-lookup"><span data-stu-id="80a42-265">How can a global admin add a new guest user to the organization?</span></span>

<span data-ttu-id="80a42-266">作为全局管理员，你可以采用多种方式将新来宾用户添加到组织：</span><span class="sxs-lookup"><span data-stu-id="80a42-266">As a global admin, you can add a new guest user to the organization in a couple ways:</span></span>
  
    
    

- <span data-ttu-id="80a42-267">身为团队所有者的全局管理员和团队所有者可以通过 Microsoft Teams 桌面客户端或 Web 客户端[将来宾添加到团队](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)。</span><span class="sxs-lookup"><span data-stu-id="80a42-267">Global admins who are owners of a team and owners of a team can [add a guest to a team](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) through either the Microsoft Teams desktop or the web clients.</span></span>
    
  
- <span data-ttu-id="80a42-268">通过 Azure Active Directory B2B 协作将来宾添加到贵组织。</span><span class="sxs-lookup"><span data-stu-id="80a42-268">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="80a42-269">利用 Azure Active Directory B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-269">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="80a42-270">有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?LinkId=826383)。</span><span class="sxs-lookup"><span data-stu-id="80a42-270">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?LinkId=826383).</span></span>
    
  

#### <a name="is-there-a-way-to-block-individual-guest-users"></a><span data-ttu-id="80a42-271">是否有办法阻止单个来宾用户？</span><span class="sxs-lookup"><span data-stu-id="80a42-271">Is there a way to block individual guest users?</span></span>

<span data-ttu-id="80a42-272">没有，无法阻止单个来宾用户。</span><span class="sxs-lookup"><span data-stu-id="80a42-272">No, individual guest users can't be blocked.</span></span>
  
    
    

#### <a name="can-global-admins-block-guests-in-teams-and-still-allow-guests-to-access-sharepoint-sites"></a><span data-ttu-id="80a42-273">全局管理员是否可以在团队中阻止来宾，但仍允许来宾访问 SharePoint 网站？</span><span class="sxs-lookup"><span data-stu-id="80a42-273">Can global admins block guests in teams and still allow guests to access SharePoint sites?</span></span>

<span data-ttu-id="80a42-274">是，全局管理员可以使用 Azure Active Directory Powershell cmdlet 在“公司”对象上禁用 _AllowGuestAccessToGroups_ 参数，前提是为 SharePoint 网站开启了外部共享。</span><span class="sxs-lookup"><span data-stu-id="80a42-274">Yes, global admins can use Azure Active Directory Powershell cmdlets to disable the  _AllowGuestAccessToGroups_ parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>
  
    
    

#### <a name="what-other-controls-are-available-to-it-admins-to-manage-guests-in-microsoft-teams"></a><span data-ttu-id="80a42-275">IT 管理员可以使用哪些其他控制功能在 Microsoft Teams 中管理来宾？</span><span class="sxs-lookup"><span data-stu-id="80a42-275">What other controls are available to IT admins to manage guests in Microsoft Teams?</span></span>

<span data-ttu-id="80a42-276">IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。</span><span class="sxs-lookup"><span data-stu-id="80a42-276">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="80a42-277">这些控制功能通过 Office 365 管理中心提供。</span><span class="sxs-lookup"><span data-stu-id="80a42-277">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="80a42-278">来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。</span><span class="sxs-lookup"><span data-stu-id="80a42-278">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

#### <a name="can-users-share-a-team-file-with-an-external-user-who-isnt-a-member-of-the-team"></a><span data-ttu-id="80a42-279">用户是否可以与不是团队成员的外部用户共享团队文件？</span><span class="sxs-lookup"><span data-stu-id="80a42-279">Can users share a team file with an external user who isn't a member of the team?</span></span>

<span data-ttu-id="80a42-280">不可以。</span><span class="sxs-lookup"><span data-stu-id="80a42-280">No.</span></span> <span data-ttu-id="80a42-281">用户只能与受邀加入团队的来宾共享 Microsoft Teams 文件。</span><span class="sxs-lookup"><span data-stu-id="80a42-281">Users can only share Microsoft Teams files with guests who have been invited to join the team.</span></span>
  
    
    

#### <a name="is-an-additional-office-365-license-required-for-guest-access"></a><span data-ttu-id="80a42-282">来宾访问是否需要额外的 Office 365 许可证？</span><span class="sxs-lookup"><span data-stu-id="80a42-282">Is an additional Office 365 license required for guest access?</span></span>

<span data-ttu-id="80a42-283">不需要额外的许可证。</span><span class="sxs-lookup"><span data-stu-id="80a42-283">No additional license is required.</span></span> <span data-ttu-id="80a42-284">所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。</span><span class="sxs-lookup"><span data-stu-id="80a42-284">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span>
  
    
    

#### <a name="do-office-365-and-azure-active-directory-service-limits-apply-to-guests"></a><span data-ttu-id="80a42-285">Office 365 和 Azure Active Directory 服务限制是否适用于来宾？</span><span class="sxs-lookup"><span data-stu-id="80a42-285">Do Office 365 and Azure Active Directory service limits apply to guests?</span></span>

<span data-ttu-id="80a42-286">是，来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。</span><span class="sxs-lookup"><span data-stu-id="80a42-286">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    

  
    
    

#### <a name="how-long-does-it-take-until-the-guest-user-settings-take-effect-in-the-office-365-organization"></a><span data-ttu-id="80a42-287">来宾用户设置在 Office 365 组织中生效需要多长时间？</span><span class="sxs-lookup"><span data-stu-id="80a42-287">How long does it take until the guest user settings take effect in the Office 365 organization?</span></span>

<span data-ttu-id="80a42-288">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="80a42-288">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="80a42-289">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="80a42-289">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span>
  
    
    

#### <a name="can-a-global-admin-manage-sharepoint-online-external-user-settings-for-the-teams-connected-team-site"></a><span data-ttu-id="80a42-290">全局管理员是否可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置？</span><span class="sxs-lookup"><span data-stu-id="80a42-290">Can a global admin manage SharePoint Online external user settings for the Teams connected team site?</span></span>

<span data-ttu-id="80a42-291">是，你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。</span><span class="sxs-lookup"><span data-stu-id="80a42-291">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="80a42-292">有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="80a42-292">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
  
    
    

  
    
    

#### <a name="how-does-conditional-access-work-with-guest-access"></a><span data-ttu-id="80a42-293">条件访问是否适用于来宾访问？</span><span class="sxs-lookup"><span data-stu-id="80a42-293">How does conditional access work with guest access?</span></span>

<span data-ttu-id="80a42-294">利用 Azure Active Directory B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。</span><span class="sxs-lookup"><span data-stu-id="80a42-294">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="80a42-295">可以在租户、应用或单个用户级别强制应用这些策略，方式与对组织的全职员工和成员启用它们一样。</span><span class="sxs-lookup"><span data-stu-id="80a42-295">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="80a42-296">此类策略在资源组织上强制应用。</span><span class="sxs-lookup"><span data-stu-id="80a42-296">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="80a42-297">有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="80a42-297">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span>
  
    
    

#### <a name="if-i-have-a-team-with-an-office-365-group-and-i-add-a-guest-to-the-group-does-that-user-automatically-get-access-to-the-team"></a><span data-ttu-id="80a42-298">如果我有一个使用 Office 365 组的团队，我向该组添加来宾后，该用户是否自动获取访问团队的权限？</span><span class="sxs-lookup"><span data-stu-id="80a42-298">If I have a team with an Office 365 group, and I add a guest to the group, does that user automatically get access to the team?</span></span>

<span data-ttu-id="80a42-299">是，来宾将获取访问团队的权限。</span><span class="sxs-lookup"><span data-stu-id="80a42-299">Yes, the guest will get access to the team.</span></span> <span data-ttu-id="80a42-300">通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-300">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>
  
    
    

#### <a name="what-event-appears-in-the-audit-log-to-indicate-a-guest-has-been-sent-an-invitation"></a><span data-ttu-id="80a42-301">审核日志中的什么事件指示已向来宾发送邀请？</span><span class="sxs-lookup"><span data-stu-id="80a42-301">What event appears in the audit log to indicate a guest has been sent an invitation?</span></span>

<span data-ttu-id="80a42-302">你可以在 Azure Active Directory 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。</span><span class="sxs-lookup"><span data-stu-id="80a42-302">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="80a42-303">在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。</span><span class="sxs-lookup"><span data-stu-id="80a42-303">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="80a42-304">有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="80a42-304">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>
  
    
    

#### <a name="if-i-have-existing-guest-users-that-were-added-via-azure-ad-b2b-office-365-groups-or-sharepoint-online-do-i-have-to-do-anything-else-with-them-for-microsoft-teams"></a><span data-ttu-id="80a42-305">如果我有通过 Azure AD B2B、Office 365 组或 SharePoint Online 添加的现有来宾用户，是否需要为了 Microsoft Teams 对其进行任何其他操作？</span><span class="sxs-lookup"><span data-stu-id="80a42-305">If I have existing guest users that were added via Azure AD B2B, Office 365 Groups, or SharePoint Online, do I have to do anything else with them for Microsoft Teams?</span></span>

<span data-ttu-id="80a42-306">你已通过 Azure Active Directory B2B、Office 365 组或 SharePoint Online 添加的来宾用户已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="80a42-306">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="80a42-307">Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。</span><span class="sxs-lookup"><span data-stu-id="80a42-307">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span>
  
    
    

#### <a name="if-external-accounts-are-available-does-that-mean-external-sharing-is-enabled"></a><span data-ttu-id="80a42-308">如果外部帐户可用，是否表示启用了外部共享？</span><span class="sxs-lookup"><span data-stu-id="80a42-308">If external accounts are available, does that mean external sharing is enabled?</span></span>

<span data-ttu-id="80a42-309">管理员可以在 Azure Active Directory 中创建来宾帐户，与外部共享设置无关。</span><span class="sxs-lookup"><span data-stu-id="80a42-309">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="80a42-310">如果外部共享处于关闭状态，则仅管理员可以创建来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="80a42-310">If external sharing is off, only an admin can create guest accounts.</span></span>
  
    
    

  
    
    

## <a name="more-information"></a><span data-ttu-id="80a42-311">更多信息</span><span class="sxs-lookup"><span data-stu-id="80a42-311">More information</span></span>

 [<span data-ttu-id="80a42-312">Microsoft Teams 的管理员设置</span><span class="sxs-lookup"><span data-stu-id="80a42-312">Administrator settings for Microsoft Teams</span></span>](https://support.office.com/en-us/article/Administrator-settings-for-Microsoft-Teams-3966a3f5-7e0f-4ea9-a402-41888f455ba2)
  
    
    
 [<span data-ttu-id="80a42-313">有关 Microsoft Teams 的常见问题 - 管理帮助</span><span class="sxs-lookup"><span data-stu-id="80a42-313">Frequently asked questions about Microsoft Teams - Admin Help</span></span>](https://support.office.com/en-us/article/Frequently-asked-questions-about-Microsoft-Teams-–-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)
  
    
    
 [<span data-ttu-id="80a42-314">向团队添加来宾</span><span class="sxs-lookup"><span data-stu-id="80a42-314">Adding guests to teams</span></span>](https://support.office.com/en-us/article/Adding-guests-to-teams-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)
  
    
    
<span data-ttu-id="80a42-315">视频：[深入了解来宾访问](https://go.microsoft.com/fwlink/p/?linkid=858791)</span><span class="sxs-lookup"><span data-stu-id="80a42-315">Video:  [Deep Dive into Guest Access](https://go.microsoft.com/fwlink/p/?linkid=858791)</span></span>
  
    
    

