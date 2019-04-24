---
title: 在 Microsoft Teams 中搜索事件的审核日志
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解如何从 Office 365 审核日志检索 Microsoft Teams 数据。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194989"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 Microsoft Teams 中搜索事件的审核日志
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

审核日志可帮助你调查 Office 365 服务中的特定活动。 对于 Teams，审核的部分活动包括：

-   团队创建

-   团队删除

-   添加频道

-   更改设置

要查看 Office 365 中审核的活动的完整列表，请阅读[在 Office 365 安全与合规中心搜索审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="turn-on-auditing-in-teams"></a>在 Teams 中启用审核

您可以查看审核数据之前，必须**安全 & 合规性中心**中的审核功能的第一个开启 (https://protection.office.com)。 有关启用审核的帮助，请阅读[启用或关闭 Office 365 审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。


> [!IMPORTANT]
> 只有在启用审核后才能获取审核数据。



## <a name="retrieve-teams-data-from-the-audit-log"></a>从审核日志检索 Teams 数据

1.  要检索审核日志，请转到[安全与合规中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在“**搜索和调查**”下，选择“**审核日志搜索**”。![安全与合规中心的“审核日志搜索”页面屏幕截图。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  使用“**搜索**”按活动、日期和你要审核的用户进行筛选。

3.  将结果导出到 Excel 以供进一步分析。


> [!IMPORTANT]
> 审核数据仅在审核启用后在审核日志中显示。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>视频：技术提示：在 Teams 中使用审核日志搜索

加入 Teams 计划经理 Ansuman Acharya，他将说明如何在 Office 365 安全与合规中心执行 Teams 审核日志搜索。 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






