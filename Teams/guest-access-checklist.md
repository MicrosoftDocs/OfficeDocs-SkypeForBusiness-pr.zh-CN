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
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833252"
---
<a name="microsoft-teams-guest-access-checklist"></a>Microsoft Teams 来宾访问清单
==========================================

在 Microsoft Teams 中使用此清单来帮助您启用和配置来宾访问。 你需要成为全局管理员或 Teams 管理员才能进行这些更改。

> [!IMPORTANT]
> 可能需要等待长达 24 小时才能使更改生效。 

观看此短视频（5 分 31 秒），了解如何通过 Microsoft 365（包括 Teams）启用来宾访问。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>步骤 1：在 Teams 组织范围内级别启用来宾访问

要启用来宾访问，请转至 **Microsoft Teams 管理中心**。 

1. 在 Teams 管理中心中，选择“**组织范围的设置**” > “**来宾访问**”。
2. 将“**在 Microsoft Teams 中允许来宾访问**”开关设置为“**打开**”。

    ![屏幕截图显示 Teams 设置开关示例](media/guest-access-checklist-set-up-guests-image1.png)

3. 在同一页面上，为来宾打开或关闭“**呼叫**”、“**会议**”和“**消息传递**”设置。
4. 单击“**保存**”。

> [!TIP]
> 如果使用 Azure Active Directory、SharePoint Online 和 Office 365 组中的默认设置，则可能已完成来宾访问配置。 在此情况下，可以跳过其余步骤。 如果不确定，或者如果使用 AAD、SharePoint Online 或 Office 365 组的自定义设置，请继续完成此清单中的其余步骤。

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>步骤 2：配置 Azure AD 企业对企业设置

这些是支持 Teams 中的来宾访问的 Azure AD 设置。 这些设置配置完成之后，可以在 Teams 中“[添加](add-guests.md)”和“[管理来宾](manage-guests.md)”。

1. 以租户管理员身份登录 [Azure 门户](https://portal.azure.com)。
2. 选择“**Azure Active Directory**” > “**用户** > ”“**用户设置**”。
3. 在“**外部用户**”下，选择“**管理外部协作设置**”。
   > [!NOTE]
   > “**外部协作设置**”也可从“**组织关系**”页面获取。 在 Azure Active Directory 中的“**管理**”下，转至“**组织关系**” > “**设置**”。
4. 在“**外部协作设置**”页面上，选择想要启用的策略。

    - **来宾用户权限受限**：此策略决定目录中来宾的权限。 选择“**是**”阻止来宾执行特定目录任务，如枚举用户、组或其他目录资源。 选择“**否**”为来宾授予与目录中的常规用户相同的目录数据访问权限。
     - **来宾邀请者角色中的管理员和用户可进行邀请**：要允许“来宾邀请者”角色中的管理员和用户邀请来宾，请将此策略设置为“**是**”。
     - **成员可邀请**：要允许目录的非管理员成员邀请来宾，请将此策略设置为**是**（建议设置）。 如果你希望仅管理员能够添加来宾，可以将此策略设置为**否**。 请记住，设置为**否**将会限制非管理员团队所有者的来宾体验；他们只能向管理员已在 AAD 中添加的团队添加来宾。
     - **来宾可进行邀请**：要允许来宾邀请其他来宾，请将此策略设置为“**是**”。
         > [!IMPORTANT]
         > 目前，Teams 不支持来宾邀请者角色，因此即使你将“**来宾可邀请**”设置为“**是**”，来宾也不能邀请 Teams 中的其他来宾。
     - **为来宾启用电子邮件一次性密码(预览)**：有关一次性密码功能的更多信息，请参阅[电子邮件一次性密码身份验证(预览)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。
     - **协作限制**：有关允许或阻止对特定域的邀请的更多信息，请参阅[允许或阻止对特定组织中的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。
        > [!NOTE]
        > 对于协作限制，请参阅[启用 B2B 外部协作并管理可邀请来宾的人员](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。
      
    要详细了解如何控制可邀请来宾的人员，请参阅[委托 Azure Active Directory B2B 协作邀请](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

## <a name="step-3-configure-office-365-groups"></a>步骤 3：配置 Office 365 组

1. 在 Microsoft 365 管理中心中，转至“**设置**” > “**设置**”，单击“**服务**”，然后选择“**Office 365 组**”。

     ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-services-settings.png)
2. 确保已选中“**允许组织外部的组成员访问组内容**”复选框。 如果未选中此设置，则来宾无法访问任何组内容。

    ![屏幕截图显示 Office 365 组设置](media/guest-access-checklist-office365.png)
3. 确保已选中“**允许组拥有者将组织外部的人员添加到组**”复选框。 如果未选中此设置，则团队拥有者无法添加新来宾。 作为最低条件，此设置必须启用才能支持来宾访问。

有关配置这些设置的详细说明，请参阅[管理 Office 365 组中的来宾访问](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)和[控制 Office 365 组中的来宾访问](Teams-dependencies.md#control-guest-access-in-office-365-groups)。

## <a name="step-4-configure-sharing-in-office-365"></a>步骤 4：在 Office 365 中配置共享 

确保用户可以添加来宾。 操作步骤如下：

1. 在 Microsoft 365 管理中心中，转至“**设置**” > “**设置**”，单击“**安全和隐私**”，然后选择“**共享**”。

     ![屏幕截图显示服务设置示例](media/guest-access-checklist-security-privacy-settings.png)
 
2. 选中“**允许用户向此组织添加新来宾**”复选框，然后单击“**保存更改**”。

     ![屏幕截图显示共享设置开关示例](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > 此设置的作用相当于 Azure AD 中的“**用户设置**” > “**外部用户**”中的“**成员可进行邀请**”设置。  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>步骤 5：在 SharePoint 中验证共享设置

1. 登录到 Microsoft 365 管理中心。
2. 在“**管理中心**”下，选择“**SharePoint**”。
3. 在新的 SharePoint 管理中心的“**网站**”下，选择“**活动网站**”。

    ![SharePoint 管理中心中的活动网站](media/guest-access-checklist-SPOSettings0.png)

3. 选择“网站”，然后单击“**共享**”。
4. 确保将选项设置为“**任何人**”或“**新来宾和现有来宾**”。

     ![屏幕截图显示 SharePoint Online 设置开关示例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>步骤 6：设置来宾用户权限

在 Teams 应用程序中，在单个团队级别配置来宾权限，以控制来宾是否可以创建、更新或删除频道。 Teams 管理员和团队拥有者可以配置这些设置。

![屏幕截图显示团队/频道设置开关示例](media/guest-access-checklist-TeamsSettings2.png)

要了解与来宾访问相关的更多信息，请参阅 [Teams 中的来宾访问](guest-access.md)和[启用或禁用 Microsoft Teams 的来宾访问](set-up-guests.md)。

## <a name="troubleshooting"></a>故障排除

如果在设置来宾访问或在 Teams 中添加来宾时遇到问题，请使用以下资源来帮助你解决问题：

[对 Microsoft Teams 中的来宾访问问题进行故障排除](troubleshoot-guest-access.md)

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
