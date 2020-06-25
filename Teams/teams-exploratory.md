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
description: 未获得 Microsoft Teams 许可的 Microsoft 365 或 Office 365 用户可以启动 Exploratory Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99017e63ae784c7c4271454829198c7c06ecfe8e
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868459"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 许可证
=======================================================

借助 Microsoft Teams Exploratory 体验，组织中拥有 Azure Active Directory (AAD) 且未获得 Teams 许可的用户可以启用 Teams 的探索体验。 管理员可以为组织中的用户打开或关闭此功能。 以前的 [Microsoft 商业云试用版](iw-trial-teams.md)现在替换为 Teams Exploratory 体验。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory 体验中包含哪些服务？

管理员将在 Teams Exploratory 体验中看到的服务计划有：
 - Exchange Online（计划 1)
 - 适用于 Microsoft 365 或 Office 365 的流
 - MyAnalytics 提供的见解
 - Microsoft Forms（计划 E1）
 - Microsoft Planner
 - Microsoft 搜索
 - Microsoft StaffHub
 - 适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream
 - Microsoft Teams
 - 适用于 Microsoft 365 或 Office 365 的移动设备管理
 - 适用于 Office 365 的 Office 移动应用 
 - Office Online
 - 适用于 Microsoft 365 或 Office 365 的 PowerApps
 - SharePoint Online（计划 1）
 - Sway
 - 待办事项（计划 1）
 - Whiteboard（计划 1）
 - Yammer 企业版


## <a name="whos-eligible"></a>谁有资格使用？

只要用户拥有托管 AAD 域电子邮件地址，且当前没有/尚未分配有 Teams 许可证，则有资格运行此体验。 例如，如果用户拥有 Microsoft 365 商业应用版（不包括 Teams），则他们符合获取 Teams Exploratory 体验的条件。

必须允许用户注册应用和试用版（在 Microsoft 365 管理中心中）。 有关详细信息，请参阅本文后面部分的[管理 Teams Exploratory 体验](#manage-the-teams-exploratory-experience)。 


## <a name="who-isnt-eligible"></a>谁没有资格使用

如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>如何注册 Teams Exploratory 体验？

符合条件的用户可通过登录到 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 注册 Teams Exploratory 体验。 将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams 探索性体验

Teams Exploratory 体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。

Teams Exploratory 体验附带 Exchange Online 许可证，但它不会在管理员进行分配前分配给用户。 如果用户没有 Exchange 许可证并且管理员尚未分配 Exchange Online 许可证，则用户将无法在 Teams 中计划会议，并且可能无法使用其他 Teams 功能。

管理员可以通过使用**试用版应用和服务**开关，禁用最终用户在其组织内运行 Teams Exploratory 体验的功能。


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用和服务

可以禁用用户安装试用版应用和服务的功能，这会阻止用户运行 Teams 探索体验。 必须具有管理员权限。 若要详细了解管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](teams-exploratory.md)。

1. 从 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home)，转到**设置** > **设置**，选择**服务**，然后选择**用户自有应用和服务**。

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. 清除**允许用户安装试用版应用和服务**复选框。

    ![管理中心中“用户自有应用和服务”页面的屏幕截图](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果你的组织不符合获取 Teams Exploratory 的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>为拥有包含 Teams 的许可证的用户管理可用性

分配了包含 Teams 的许可证的用户不符合获取 Teams Exploratory 的条件。 启用 Teams 服务计划时，用户可登录并使用 Teams。 如果禁用服务计划，则用户无法登录，并且 Teams Exploratory 体验不可用。 必须具有管理员权限。 

关闭对 Teams 的访问：

1. 在 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home)中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁的框。

3. 在右侧的“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将开关切换为“**关闭**”。

    ![管理中心中的“产品许可证”页面的屏幕截图。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>为已在使用 Teams Exploratory 体验的用户管理团队可用性

如果用户运行 Teams Exploratory 体验，则可以通过删除许可证或服务计划将其关闭。 必须具有管理员权限。 

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

要从 Teams Exploratory 许可证升级用户（必须拥有管理员权限），请执行以下操作：

1. 购买包含 Teams 的订阅。

2. 删除用户的 Teams Exploratory 订阅。

3. 分配新购买的许可证。

有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

> [!NOTE]
> 如果 Teams Exploratory 许可证到期，而用户未立即升级到包含 Teams 的订阅，则不删除该用户数据。 该用户仍保留在 Azure Active Directory 中，且 Teams 中的所有数据都将保留。 一旦向该用户分配新的许可证来重新启用 Teams 功能，则所有内容仍将存在。 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>这对旧版 Microsoft Teams 商业云试用版许可证有何影响？

从 2020 年 2 月起，符合条件的用户可开始使用最新的 Microsoft Teams Exploratory 体验。 所有旧版 Teams 商业云试用版许可证将在试用版到期前自动转换为新的服务。

当用户首次登录到其过期的 Teams 商业云试用版时，我们会自动向该用户分配 Teams Exploratory 体验许可证。 用户在登录前不会进行转换。

### <a name="remove-a-teams-exploratory-license"></a>删除 Teams Exploratory 许可证

- 如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果要通过管理门户删除此许可证，请参阅[从组织删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams Exploratory 体验持续多长时间？

在 2021 年 1 月或之后的下一个**协议周年日**或**续订**前，使用 Microsoft Teams 探索体验都是免费的。 届时，Microsoft Exploratory 体验许可证的最终用户需要迁移到包含 Teams 的付费许可证。 此后启动的任何 Microsoft 探索体验许可证在下一个**周年日**或**续订**周期前一直都是免费的。 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>如果最终用户刚好在我的周年纪念或续订日期前启动 Microsoft Teams Exploratory 体验，会发生什么情况？

在**协议周年日**或**续订**后的 90 天内启动的 Microsoft Teams 探索体验许可证无需迁移到付费许可证，直到下一个周年日或续订周期。 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>如果我的协议没有周年日或每年的续约日期（例如逐月协议），该怎么办？

对于无周年日或年度续订日期的协议，第一位最终用户后面的年份激活 Microsoft 团队探索体验许可证将被视为周年日或续订日期。 根据上述策略，必须在每年的此日期之前将拥有 Microsoft Teams 探索许可证的用户转换为付费许可证。

例如，如果第一位最终用户在 2020 年 6 月 19 日激活了 Microsoft Teams 探索，则他们和客户租户中的所有其他符合条件的用户必须在 2021 年 6月 19 日之前转换为 Teams 付费许可证。 

