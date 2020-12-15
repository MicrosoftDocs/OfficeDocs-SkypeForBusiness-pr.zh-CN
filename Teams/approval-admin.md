---
title: Teams 中的审批应用程序可用性
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的审批应用程序可用性。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675170"
---
# <a name="teams-approvals-app-availability"></a>Teams 审批应用可用性

[!INCLUDE [preview-feature](includes/preview-feature.md)]

审批应用作为个人应用可供所有 Microsoft Teams 用户使用。
"审批"应用提供了一种简单方法，在 Teams 中为结构化和非结构化审批提供审核、合规性、责任和工作流。

 ![显示审批应用](media/approvals-selection.png)

用户可以固定"审批"应用以将其保存到菜单栏。

 ![显示具有固定选项的审批应用](media/approvalApp-pin.png)

从"审批"应用创建的第一个审批将触发在默认通用数据服务 (CDS) 预配。 从"审批"应用创建的审批将存储在默认 CDS 环境中。

本文介绍"审批"应用要求和角色。

## <a name="required-permissions-and-licenses"></a>所需的权限和许可证

若要使用"审批"应用，需要以下项目的权限：

- 创建 Microsoft CDS 数据库的权限。

- flow.microsoft.com [](https://flow.microsoft.com/)

- 目标环境中管理员角色。

- [Power Automate、Office](https://docs.microsoft.com/power-automate/get-started-approvals)365 或 Dynamics 365 的许可证。

## <a name="storage-with-cds"></a>使用 CDS 存储

COMMON Data Model (CDM) 是 CDS 中的业务和分析应用程序使用的共享数据语言。 它由 Microsoft 和合作伙伴发布的一组标准化可扩展数据架构组成，可在应用程序和业务流程之间实现数据的一致性及其含义。 详细了解 Microsoft [Power Platform 的常见数据模型](https://docs.microsoft.com/power-automate/get-started-approvals)。

了解有关"审批 ["工作流的更多内容](https://docs.microsoft.com/power-automate/modern-approvals)。

## <a name="approvals-teams-app-permissions"></a>审批 Teams 应用权限

"审批团队"应用允许你访问以下功能：

- 接收你向它提供的消息和数据。

- 向您发送消息和通知。

- 在没有 Teams 提供的标头的情况下呈现个人应用和对话框。

- 访问个人资料信息，例如姓名、电子邮件地址、公司名称和首选语言。

- 接收团队成员在频道中提供的消息和数据。

- 在频道中发送消息和通知。

- 访问团队的信息：
  - 团队名称
  - 频道列表
  - 名单 (团队成员的姓名和电子邮件地址) 。

- 使用团队的信息联系他们。

## <a name="disable-the-approvals-app"></a>禁用"审批"应用

"审批"应用默认可用。 可以在 Teams 管理中心禁用该应用。

  1. 登录到 Teams 管理中心。

  2. 展开 **Teams 应用，** 然后选择"**管理应用"。**

  3. 搜索"审批"应用。

![显示管理中心导航，突出显示"管理> Teams 应用](media/manage-approval-apps.png)

  4. 选择"审批"。

  5. 选择切换开关，为组织禁用应用。

![显示"审批"应用的详细信息](media/approvals-details.png)

## <a name="retention-policy"></a>保留策略

从"审批"应用创建的审批存储在默认 CDS 环境中，该环境目前不支持备份。 详细了解如何备份[和还原环境 - Power Platform \| Microsoft Docs。](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>审核

审批应用记录 Microsoft 365 安全与合规中心内的审核事件。 可以查看审核日志。

1. 转到 M365 合规性站点。

2. 选择" **审核"** 部分。

3. 在 Microsoft **Teams 审批活动下搜索活动**。

可以搜索以下活动：

- 创建新的审批请求

- 查看审批请求详细信息

- 已批准的审批请求

- 已拒绝审批请求

- 已取消审批请求

- 共享审批请求

- 附加到审批请求的文件

- 重新分配的审批请求

- 向审批请求添加了电子签名

若要在 Flow 中访问更多审核审批，请为主要审批实体（审批、审批请求和审批响应）在默认环境中启用和配置审核。 创建、更新和删除操作是审批记录的可审核事件。 详细了解审核数据和[用户活动以确保安全性和符合性 - Power Platform \| Microsoft Docs。](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

可以在 Microsoft 365 安全与合规中心 [进一步自定义审核](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)。

1. 若要使用预配置的报表，请登录到 Office 365 安全性和符合性。

2. 选择 **"搜索&调查**。

3. 搜索审核日志并选择 **Dynamics 365 活动** 选项卡。

详细了解[Microsoft Dataverse 和模型驱动的应用活动日志记录 - Power Platform。](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)

## <a name="security"></a>安全性

在 Teams 审批应用中，用户可以创建新的审批并查看已发送和收到的审批。 除非用户是请求的回复者或查看者，否则他们无法访问其他人创建的审批。

> [!Note]
> 如果用户是创建审批的聊天或频道的一部分，则他们将被赋予请求的查看者角色。 如果在创建审批时未赋予他们该角色，他们无法对请求采取措施。
