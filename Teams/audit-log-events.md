---
title: 在 Microsoft Teams 中搜索事件的审核日志
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 了解如何从 Office 365 审核日志检索 Microsoft Teams 数据。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341620"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 Microsoft Teams 中搜索事件的审核日志

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

审核日志可帮助你调查 Office 365 服务中的特定活动。 对于 Teams，审核的部分活动包括：

- 团队创建

- 团队删除

- 添加频道

- 更改设置

> [!NOTE]
> 来自专用频道的审核事件也会被记录为团队和标准频道。

要查看 Office 365 中审核的活动的完整列表，请阅读[在 Office 365 安全与合规中心搜索审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="turn-on-auditing-in-teams"></a>在 Teams 中启用审核

在你可以查看审核数据之前，你必须先在[安全 & 合规中心](https://protection.office.com)中启用审核。 有关启用审核的帮助，请阅读[启用或关闭 Office 365 审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。

> [!IMPORTANT]
> 只有在启用审核后才能获取审核数据。

## <a name="retrieve-teams-data-from-the-audit-log"></a>从审核日志检索 Teams 数据

1. 要检索审核日志，请转到[安全与合规中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在 "**搜索**" 下，选择 "**审核日志搜索**"。
1. 使用“**搜索**”按活动、日期和你要审核的用户进行筛选。
1. 将结果导出到 Excel 以供进一步分析。

> [!IMPORTANT]
> 审核数据仅在审核启用后在审核日志中显示。

## <a name="external-user-scenario"></a>外部用户方案

从业务角度看，您可能想要关注的一种方案是向团队环境添加外部用户。 如果启用外部用户，则监视其状态是一个好主意。

![通过批量删除触发的事件列表的屏幕截图](media/TeamsExternalUserAddPolicy.png)

此策略的屏幕截图用于监视外部用户添加允许你命名策略，根据你的业务需求设置严重性，将其设置为（在本例中为一个活动），然后建立仅专门监视添加的参数对于非内部用户，并将此活动限制为 Microsoft 团队。

然后，将能够在活动日志中查看此策略的结果：

![通过批量删除触发的事件列表的屏幕截图](media/TeamsExternalUserList.png)

在此处，你可以查看与你已设置的策略的匹配项，并根据需要进行任何调整，或将结果导出为在其他位置使用。

## <a name="mass-delete-scenario"></a>批量删除方案

如上文所述，您可以监控删除方案。 可以创建一个策略来监视团队网站的大量删除：

![策略创建页面的屏幕截图，显示用于批量工作组删除检测的策略设置](media/TeamsMassDeletePolicy.png)

如屏幕截图所示，你可以为此策略设置许多不同的参数以监视团队删除，包括严重性、单个或重复操作，以及将此限制为团队和网站删除的参数。 这可以独立于模板执行，也可以根据组织的需要，创建基于此策略创建的模板。

建立适用于您的企业的策略后，您可以在触发事件时查看活动日志中的结果：

![通过批量删除触发的事件列表的屏幕截图](media/TeamsMassDeleteList.png)

您可以筛选到已设置的策略，以查看该策略的结果。 如果你在活动日志中获得的结果不满意（也许你看到了大量结果，或者根本看不到任何结果），这可能会帮助你微调查询以使其更与你需要的内容相关。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>视频：技术提示：在 Teams 中使用审核日志搜索

加入 Teams 计划经理 Ansuman Acharya，他将说明如何在 Office 365 安全与合规中心执行 Teams 审核日志搜索。

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
