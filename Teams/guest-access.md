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
<a name="manage-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理来宾访问
======================================


利用 Microsoft Teams 中的来宾访问功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。 来宾是贵组织的员工、学生和成员以外的任何人。 他们在贵组织没有学校或工作帐户。 例如，来宾可以包括合作伙伴、供应商、提供商或顾问。
  
    
    

使用 Teams 的组织可以向其合作伙伴提供对团队、频道中的文档、资源、聊天和应用的外部访问权限，同时对其自己的公司数据维护完全控制。

Teams 建立在 Office 365 组之上，为 Office 365 组提供访问共享资产的全新方式。 Teams 是实现在组/团队成员之间进行持久聊天的最佳解决方案。 Office 365 是针对一组共享团队资产（例如 SharePoint 网站或 Power BI 仪表板）提供跨应用成员身份的服务，以便团队可以有效且安全地协作。
  
    
    

## <a name="how-a-guest-joins-a-team"></a>来宾加入团队的方式


  
    
    
Teams 中的团队所有者可以通过 Web 或桌面在其团队中添加和管理来宾。 仅拥有与 Azure Active Directory 或 Office 365 工作或学校帐户对应的电子邮件地址的用户可以添加为来宾用户。
  
    
    

> [!NOTE]
> 管理员必须在 Teams 中启用来宾访问，来宾才可以加入团队。 为此，请使用你的 Office 365 全局管理员帐户[登录](https://portal.office.com/adminportal/home)。 然后选择**“设置”** > **“服务&amp;和外接程序”** > **“Microsoft Teams”**。 在**“选择要配置的用户/许可证类型”**中选择**“来宾”**，然后在**“对此类型的所有用户开启或关闭 Microsoft Teams”**中选择**“开启”**。 最长可能需要一个小时，设置将会生效。 有关更多详细信息，请参阅本文的“管理”选项卡中的“开启或关闭 Microsoft Teams 的来宾访问”。 
  
    
    

下面介绍来宾如何成为团队成员：
  
    
    

- **第 1 步** 团队所有者或 Office 365 管理员[向团队添加来宾](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)。
    
  
- **第 2 步** Office 365 管理员或团队所有者可以根据需要管理来宾的权限。 例如，允许来宾添加或删除频道，或者禁用对文件的访问权限。
    
  
- **第 3 步** 来宾收到来自团队所有者的欢迎电子邮件，邀请其加入团队。 来宾接受邀请后，可以[参与团队和频道](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels)、接收和响应频道消息、[访问频道中的文件](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)以及参与聊天。 使用 Teams 时，文本和图标相结合为所有团队成员提供了来宾参与团队情况的清晰说明。 有关更多详细信息，请参阅[来宾体验介绍](#guestexp)
    
  
来宾随时可以通过 Teams Web 和桌面客户端离开团队。 有关详细信息，请参阅[如何离开团队？](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)
  
    
    

> [!NOTE]
> 仅贵组织外部的人员（例如，合作伙伴或顾问）可以添加为来宾。 贵组织中的人员可以作为常规团队成员加入。 
  
    
    

<a name="guestexp"></a>
## <a name="what-the-guest-experience-is-like"></a>来宾体验介绍

来宾受邀加入团队时，会收到欢迎电子邮件，其中包括有关团队的一些信息以及成为成员后应做些什么。 来宾必须接受电子邮件中的邀请才能访问团队及其频道。
  
    
    

  
    
    
![此屏幕截图显示了 Microsoft Teams 中的一个团队所有者向一个来宾用户发送的欢迎电子邮件。 该邮件包括团队所有者可以自定义的文本以及 Teams 功能（例如，聊天、通话和会议）的简要说明。](media/bc0deb82-6394-4280-8fed-312645c8fefe.png)
  
    
    
所有团队成员将在频道线索中看到一条消息，告知团队所有者添加了来宾并提供该来宾的姓名。 团队中的所有人都可以轻松识别谁是来宾。 如以下示例团队屏幕截图中所示，横幅显示“This team has guests”，每个来宾的姓名旁边显示“GUEST”标签。
  
    
    

  
    
    
![此屏幕截图显示了 Northwind Traders 的 Marketing 频道的一部分，顶部横幅中的通知显示“This team has guests”，身为来宾的用户通过其姓名旁边的词语“GUEST”标识。](media/33394a31-7d10-4950-8b39-b7d9953397c3.png)
  
    
    
下表比较了组织的团队成员可用的 Microsoft Teams 功能和团队的来宾用户可用的功能。
  
    
    


|**Teams 中的功能**|**组织中的 Teams 用户**|**来宾用户**|
|:-----|:-----|:-----|
|创建频道  <br/>  *团队所有者控制此设置。*  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|参与私人聊天  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|参与频道对话  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|发布、删除和编辑消息  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|共享频道文件  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|共享聊天文件  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|添加应用（选项卡、聊天机器人或连接器）  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|创建租户范围和团队/频道来宾访问策略  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|邀请 Office 365 租户的域外部的用户  <br/> ||![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|创建团队  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|发现和加入公用团队  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|查看组织结构图  <br/> |![checkmark](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
   

    
> [!NOTE]
> Office 365 管理员控制来宾可用的功能。 
  
    
## <a name="manage-guests"></a>管理来宾


所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。 无需额外的 Office 365 许可证。
  
    
    
Teams 来宾访问是租户级别设置，默认情况下关闭。 管理员可以通过 Office 365 管理中心管理来宾访问。 有关更多详细信息，请参阅[管理对 Microsoft Teams 的来宾访问](#manageguest)和[控制对 Microsoft Teams 的来宾访问](#controlguest)。
  
    
    

> [!NOTE]
> Teams 来宾访问租户设置仅阻止来宾登录。 团队所有者将能够邀请新来宾以及向其各自团队添加现有目录来宾用户。 请注意，Teams 始终支持 Azure Active Directory 外部设置以允许或阻止向租户添加来宾用户。 
  
    
    

此外，你还可以使用 Azure Active Directory 门户管理来宾及其对 Office 365 和 Teams 资源的访问。 Teams 来宾访问利用 Azure Active Directory 企业到企业 (B2B) 协作功能作为基础结构来存储安全主体信息，例如，标识属性、成员身份以及多重身份验证设置。 要详细了解 Azure Active Directory B2B，请参阅 [Azure AD B2B 协作是什么？](https://go.microsoft.com/fwlink/p/?linkid=853011)和[Azure Active Directory B2B 协作 FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)。
  
    
    

#### <a name="related-key-services-and-dependencies"></a>相关关键服务和相依性

Teams 依赖 SharePoint Online 和 OneDrive for Business 存储频道和聊天对话的文件和文档。 此外，Teams 还依赖 Office 365 组存储团队的成员身份和其他属性，例如，团队数据分类设置。
  
    
    
为了实现完整的 Teams 来宾访问体验，Office 365 管理员需要对以下设置选择**“开启”**：
  
    
    

- 在 SharePoint Online 中：**仅允许与已在目录中的外部用户共享**
    
    有关详细信息，请参阅[为你的 SharePoint Online 环境管理外部共享](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)。
    
  
- 在 Office 365 组中：**允许组所有者将组织外部的人员添加到组**
    
    有关详细信息，请参阅[控制对 Microsoft Teams 的来宾访问](#controlguest)。
    
  

#### <a name="turn-on-or-off-guest-access-for-microsoft-teams"></a>为 Microsoft Teams 开启或关闭来宾访问
<a name="bkmk_TurnonOrTurnOff"> </a>


1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。
    
  
2. 在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。
    
     ![登录 Office 365，访问 Office 365 管理中心，转到“设置”，然后选择“服务&amp;和外接程序”](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. 选择**“Microsoft Teams”**。
    
     ![此屏幕截图显示了在 Office 365 管理中心中选择的 Microsoft Teams 外接程序对应的选项。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. 在**“选择要配置的用户/许可证类型”**中，选择**“来宾”**。
    
  
![Microsoft Teams 外接程序的屏幕截图显示选择了“来宾”许可证且 Microsoft Teams 选项设置为“开启”。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
  
  
5. 单击或点击**“对此类型的所有用户开启或关闭 Microsoft Teams”**旁边的切换将其设置为**“开启”**为贵组织开启 Teams 和来宾访问，然后选择**“保存”**。 
    
  
> [!NOTE]
> 最长可能需要一个小时，设置将会生效。 
  
    
## <a name="control-adding-guest-users-to-microsoft-teams-and-office-365-groups"></a>控制向 Microsoft Teams 和 Office 365 组添加来宾用户
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。
    
  
2. 在导航菜单中，依次选择**“设置”**和**“服务&amp;和外接程序”**。
    
  
3. 选择**“Office 365 组”**。
    
     ![Office 365 组](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. 在“Office 365 组”页面上，将切换设置为**“开启”**或**“关闭”**，具体取决于你是否要允许贵组织外部的团队和组所有者访问 Office 365 组。 单击或点击**“允许组所有者将组织外部的人员添加到组”**旁边的切换将其设置为**“开启”**。
    
    
  
    
    
![此屏幕截图显示了“Office 365 组”面板，用于允许组织外部的组成员访问组内容和允许组所有者将组织外部的人员添加到组的选项已开启。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
  
  
  
<a name="controlguest"> </a>
## <a name="turn-on-or-off-the-sharing-option-for-office-365"></a>为 Office 365 开启或关闭“共享”选项。


“共享”选项用于允许将来宾添加到贵组织。 默认情况下，启用“共享”选项。 有关如何关闭“共享”选项的信息，请参阅[开启或关闭“共享”选项](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)。
  
    
    

> [!IMPORTANT]
> 如果你关闭“共享”选项，则来宾访问不可用。 
  

## <a name="use-powershell-to-control-guest-access"></a>使用 PowerShell 控制来宾访问
<a name="bkmk_UsePowerShell"> </a>

除了使用 Office 365 管理中心和 Azure Active Directory 门户外，你还可以使用 Windows PowerShell 控制来宾访问。 使用 PowerShell 可以执行以下操作：
  
    
    

- 允许或阻止来宾访问所有团队和 Office 365 组
    
  
- 允许将来宾添加到所有团队和 Office 365 组
    
  
- 在特定团队或 Office 365 组中允许或阻止来宾用户
    
  
有关更多详细信息，请参阅[使用 PowerShell 控制来宾访问](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)。
  
    
    
你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。 例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。 你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。 有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。
  
    
    
<a name="manageguest"> </a>
### <a name="view-guest-users"></a>查看来宾用户



1. 在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 上使用你的 Office 365 全局管理员帐户登录。
    
  
2. 转到**“用户”** > **“来宾用户”**。
    
    
  
    
    
![此屏幕截图显示了在 Office 365 管理中心的“用户”部分中选择了“来宾用户”选项。](media/95b83ff5-72ef-4668-b541-4e25b767620a.png)
  
    

## <a name="invite-guest-users"></a>邀请来宾用户
<a name="bkmk_UsePowerShell"> </a>

团队所有者或 Office 365 管理员可以单个[邀请来宾加入团队](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)。 但是，管理员无法使用 Office 365 管理中心或 Azure Active Directory 门户一次邀请多个来宾。 要集中邀请来宾，请考虑使用 Azure Active Directory B2B 协作预览版。 有关详细信息，请参阅[关于 Azure AD B2B 协作预览](https://go.microsoft.com/fwlink/p/?linkid=853011)。
  
    
    

## <a name="edit-guest-user-information"></a>编辑来宾用户信息
<a name="bkmk_UsePowerShell"> </a>

当前，无法在 Office 365 管理中心或 Exchange 管理中心中编辑来宾信息。 要编辑来宾帐户（例如，显示名称或个人资料照片），请访问 Azure Active Directory 门户。 有关详细信息，请参阅[了解 Office 365 标识和 Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)。
  
    
    
## <a name="frequently-asked-questions-for-admins"></a>管理员的常见问题
<a name="bkmk_UsePowerShell"> </a>

下面是 Office 365 管理员面临的有关在 Microsoft Teams 中邀请来宾加入团队的常见问题。
  
    
    

#### <a name="what-is-a-guest"></a>来宾是什么？


  
    
    
来宾不是贵组织的员工、学生和成员。 他们在贵组织没有学校或工作帐户。
  
    
    

  
    
    

#### <a name="who-can-be-added-as-a-guest-user"></a>哪些人可以添加为来宾用户？

仅拥有与 Azure Active Directory 或 Office 365 工作或学校帐户对应的电子邮件地址的用户可以添加为来宾用户。
  
    
    

#### <a name="can-users-add-people-within-my-organization-who-are-not-part-of-the-team-as-a-guest"></a>用户是否可以将我的组织中不属于团队的人员添加为来宾？

仅贵组织外部的人员（例如，合作伙伴或顾问）可以添加为来宾。 用户可以将贵组织中的人员作为常规团队成员或订阅者邀请加入。
  
    
    

#### <a name="why-does-a-user-get-the-message-contact-your-administrator-when-they-try-to-add-a-guest-to-their-team"></a>为什么用户尝试将来宾添加到其团队时收到消息“请与管理员联系。”？

作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。 用户看到该消息时，可能是未启用来宾功能。
  
    
    

#### <a name="how-can-a-global-admin-add-a-new-guest-user-to-the-organization"></a>全局管理员如何将新来宾用户添加到组织？

作为全局管理员，你可以采用多种方式将新来宾用户添加到组织：
  
    
    

- 身为团队所有者的全局管理员和团队所有者可以通过 Microsoft Teams 桌面客户端或 Web 客户端[将来宾添加到团队](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)。
    
  
- 通过 Azure Active Directory B2B 协作将来宾添加到贵组织。 利用 Azure Active Directory B2B 协作，全局管理员可以通过将不超过 2,000 行的逗号分隔值 (CSV) 文件上载到 B2B 协作门户来邀请和授权一组外部用户。 有关更多详细信息，请参阅 [Azure Active Directory B2B 协作](https://go.microsoft.com/fwlink/p/?LinkId=826383)。
    
  

#### <a name="is-there-a-way-to-block-individual-guest-users"></a>是否有办法阻止单个来宾用户？

没有，无法阻止单个来宾用户。
  
    
    

#### <a name="can-global-admins-block-guests-in-teams-and-still-allow-guests-to-access-sharepoint-sites"></a>全局管理员是否可以在团队中阻止来宾，但仍允许来宾访问 SharePoint 网站？

是，全局管理员可以使用 Azure Active Directory Powershell cmdlet 在“公司”对象上禁用 _AllowGuestAccessToGroups_ 参数，前提是为 SharePoint 网站开启了外部共享。
  
    
    

#### <a name="what-other-controls-are-available-to-it-admins-to-manage-guests-in-microsoft-teams"></a>IT 管理员可以使用哪些其他控制功能在 Microsoft Teams 中管理来宾？

IT 管理员可以在租户级别添加来宾、设置和管理来宾用户策略和权限、确定哪些用户可以邀请来宾以及获取有关来宾用户活动的报告。 这些控制功能通过 Office 365 管理中心提供。 来宾用户内容和活动与 Office 365 的其他部分一样受到相同的合规性和审核保护。
  
    
    

#### <a name="can-users-share-a-team-file-with-an-external-user-who-isnt-a-member-of-the-team"></a>用户是否可以与不是团队成员的外部用户共享团队文件？

不可以。 用户只能与受邀加入团队的来宾共享 Microsoft Teams 文件。
  
    
    

#### <a name="is-an-additional-office-365-license-required-for-guest-access"></a>来宾访问是否需要额外的 Office 365 许可证？

不需要额外的许可证。 所有 Office 365 商业高级版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。
  
    
    

#### <a name="do-office-365-and-azure-active-directory-service-limits-apply-to-guests"></a>Office 365 和 Azure Active Directory 服务限制是否适用于来宾？

是，来宾受 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 服务限制约束。
  
    
    

  
    
    

#### <a name="how-long-does-it-take-until-the-guest-user-settings-take-effect-in-the-office-365-organization"></a>来宾用户设置在 Office 365 组织中生效需要多长时间？

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。
  
    
    

#### <a name="can-a-global-admin-manage-sharepoint-online-external-user-settings-for-the-teams-connected-team-site"></a>全局管理员是否可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置？

是，你可以管理 Teams 连接的团队网站的 SharePoint Online 外部用户设置。 有关更多详细信息，请参阅[管理 SharePoint 团队网站设置](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。
  
    
    

  
    
    

#### <a name="how-does-conditional-access-work-with-guest-access"></a>条件访问是否适用于来宾访问？

利用 Azure Active Directory B2B 协作，组织可以对 B2B 用户强制应用条件访问和多重身份验证 (MFA) 策略。 可以在租户、应用或单个用户级别强制应用这些策略，方式与对组织的全职员工和成员启用它们一样。 此类策略在资源组织上强制应用。 有关详细信息，请参阅 [B2B 协作用户的条件访问](https://go.microsoft.com/fwlink/?linkid=857454)。
  
    
    

#### <a name="if-i-have-a-team-with-an-office-365-group-and-i-add-a-guest-to-the-group-does-that-user-automatically-get-access-to-the-team"></a>如果我有一个使用 Office 365 组的团队，我向该组添加来宾后，该用户是否自动获取访问团队的权限？

是，来宾将获取访问团队的权限。 通过 Office 365 组添加来宾不会为该来宾生成邀请电子邮件，因此该团队中的人员应通知该来宾。
  
    
    

#### <a name="what-event-appears-in-the-audit-log-to-indicate-a-guest-has-been-sent-an-invitation"></a>审核日志中的什么事件指示已向来宾发送邀请？

你可以在 Azure Active Directory 或 Office 365 安全性&amp;和合规性中心中跟踪来宾添加情况。 在 Microsoft Teams 中添加来宾会进行审核并记录为 Azure AD 组管理活动“已向组添加成员”。 有关更多详细信息，请参阅[审核和报告 B2B 协作用户](https://go.microsoft.com/fwlink/p/?linkid=858884)和[在 Office 365 安全性&amp;和合规性中心中搜索审核日志](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。
  
    
    

#### <a name="if-i-have-existing-guest-users-that-were-added-via-azure-ad-b2b-office-365-groups-or-sharepoint-online-do-i-have-to-do-anything-else-with-them-for-microsoft-teams"></a>如果我有通过 Azure AD B2B、Office 365 组或 SharePoint Online 添加的现有来宾用户，是否需要为了 Microsoft Teams 对其进行任何其他操作？

你已通过 Azure Active Directory B2B、Office 365 组或 SharePoint Online 添加的来宾用户已准备就绪。 Office 365 管理员或团队所有者可以向其各自团队添加那些来宾。
  
    
    

#### <a name="if-external-accounts-are-available-does-that-mean-external-sharing-is-enabled"></a>如果外部帐户可用，是否表示启用了外部共享？

管理员可以在 Azure Active Directory 中创建来宾帐户，与外部共享设置无关。 如果外部共享处于关闭状态，则仅管理员可以创建来宾帐户。
  
    
    

  
    
    

## <a name="more-information"></a>更多信息

 [Microsoft Teams 的管理员设置](https://support.office.com/en-us/article/Administrator-settings-for-Microsoft-Teams-3966a3f5-7e0f-4ea9-a402-41888f455ba2)
  
    
    
 [有关 Microsoft Teams 的常见问题 - 管理帮助](https://support.office.com/en-us/article/Frequently-asked-questions-about-Microsoft-Teams-–-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)
  
    
    
 [向团队添加来宾](https://support.office.com/en-us/article/Adding-guests-to-teams-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)
  
    
    
视频：[深入了解来宾访问](https://go.microsoft.com/fwlink/p/?linkid=858791)
  
    
    

