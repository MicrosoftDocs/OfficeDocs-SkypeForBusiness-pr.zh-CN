---
title: 在 Microsoft Teams 中管理审批应用
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中管理组织的审批应用。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbedcfb7215adbde9ee8b8dd2afb3e88422e28c2
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131181"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>在 Microsoft Teams 中管理审批应用

“审批”应用可作为个人应用提供给所有 Microsoft Teams 用户。
“审批”应用提供了一种在 Teams 中将审核、合规性、责任和工作流引入结构化审批和非结构化审批的简单方法。

 ![显示审批应用。](media/approvals-selection.png)

用户可以固定“审批”应用以将其保存到菜单栏。

 ![显示具有固定选项的审批应用。](media/approvalApp-pin.png)

从“审批”应用创建的第一个审批将触发在默认 Microsoft Dataverse 环境中预配审批解决方案。 从“审批”应用创建的审批将存储在默认的 Microsoft Dataverse 环境中。

本文介绍了“审批”应用要求和角色。

> [!NOTE]
> 此功能尚未发布到政府社区云高 (GCCH) 和国防部 (DOD) 用户。

## <a name="required-permissions-and-licenses"></a>所需权限和许可证

若要部署“审批”应用，需要对以下项拥有权限：

- 创建 Microsoft Dataverse 数据库的权限。

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) 上的帐户

- 目标环境中的管理员角色。

- [Power Automate](/power-automate/get-started-approvals)、Office 365或 Dynamics 365 许可证。

- 用户需要Microsoft Forms许可证才能设置新的审批模板。

若要使用“审批”应用，需要 Power Automate 许可证，并且你的帐户会在首次审批分配时自动添加到目标环境中的“审批用户”角色。

## <a name="storage-with-microsoft-dataverse"></a>使用 Microsoft Dataverse 存储

通用数据模型 (CDM) 是 Microsoft Dataverse 中的业务和分析应用程序使用的共享数据语言。 它由 Microsoft 和我们的合作伙伴发布的一组标准化、可扩展的数据架构组成，这些架构可实现跨应用程序和业务流程的数据及其含义的一致性。 了解有关 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals) 的详细信息。

了解有关[审批工作流](/power-automate/modern-approvals)的详细信息。

