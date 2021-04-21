---
title: Teams 中的“审批”应用程序可用性
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的“审批”应用程序可用性。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e03ad5c562f7fd31599bbb86f08e411dfa4b415
ms.sourcegitcommit: fb87d64c6f98041a1da50cf4ef6ff54cdc8d1d29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902566"
---
# <a name="teams-approvals-app-availability"></a>Teams“审批”应用可用性

“审批”应用可作为个人应用提供给所有 Microsoft Teams 用户。
“审批”应用提供了一种在 Teams 中将审核、合规性、责任和工作流引入结构化审批和非结构化审批的简单方法。

 ![显示“审批”应用](media/approvals-selection.png)

用户可以固定“审批”应用以将其保存到菜单栏。

 ![显示“审批”应用以及固定选项](media/approvalApp-pin.png)

从“审批”应用创建的第一个审批将触发在默认 Common Data Service (CDS) 环境中设置审批解决方案。 从“审批”应用创建的审批将存储在默认 CDS 环境中。

本文介绍了“审批”应用要求和角色。

> [!NOTE]
> 此功能尚未向政府社区云 (GCC) 、政府社区云高 (GCCH) 和国防部 (DOD) 用户发布。

## <a name="required-permissions-and-licenses"></a>所需权限和许可证

若要使用“审批”应用，你需要以下项目的权限：

- 创建 Microsoft CDS 数据库的权限。

- [flow.microsoft.com](https://flow.microsoft.com/) 上的帐户

- 目标环境中的管理员角色。

- [Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的许可证。

## <a name="storage-with-cds"></a>通过 CDS 进行存储

Common Data Model (CDM) 是业务和分析应用程序在 CDS 中使用的共享数据语言。 它由 Microsoft 和我们的合作伙伴发布的一组标准化可扩展数据架构组成，可跨应用程序和业务流程实现数据的一致性及其含义。 了解有关 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals) 的详细信息。

了解有关[审批工作流](/power-automate/modern-approvals)的详细信息。

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

## <a name="disable-the-approvals-app"></a>禁用“审批”应用

默认情况下，“审批”应用可用。 可在 Teams 管理中心中禁用该应用。

  1. 登录到 Teams 管理中心。

  2. 展开“**Teams 应用**”，选择“**管理应用**”。

  3. 搜索“审批”应用。

![显示管理中心导航，突出显示“Teams 应用”>“管理应用”](media/manage-approval-apps.png)

  4. 选择“审批”。

  5. 选择切换开关以为你的组织禁用该应用。

![显示“审批”应用的详细信息](media/approvals-details.png)

## <a name="retention-policy"></a>保留策略

从“审批”应用创建的审批存储在默认 CDS 环境中，该环境目前不支持备份。 详细了解如何[备份和还原环境 - Power Platform\| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

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