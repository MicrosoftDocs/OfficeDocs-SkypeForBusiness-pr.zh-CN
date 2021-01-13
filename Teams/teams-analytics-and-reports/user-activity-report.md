---
title: Microsoft Teams 用户活动报告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Microsoft Teams 管理中心中的 Teams 用户活动报告来查看组织中用户如何使用 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85d907e527f8b957abf1a5f3b8b9f0d8c5f44443
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809192"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

Teams 用户活动报表提供组织中用户在 Teams 中执行的活动类型的见解。 例如，可以通过通常称为 1：1 的未计划会议、群组通话、Teams 用户组织的会议和 Teams 用户参与的会议，查看临时通信的用户数。 我们将共享有关屏幕、视频和音频分钟数以及聊天通信统计信息的详细信息，例如有多少用户回复和发布频道消息，以及多少用户参与一对一或群组聊天消息。

## <a name="view-the-user-activity-report"></a>查看用户活动报告

只有 Teams 服务管理员才能进行这些更改。 请参阅 ["使用 Teams 管理员角色管理 Teams"，](https://docs.microsoft.com/microsoftteams/using-admin-roles) 了解获取管理员角色和权限。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"分析&报告**  >  **使用情况报告**。 在"**查看报表"** 选项卡上的 **"** 报表"下，选择 **"Teams 用户活动"。**
2. 在“**数据范围**”下，选择一个范围，然后单击“**运行报告**”。

    ![Teams 管理中心中带标注的 Teams 用户活动报告的屏幕截图](../media/teams-reports-user-activity-with-callouts.png "Teams 管理中心中带标注的 Teams 用户活动报告的屏幕截图")

## <a name="interpret-the-report"></a>解释报告

|标注 |说明  |
|--------|-------------|
|**1**   |可以查看 Teams 用户活动报告，了解过去 7 天、30 天或 90 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。 报告通常反映活动时间延迟 24 小时。 |
|**3**   |<ul><li>图表上的 X 轴是特定报表的选定日期范围。 </li><li>Y 轴表示参与活动的用户数。</li></ul>将鼠标悬停在表示给定日期的活动的点上，以查看该给定日期该活动的实例数。 |
|**4**   |可单击图例上的项目筛选要在图表上查看的内容。 例如，单击 **1：1** 通话、频道消息或 **聊天** 消息，仅查看与每个呼叫有关的信息。 更改所选内容不会更改表中的信息。 |
|**5**   |下表提供了按用户分类的使用情况。   <ul><li>**用户名** 是显示名称的用户名。 可以单击显示名称转到 Microsoft Teams 管理中心中的用户设置页面。</li><li>**频道** 消息是用户于指定时段在团队聊天中发布的唯一消息数。</li><li>**回复** 消息是用户指定时间段在团队频道中发布的唯一答复消息数。</li> <li>**"发布** 消息"是用户指定时间段在团队频道中发布的唯一发布消息数。</li><li>**聊天** 消息是用户于指定时段在私人聊天中发布的唯一消息数。</li><li>**紧急消息** 是在指定的时段内用户在聊天中发布紧急消息的数量。</li><li>**总** 会议数是用户指定时段内参与的计划和临时会议的总数。</li><li>**组织的会议** 是用户于指定时间段组织的计划会议和临时会议的数量。</li><li>**安排的会议是** 用户于指定时段内组织的计划会议数。</li><li>**临时组织会议是** 用户于指定时段组织的临时会议数。</li><li>**参与的会议** 数是用户于指定时段内参与的计划和临时会议数。</li><li>**已安排的会议** 是用户指定时段内参与的计划会议数。</li><li>**临时参与的会议** 是用户指定的时间段参与的即席会议数。</li><li>**1：1** 调用是用户指定的时段内参与的 1：1 调用数。</li><li>**音频** 时间是用户指定时间段参与的总音频时间。</li><li>**视频** 时间是用户指定的时间段参与的总视频时间。</li><li>**屏幕共享** 时间是用户指定的时间段参与的总屏幕共享时间。</li>  <li>**上次活动** 是用户 (Utc) 的最后一天。</li><li>**其他活动** 跟踪用户何时被视为活动用户，但对于聊天消息、1：1 通话、频道消息、总会议和组织的会议，其值为零。 例如，当用户打开通道消息帖子但不回复它时，或者当用户收到私人消息并读取它但不响应它时，</li> </ul>请注意，**群组** 通话已替换为临时会议和会议参与临时会议，其中这两个值的总和等于组调用 **测量的值**。
|**6**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**7**   |可以将报表导出到 CSV 文件进行脱机分析。 单击 **"导出到 Excel"，** 然后在"下载"选项卡上单击"下载"，在报表准备就绪后下载报表。<br><br>![显示要下载的导出报表的"下载"选项卡的屏幕截图](../media/teams-reports-export-to-csv.png) <br>在 Excel 中查看报表时，还将看到一个 **ID** 列，它表示团队 ID。 团队 ID 通常是字母数字字符串。 如果 **Id** 列显示 **\n，** 则意味着用户请求删除其信息。 ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
