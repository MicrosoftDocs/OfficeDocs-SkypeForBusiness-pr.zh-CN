---
title: Teams 中的“审批”应用程序可用性
author: guptaashish
ms.author: guptaashish
ms.reviewer: farhazk
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的“审批”应用程序可用性。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c2ec3432a503755ba6164f4a46f7b35f9696271
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442308"
---
# <a name="teams-approvals-app-availability"></a>Teams“审批”应用可用性

“审批”应用可作为个人应用提供给所有 Microsoft Teams 用户。
“审批”应用提供了一种在 Teams 中将审核、合规性、责任和工作流引入结构化审批和非结构化审批的简单方法。

 ![显示审批应用。](media/approvals-selection.png)

用户可以固定“审批”应用以将其保存到菜单栏。

 ![显示具有固定选项的审批应用。](media/approvalApp-pin.png)

从“审批”应用创建的第一个审批将触发在默认 Common Data Service (CDS) 环境中设置审批解决方案。 从“审批”应用创建的审批将存储在默认 CDS 环境中。

本文介绍了“审批”应用要求和角色。

> [!NOTE]
> 此功能尚未向 政府社区云 GCCH () 和国防部 (DOD) 发布。

## <a name="required-permissions-and-licenses"></a>所需权限和许可证

若要部署"审批"应用，需要以下项的权限：

- 创建 Microsoft CDS 数据库的权限。

- [flow.microsoft.com](https://flow.microsoft.com/) 上的帐户

- 目标环境中的管理员角色。

- 适用于 [Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的许可证。

- 用户需要 Microsoft Forms 许可证才能设置新的审批模板。

若要使用"审批"应用，需要一个许可证Power Automate，你的帐户将在第一次审批分配时自动添加到目标环境中"审批用户"角色。

## <a name="storage-with-cds"></a>通过 CDS 进行存储

Common Data Model (CDM) 是业务和分析应用程序在 CDS 中使用的共享数据语言。 它由 Microsoft 和我们的合作伙伴发布的一组标准化可扩展数据架构组成，可跨应用程序和业务流程实现数据的一致性及其含义。 了解有关 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals) 的详细信息。

了解有关[审批工作流](/power-automate/modern-approvals)的详细信息。

从模板创建的审批仍将数据存储在 CDS 中，例如其标题、详细信息、模板 ID 等。 在审批请求中提交的响应存储在 Forms 中。 详细了解 Microsoft  [Forms 的数据存储](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。

>[!Note]
>如果删除 Microsoft Forms 站点上的表单模板，将中断审批模板，用户将无法启动请求。 尝试打开 Microsoft Forms 上已删除的审批模板时，用户收到错误"CDB TableNotFound"。

组织范围的模板共享租户的相同生存期，团队范围的模板共享团队的相同生存期。 因此，永久删除团队会删除相关的模板。

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

- 所有团队所有者都可以为他们拥有的团队创建审批模板。

- 当管理员首次为整个组织创建模板时，它会自动为租户的所有管理员（包括全局管理员和 Teams 管理员）创建新的 Azure Active Directory (AAD) 组。 这些管理员将添加为组的所有者，以便他们可以共同管理组织模板。 创建团队后，组织中新增的管理员需要手动添加为组所有者，以便他们具有相同的权限来管理组织范围的模板。

> [!Note]
> 如果管理员删除了组，则你有一个月时间在门户Azure Active Directory (AAD) 还原所有相关的数据。 一个月后，或者如果管理员在回收站中删除此组，你将丢失所有相关的数据。

## <a name="disable-the-approvals-app"></a>禁用“审批”应用

默认情况下，“审批”应用可用。 可在 Teams 管理中心中禁用该应用。

  1. 登录到 Teams 管理中心。

  2. 转到 “**Teams 应用**” > “**管理应用**”。

  3. 搜索“审批”应用。

     ![显示管理中心导航，Teams应用>"管理应用"。](media/manage-approval-apps.png)

  4. 选择 **"审批"**。

  5. 选择切换开关以为你的组织禁用该应用。

     :::image type="content" alt-text="显示"审批"应用的详细信息。" source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="retention-policy"></a>保留策略

从"审批"应用创建的审批存储在默认 CDS 环境中，该环境目前不支持备份。 详细了解如何[备份和还原环境 - Power Platform\| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

在团队所有者从 Microsoft Forms Web 应用中的已删除表单选项卡中清理之前，不会删除存储在  Forms 中的数据。

## <a name="data-limitations"></a>数据限制

每个团队最多可以包含 400 个审批模板，每个模板根据 Microsoft Forms 中的当前功能最多可收集 50，000 个请求。

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

- 查看了电子签名请求详细信息

- 已审阅电子签名请求

- 已取消电子签名请求

- 创建新模板

- 编辑现有模板

- 启用/禁用模板

- 查看的模板

若要访问 Flow 中的更多审核审批，请为主审批实体“审批”、“审批请求”和“审批响应”在默认环境中启用和配置审核。 创建、更新和删除操作是审批记录的可审核事件。 详细了解[安全性和合规性的审核数据和用户活动 - Power Platform\| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。

可在 [Microsoft 365 安全与合规中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)中进一步自定义。

1. 若要使用预配置的报告，请登录到 Microsoft 365 安全与合规中心。

2. 选择“**搜索和调查**”。

3. 搜索审核日志，然后选择“**Dynamics 365 活动**”选项卡。

详细了解 [Microsoft Dataverse 和模型驱动的应用活动日志记录 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。

## <a name="security"></a>安全性

在 Teams“审批”应用中，用户能够创建新的审批并查看其已发送和接收的审批。 用户无法访问其他人创建的审批，除非他们是请求的回应者或查看者。

> [!Note]
> 如果用户属于创建审批的聊天或频道的一部分，则他们将被赋予请求的查看者角色。 如果在创建审批时他们未获得该角色，则他们无法对请求执行操作。

## <a name="approvals-e-signature-integration"></a>审批电子签名集成

若要使用"审批"应用电子签名功能，需要获得想要使用的特定电子签名提供商的许可证。 若要获取组织的许可证，您需要转到提供商的网站。

### <a name="enable-or-disable-e-signature-providers"></a>启用或禁用电子签名提供程序

可以使用 Teams 管理中心来控制哪些第三方电子签名提供商可供"审批"应用中用户使用。 默认情况下，电子签名提供程序在"审批"应用中启用。 禁用电子签名提供商时，用户创建审批时将无法访问该提供商。 用户还无法查看使用该提供程序创建的电子邮件签名请求。

1. 在管理中心左侧导航Teams，转到"Teams **管理** > **应用"**。
2. 搜索"审批"应用，然后选择它。
3. 转到"**设置**"选项卡，然后执行下列一项或多项操作：

    - 若要启用或禁用 Adobe Sign，请切换为"开 **"或** " **关"**。
    - 若要启用或禁用 DocuSign，请切换为"开 **"或** " **关"**。
4. 选择" **提交"**。

从"审批"应用创建的电子签名审批存储在所选提供商的云环境中。 若要导出有关电子签名的数据，您需要转到提供商的网站。 有关电子签名协议的存储、导出和保留详细信息，请参阅提供商的文档。
