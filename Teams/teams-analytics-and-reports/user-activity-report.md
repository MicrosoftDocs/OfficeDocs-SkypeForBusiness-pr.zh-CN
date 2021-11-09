---
title: Microsoft Teams 用户活动报告
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams 管理中心中的Microsoft Teams活动报告来查看组织中用户如何使用Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd33b28f4157a6ba58ab2c4291bfa4ef558e97ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832986"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 用户活动报告

"Teams用户活动"报表可深入了解组织中用户在活动类型中Teams。 您可以通过计划外会议（1：1 和群组通话） (计划外通信的用户) 。 查看用户已Teams的会议，以及用户Teams的会议。 查看有关屏幕、视频和音频分钟数以及聊天通信统计信息的详细信息，例如有多少用户回复和发布频道消息，以及多少用户参与 1：1 或群组聊天消息。

> [!NOTE]
> 目前无法计划用户活动报告。

## <a name="view-the-user-activity-report"></a>查看用户活动报告

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。

1. 在管理中心的左侧导航Microsoft Teams，选择 **"分析"&报告**  >  **"使用情况报告"。** 在"**查看报表"** 选项卡上的"报表 **"下**，选择 **Teams活动"。**
2. 在 **"日期范围**"下，选择一个范围，然后选择"**运行报表"。**

    ![屏幕截图：Teams管理中心中的用户活动Teams标注。](../media/teams-reports-user-activity-with-callouts.png "屏幕截图：Teams管理中心中的用户活动Teams标注")

## <a name="interpret-the-report"></a>解释报告

| 标注 |说明  |
|--------|-------------|
|**1**   |可以查看Teams用户活动报告，了解过去 7 天、30 天或 90 天的趋势。 |
|**2**   |每个报表包含此报表的生成日期。 报告通常反映活动时间 24 小时的延迟。 |
|**3**   |图中的时序数据点显示租户中聚合的不同使用情况指标。 |
|**4**   |表格数据表示每个用户聚合的不同使用情况指标。 |
|**5**   |<ul><li>图表上的 X 轴表示报告的所选数据范围。</li> <li> Y 轴表示活跃项目或活动的计数。</li> </ul>将鼠标悬停在表示给定日期中某项目或活动的点可查看该项目或活动在该给定日期的实例数量。|
|**6**   | 在租户级别以图形表示的每个指标。 通过选择图例中的项目来筛选在图表上看到的项目。 选择 **"频道消息****"、"回复消息****"、"聊天消息**"或"已组织会议"以查看与每个消息相关的信息。  更改此选项不会更改表格中的信息。 |
|**7**   |下表提供了按用户分类的使用情况。   <ul><li>**显示** 名称显示名称用户的名称。 选择显示名称转到管理中心中的用户详细信息Microsoft Teams页面。</li><li>**频道** 消息是用户于指定时间段在团队频道中发布的唯一消息数。</li><li>**回复** 消息是用户指定时间段在团队频道中发布的唯一答复消息数。</li> <li>**"发布** 消息"表示用户在指定的时间段在团队频道中发布的唯一帖子消息数。</li><li>**聊天** 消息是用户于指定时间段在私人聊天中发布的唯一消息数。</li><li>**紧急** 消息是用户在指定的时段内在聊天中发布紧急消息的数量。</li><li>**组织的"** 总会议数"是用户在指定时段内组织的一次计划会议、定期会议 <em></em>、计划外会议和未分类会议的总和。</li><li>**安排一次的会议** 是用户于指定时间段组织的一次计划会议次数。</li><li>**组织定期会议** 是用户于指定时间段组织的定期会议数。</li><li>**临时组织会议** 是用户于指定时段内组织的计划外会议数。</li><li>**参与的会议** 总数是用户在指定的时段内参与的一次性计划、定期、计划外和未分类会议 <em></em>的总和。</li><li>**计划的一次会议** 是用户指定时间段参与的一次计划会议次数。</li><li>**参与的会议计划的定期** 会议数是用户指定时间段参与的定期会议数。</li><li>**临时参与会议** 是用户指定的时间段参与计划外会议的数量。</li><li>**1：1** 调用是用户指定的时段内参与的 1：1 调用数。</li><li>**"音频** 时间"是用户 (期间) 的总音频时间（分钟）。</li><li>**视频时间** 是用户 () 期间参与的总视频时间（ 分钟）。</li><li>**屏幕共享** 时间是用户 (期间) 的总屏幕共享时间。</li>  <li>**"上次** 活动"是用户 (上次) UTC 时间Teams的日期。</li><li>**其他活动** 跟踪用户何时被视为活动用户，但对于聊天消息、1：1 通话、频道消息、总会议和组织的会议，其值为 0。 例如，当用户打开通道消息帖子但不回复它时，或者当用户收到私人消息并阅读它但不响应它时，操作会执行。</li> <li>**未分类** 会议是不能分类为计划会议、定期会议或计划外会议。 这些信息的数量短，并且大多数由于篡改的遥测信息而无法识别</li> </ul>**组呼叫** 已替换为"安排临时 **会议和****会议参与临时会议"。** 这两个值的总和等于 Group 调用 **测量的值**。
|**8**   |选择“**编辑列**”可在表格中添加或删除列。 |
|**9**   |将报表导出到 CSV 文件进行脱机分析。 选择 **"导出Excel"，** 然后选择"下载"选项卡，选择"下载"，在报表准备就绪后下载报表。<br><br>![显示要下载的导出报表的"下载"选项卡的屏幕截图。](../media/teams-reports-export-to-csv.png) <br>在报表视图中查看Excel，还会看到一个 **ID** 列，它表示用户 ID。 用户 ID 通常是字母数字字符串。 |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使用户活动Teams数据匿名，你必须是全局管理员。 这会隐藏使用 MD5 (的标识信息) ，例如显示名称、电子邮件和AAD ID 及其导出。

1. 在Microsoft 365 管理中心中，转到 **"设置** \> **Org 设置"，在**"服务"选项卡下，选择"报表 **"。**
    
2. 选择 **"报告**"，然后选择"**显示匿名标识符"。** 此设置同时应用于管理中心Microsoft 365 管理中心Teams使用情况报告。
  
3. 选择"**保存更改"。**

## <a name="related-topics"></a>相关主题

- [Teams 分析和报告](teams-reporting-reference.md)
