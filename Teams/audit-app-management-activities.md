---
title: 搜索应用管理事件的审核日志
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: 了解如何审核组织中用户和管理员的 Teams 应用活动。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 9114bae9fa24a546aec2629f1f347af193b10fd5
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677502"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>搜索应用管理活动和事件的审核日志

Microsoft 365 中的 Microsoft Purview 审核（标准版），可以搜索最终用户和管理员在各种 Microsoft 365 服务中执行的活动审核记录。

在搜索审核记录之前，请确保满足以下先决条件：

* [获取组织的订阅和用户许可](/microsoft-365/compliance/set-up-basic-audit)。
* [在 Microsoft Purview 合规门户中启用审核](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
* [分配用于搜索审核日志的权限](/microsoft-365/compliance/set-up-basic-audit)。

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>搜索 Teams 中的应用事件的审核日志

Teams 中应用事件的审核日志可帮助你调查与管理员的应用管理相关的特定操作。 虽然可以在日志中搜索各种操作，但下表列出了记录的一些此类操作。

| Teams 应用操作 | 门户中的活动名称 | 说明  |
|-------|-------|:-------|
| **已安装的应用**                 | `AppInstalled`               | 应用已安装或添加到 Teams 客户端。 |
| **升级后的应用**                  | `AppUpgraded`                | 应用已升级到目录中的最新版本。 |
| **卸载的应用**               | `AppUninstalled`             | 应用已卸载或从 Teams 客户端中删除。                                   |
| **已发布的应用**                 | `AppPublishedToCatalog`      | 将应用添加到目录中。                          |
| **已更新的应用**                   | `AppUpdatedInCatalog`        | 在目录中更新应用。                        |
| **已删除的应用**                   | `AppDeletedFromCatalog`      | 从目录中删除应用。                      |
| **删除了所有组织应用** | `DeletedAllOrganizationApps` | 从目录中删除了所有组织应用。          |

<!--- organization apps = custom or 3p --->

有关审核 Teams 活动的完整列表，请参阅 [Teams 活动](audit-log-events.md#teams-activities)和 Teams 活动中的 [排班](audit-log-events.md#shifts-in-teams-activities)。

> [!NOTE]
> 还会记录来自专用频道的应用事件，因为这些事件在 Teams 和标准频道中完成。

若要搜索 Teams 应用活动的审核日志，请执行以下步骤：

1. 登录到 Microsoft Purview 合规性门户，并转到 **解决方案** > **[审核](https://compliance.microsoft.com/auditlogsearch)**。
1. 在 **“审核** ”页上，根据需要更新以下字段：

   * **日期和时间范围**：选择要检查审核日志的时间段的开始和结束日期。
   * **活动**：输入 Microsoft Teams 活动。 从列表中，选择一个或多个应用活动。 若要快速查找 Teams 活动，可以`Teams activities`在“**活动**”搜索字段中搜索单词。
   * **文件、文件夹或网站**：输入文件名、URL 或其中一部分内容。
   * **用户**：添加要搜索其审核日志的用户。

1. 选择“**搜索**”。

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="在 Microsoft Purview 合规门户中搜索 Teams 活动以审核 Teams 事件。" lightbox="media/compliance-search-teams-activities.png":::

可以将搜索的审核记录导出为 CSV 文件。 有关详细信息，请参阅 [导出、配置和查看审核日志](/microsoft-365/compliance/export-view-audit-log-records)。

> [!NOTE]
> 当用户或管理员执行上述活动之一时，Teams 会生成并存储审核记录。 在审核（标准版）中，记录将保留 90 天，这意味着可以搜索过去三个月内发生的活动。

> [!TIP]
> 作为管理员，如果要创建每用户报告，以了解用户是否已阻止或静音机器人，请参阅 [了解谁阻止、静音或卸载了机器人](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot)。

## <a name="related-articles"></a>相关文章

* [使用审核日志调查Microsoft Power Platform 安装活动](manage-power-platform-apps.md#use-audit-logs-to-check-microsoft-power-platform-installation-activity)。
* [在合规性门户中搜索审核登录](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。
* [Microsoft Purview 审核高级版概述](/microsoft-365/compliance/advanced-audit)。
* [打开或关闭审核](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。
