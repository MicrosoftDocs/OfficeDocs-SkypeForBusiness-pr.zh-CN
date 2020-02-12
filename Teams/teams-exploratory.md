---
title: 管理 Microsoft Teams Exploratory 体验
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Office 365 用户可以启动 Exploratory Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb0998579c29cd7405319600c436468bac2ec4e8
ms.sourcegitcommit: 73376693670d12f3d9038d4ed604e6685ee21984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41917017"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 许可证
=======================================================

借助 Microsoft Teams Exploratory 体验，组织中拥有 Azure Active Directory (AAD) 且未获得 Teams 许可的用户可以启用 Teams 的探索体验。 管理员可以为组织中的用户打开或关闭此功能。 以前的 [Microsoft 商业云试用版](iw-trial-teams.md)现在称为 Teams Exploratory 体验。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory 体验中包含哪些服务？

Teams Exploratory 体验中包含的服务计划如下：
 - Exchange Online（计划 1)
 - Flow for Office 365
 - MyAnalytics 提供的见解
 - Microsoft Forms（计划 E1）
 - Microsoft Planner
 - Microsoft 搜索
 - Microsoft StaffHub
 - Microsoft Stream for O365 E1 SKU
 - Microsoft Teams
 - Office 365 移动设备管理
 - 适用于 Office 365 的 Office 移动应用 
 - Office Online
 - PowerApps for Office 365
 - SharePoint Online（计划 1）
 - Sway
 - 待办事项（计划 1）
 - Whiteboard（计划 1）
 - Yammer 企业版


## <a name="whos-eligible"></a>要获取 Teams Exploratory 体验，需要满足什么条件？

必须允许用户注册应用和试用版（在 Microsoft 365 管理中心中）。 有关详细信息，请参阅本文后面部分的[管理 Teams Exploratory 体验](#manage-the-teams-exploratory-experience)。 

没有包含 Teams 的 Office 365 许可证的用户可以启用 Teams Exploratory 体验。 例如，如果用户拥有 Office 365 商业版（不包括 Teams），则他们符合获取 Teams Exploratory 体验的条件。

## <a name="who-isnt-eligible"></a>不符合条件的情况

如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>如何注册 Teams Exploratory 体验？

符合条件的用户可通过登录到 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 注册 Teams Exploratory 体验。 将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams 探索性体验

Teams Exploratory 体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。

Teams Exploratory 体验附带 Exchange Online 许可证，但它不会在管理员进行分配前分配给用户。 如果用户没有 Exchange 许可证并且管理员尚未分配 Exchange Online 许可证，则用户将无法在 Teams 中计划会议，并且可能无法使用其他 Teams 功能。

管理员可以通过使用**试用版应用和服务**开关，禁用最终用户在其组织内运行 Teams Exploratory 体验的功能。


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用和服务

可以关闭用户安装试用版应用和服务的功能，这将阻止用户运行 Teams Exploratory 体验。

1. 从 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home)，转到**设置** > **设置**，选择**服务**，然后选择**用户自有应用和服务**。

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. 清除**允许用户安装试用版应用和服务**复选框。

    ![管理中心中“用户自有应用和服务”页面的屏幕截图](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果你的组织不符合获取 Teams Exploratory 的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>为拥有包含 Teams 的许可证的用户管理可用性

分配了包含 Teams 的许可证的用户不符合获取 Teams Exploratory 的条件。 启用 Teams 服务计划时，用户可登录并使用 Teams。 如果禁用服务计划，则用户无法登录，并且 Teams Exploratory 体验不可用。

关闭对 Teams 的访问：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁的框。

3. 在右侧的“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将开关切换为“**关闭**”。

    ![管理中心中的“产品许可证”页面的屏幕截图。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>为已在使用 Teams Exploratory 体验的用户管理团队可用性

如果用户运行 Teams Exploratory 体验，则可以通过删除许可证或服务计划将其关闭。

若要关闭 Teams Exploratory 体验许可证，请执行以下操作：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁的框。

3. 在右侧的“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将此 Exploratory 许可证的开关切换为“**关**”。
   
    >[!Note]
    >组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>为拥有 Teams Exploratory 许可证的用户管理 Teams

你可以管理拥有 Teams Exploratory 许可证的用户，就像管理具有常规付费许可证的用户一样。 有关详细信息，请参阅[为你的组织管理 Teams 设置](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>从 Teams Exploratory 许可证升级用户

要从 Teams Exploratory 许可证升级用户，请执行以下操作：

1. 购买包含 Teams 的订阅。

2. 删除用户的 Teams Exploratory 订阅。

3. 分配新购买的许可证。

有关详细信息，请参阅[适用于 Microsoft Teams 的 Office 365 许可](Office-365-licensing.md)。

> [!NOTE]
> 如果 Teams Exploratory 许可证到期，而用户未立即升级到包含 Teams 的订阅，则不删除该用户数据。 该用户仍保留在 Azure Active Directory 中，且 Teams 中的所有数据都将保留。 一旦向该用户分配新的许可证来重新启用 Teams 功能，则所有内容仍将存在。 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>这对旧版 Microsoft Teams 商业云试用版许可证有何影响？

从 2020 年 1 月中旬起，符合条件的用户可开始使用最新的 Microsoft Teams Exploratory 体验。 所有旧版 Teams 商业云试用版许可证将在试用版到期前自动转换为新的服务。

### <a name="remove-a-teams-exploratory-license"></a>删除 Teams Exploratory 许可证

- 如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果要通过管理门户删除此许可证，请参阅：[在 Office 365 商业版中删除用户许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)
