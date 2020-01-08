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
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962530"
---
<a name="microsoft-teams-guest-access-checklist"></a>Microsoft Teams 来宾访问清单
==========================================

使用此清单可帮助你打开和配置 Microsoft 团队中的来宾访问。 您必须是全局管理员或团队管理员才能进行这些更改。

> [!IMPORTANT]
> 您可能需要等待24小时才能使更改生效。 

观看此简短视频（5:31 分钟），了解如何在整个 Microsoft 365 （包括团队）中打开来宾访问。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>步骤1：在团队的组织范围级别启用来宾访问

若要启用来宾访问，请转到**Microsoft 团队管理中心**。 

1. 在 "团队管理中心" 中，选择 "**组织范围设置** > "**来宾访问**。
2. 将 "**允许 Microsoft 团队中的来宾访问**" 切换到 **"开**"。

    ![屏幕截图显示团队设置切换的示例](media/guest-access-checklist-set-up-guests-image1.png)

3. 在此同一页面上，打开或关闭来宾的**呼叫**、**会议**和**消息**设置。
4. 单击“**保存**”。

> [!TIP]
> 如果你使用的是 Azure Active Directory、SharePoint Online 和 Office 365 组中的默认设置，则可能会完成来宾访问配置。 在这种情况下，您可以跳过其余步骤。 如果不确定，或者如果你使用的是 AAD、SharePoint Online 或 Office 365 组的自定义设置，请继续执行此清单中的其余步骤。


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>步骤2：配置 Azure AD 企业到企业版设置

1. 以租户管理员身份登录到[Azure 门户](https://portal.azure.com)。
2. 选择 " **Azure Active Directory** > **用户** > "**用户设置**。
3. 在 "**外部用户**" 下，选择 "**管理外部协作设置**"。
   > [!NOTE]
   > 此外，还可从 "**组织关系**" 页面获取**外部协作设置**。 在 Azure Active Directory 中的 "**管理**" 下，转到 "**组织关系** > "**设置**。
4. 在 "**外部协作设置**" 页面上，选择要启用的策略。

    - **来宾用户权限受到限制**：此策略确定你的目录中的来宾的权限。 选择 **"是"** 阻止来自某些目录任务的来宾，例如枚举用户、组或其他目录资源。 选择 "**否**"，为来宾提供与目录中普通用户相同的访问目录数据。
     - **来宾 inviter 角色中的管理员和用户可以邀请**：要允许管理员和 "来宾 inviter" 角色中的用户邀请来宾，请将此策略设置为 **"是"**。
     - **成员可以邀请**：若要允许你的目录的非管理员成员邀请来宾，请将此策略设置为 **"是"**。

         > [!NOTE]
         > 如果您设置的**成员可以邀请**"**否**"，然后在 Office 365 组和 Microsoft 团队中启用来宾访问，则管理员可以控制您的目录的来宾邀请。 来宾位于目录中后，可通过非管理员成员的团队所有者将其添加到团队。 有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。
         > [!IMPORTANT]
         > 要让来宾访问可在 Teams 中正常工作，必须将“**成员可邀请**”设置为“**是**”。   
     - **来宾可以邀请**：要允许来宾邀请其他来宾，请将此策略设置为 **"是"**。
         > [!IMPORTANT]
         > 目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。
     - **启用来宾电子邮件一次性密码（预览版）**：有关一次性密码功能的详细信息，请参阅[通过电子邮件发送一次性密码身份验证（预览版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。
     - **协作限制**：有关允许或阻止特定域的邀请的详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。
        > [!NOTE]
        > 有关协作限制，请参阅[启用 B2B 外部协作和管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。
      
 
    要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。


## <a name="step-3-configure-office-365-groups"></a>步骤3：配置 Office 365 组

1. 在 Microsoft 365 管理中心中，转到 "**设置** > **服务 & 加载项**"，然后选择 " **Office 365 组**"。

     ![屏幕截图显示 Office 365 组的切换](media/guest-access-checklist-office365.png)
2. 确保选中 "**允许组织访问组内容之外的成员进行分组**" 复选框。 如果未选择此设置，来宾将无法访问任何组内容。
3. 确保已选中 "**允许组所有者将组织外部人员添加到组**" 复选框。 如果未选择此设置，则团队所有者将无法添加新来宾。 此设置至少必须启用才能支持来宾访问。

有关配置这些设置的详细说明，请参阅[在 office 365 组中管理来宾访问](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。
 

## <a name="step-4-configure-sharing-in-office-365"></a>步骤4：在 Office 365 中配置共享 

请确保用户可以添加来宾。 操作方法如下：

1. 在 Microsoft 365 管理中心中，转到 "**设置** > **安全 & 隐私**"。

     ![屏幕截图显示服务设置的示例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. 在 "**共享**" 中，选择 "**编辑**"。

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. 设置 "**允许用户向此组织添加新来宾** **"，然后**单击 "**保存**"。

     ![屏幕截图显示共享设置切换的示例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > 此设置等效于**成员可**在 Azure AD 中的**用户设置** > **外部用户**中邀请的设置。  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>步骤5：验证 SharePoint 中的共享设置

1. 登录到 Microsoft 365 管理中心。
2. 在 "**管理中心**" 下，选择 " **SharePoint**"。
3. 在新的 SharePoint 管理中心的 "**网站**" 下，选择 "**活动网站**"。

    ![SharePoint 管理中心中的活动网站](media/guest-access-checklist-SPOSettings0.png)

3. 选择 "网站"，然后单击 "**共享**"。
4. 请确保已将该选项设置为 "**任何人**" 或 "**现有来宾**"。
 
     ![屏幕截图显示 SharePoint Online 设置切换的示例](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>步骤6：设置来宾用户权限

在 "团队" 应用程序中，在单个团队级别配置用于控制来宾是否可以创建、更新或删除频道的来宾权限。 团队管理员和团队所有者可以配置这些设置。

![屏幕截图显示团队/频道设置切换的示例](media/guest-access-checklist-TeamsSettings2.png)

若要了解有关来宾访问的详细信息，请参阅[团队中的来宾访问](guest-access.md)和[打开或关闭 Microsoft 团队的来宾访问](set-up-guests.md)。


## <a name="troubleshooting"></a>疑难解答

如果您在设置来宾访问或在团队中添加来宾时遇到问题，请使用以下资源帮助您：

[解决 Microsoft 团队中的来宾访问问题](troubleshoot-guest-access.md)

[团队疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