从模板创建的审批仍将数据存储在 Microsoft Dataverse 中，例如标题、详细信息、模板 ID 等。 在审批请求上提交的响应存储在窗体中。 详细了解[用于Microsoft Forms的数据存储](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。

>[!Note]
>如果在 Microsoft Forms 网站上删除表单模板，则会中断审批模板，并且用户无法启动请求。 用户在尝试打开在 Microsoft Forms 上删除的审批模板时收到错误“CDB TableNotFound”。

组织范围的模板共享租户的相同生存期，团队范围的模板共享团队的同一生存期。 因此，永久删除团队会删除相关模板。

## <a name="approvals-teams-app-permissions"></a>“审批”Teams 应用权限

通过“审批”Teams 应用，你能够访问以下功能：

- 接收你向其提供的消息和数据。

- 向你发送消息和通知。

- 呈现个人应用和对话框，但不显示 Teams 提供的标题。

- 访问你的个人资料信息，如姓名、电子邮件地址、公司名称和首选语言。

- 在频道中接收团队成员向其提供的消息和数据。

- 在频道中发送消息和通知。

- 访问团队的信息：
  - 团队名称
  - 频道列表
  - 名单（团队成员的姓名和电子邮件地址）。

- 使用团队的信息联系他们。

审批模板权限

- 所有团队所有者都可以为其拥有的团队创建审批模板。

- 管理员首次为其整个组织创建模板时，会自动为租户的所有管理员（包括全局管理员和 Teams 服务管理员）创建新的 Azure Active Directory (AAD) 组。 这些管理员添加为组的所有者，以便他们可以共同管理组织模板。 创建团队后，组织新加入的管理员需要手动添加为组所有者，以便他们具有相同的权限来管理组织范围的模板。

> [!Note]
> 如果管理员删除了该组，则你有一个月的时间在 Azure Active Directory (AAD) 门户中还原该组，以还原所有相关数据。 一个月后，或者如果管理员在回收站中删除此组，你将丢失所有相关数据。

## <a name="disable-the-approvals-app"></a>禁用“审批”应用

默认情况下，“审批”应用可用。 可在 Teams 管理中心中禁用该应用。

  1. 登录到 Teams 管理中心。

  2. 转到 “**Teams 应用**” > “**管理应用**”。

  3. 搜索“审批”应用。

     ![显示管理员中心导航，其中突出显示了 Teams 应用>“管理应用”。](media/manage-approval-apps.png)

  4. 选择“ **审批**”。

  5. 选择切换开关以为你的组织禁用该应用。

     :::image type="content" alt-text="显示“审批”应用的详细信息。" source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>将审批固定到 Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>使用定制的一线应用体验将审批和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定的应用包括审批、对讲机、任务和排班。 默认情况下，此功能处于打开状态，为一线员工提供适合其需求的开箱即用体验。

应用固定到应用栏（Teams 桌面客户端一侧和 Teams 移动客户端底部的栏），用户可以快速轻松地访问应用栏。

若要了解详细信息，包括体验如何与设置的应用策略配合使用，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>使用应用设置策略将审批固定到 Teams

应用设置策略允许自定义 Teams，以固定用户中最重要的应用。

若要为用户固定“审批”应用，可以编辑全局 (组织范围的默认) 策略，或在应用设置策略中创建和分配自定义策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

## <a name="retention-policy"></a>保留策略

从“审批”应用创建的审批存储在默认的 Microsoft Dataverse 环境中，该环境目前不支持备份。 详细了解如何[备份和还原环境 - Power Platform\| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

在团队所有者从 Microsoft Forms Web 应用中的 **已删除表单** 选项卡中清理数据之前，不会删除存储在窗体中的数据。

## <a name="conditional-access-policies"></a>条件访问策略

目前，Teams 中的“审批”应用不支持为 Microsoft Teams 设置的条件访问策略。

## <a name="data-limitations"></a>数据限制

每个团队最多可以包含 400 个审批模板，每个模板可以根据Microsoft Forms中的当前功能收集最多 50，000 个请求。

## <a name="auditing"></a>审核

“审批”应用将在 Microsoft 365 安全与合规中心中记录审核事件。 你可查看审核日志。

1. 转到 Microsoft 365 合规中心网站。

2. 选择“**审核**”部分。

3. 在 **Microsoft Teams 审批活动** 下搜索活动。

可搜索以下活动：

- 新建审批请求

- 查看审批请求详细信息

- 已批准审批请求

- 已拒绝审批请求

- 已取消审批请求

- 已共享审批请求

- 已将文件附加到审批请求

- 已重新分配审批请求

- 已向审批请求添加了电子签名

- 已查看电子签名请求详细信息

- 审阅的电子签名请求

- 已取消电子签名请求

- 创建新模板

- 编辑现有模板

- 启用/禁用模板

- 查看的模板

若要访问 Power Automate 中的更多审核审批，请在默认环境中为主要审批实体“审批”、“审批请求”和“审批响应”启用和配置审核。 创建、更新和删除操作是审批记录的可审核事件。 详细了解[安全性和合规性的审核数据和用户活动 - Power Platform\| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。

可在 [Microsoft 365 安全与合规中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)中进一步自定义。

1. 若要使用预配置的报告，请登录到 Microsoft 365 安全与合规中心。

2. 选择“**搜索和调查**”。

3. 搜索审核日志，然后选择“**Dynamics 365 活动**”选项卡。

详细了解 [Microsoft Dataverse 和模型驱动的应用活动日志记录 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>安全性

在 Teams“审批”应用中，用户能够创建新的审批并查看其已发送和接收的审批。 用户无法访问其他人创建的审批，除非他们是请求的回应者或查看者。

>[!Note]
> 如果用户是创建审批的聊天或频道的一部分，则用户将获得请求的查看者角色。 如果在创建审批时他们未获得该角色，则他们无法对请求执行操作。

## <a name="approvals-e-signature-integration"></a>审批电子签名集成

若要使用审批应用电子签名功能，需要要使用的特定电子签名提供程序的许可证。 若要获取组织的许可证，需要转到提供商的网站。

### <a name="enable-or-disable-e-signature-providers"></a>启用或禁用电子签名提供程序

可以使用 Teams 管理中心来控制“审批”应用中的用户可以使用哪些第三方电子签名提供程序。 默认情况下，在“审批”应用中启用电子签名提供程序。 禁用电子签名提供程序时，用户在创建审批时将无法访问该提供程序。 用户也无法查看使用该提供程序创建的电子签名请求。

1. 在 Teams 管理中心的左窗格中，转到 **“Teams 应用** > **”“管理应用**”。
2. 搜索“审批”应用，然后选择它。
3. 转到 **“设置”** 选项卡，然后执行以下一项或多项操作：

    - 若要启用或禁用 Adobe Sign，请将开关切换为 **“打开** ”或 **“关闭**”。
    - 若要启用或禁用 DocuSign，请将开关切换为 **“打开** ”或“ **关闭**”。
4. 选择“ **提交**”。

从“审批”应用创建的电子签名审批存储在所选提供商的云环境中。 若要导出有关电子签名的数据，需要转到提供商的网站。 有关电子签名协议的存储、导出和保留的详细信息，请参阅提供商的文档。
