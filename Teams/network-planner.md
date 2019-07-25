---
title: 使用 Microsoft 团队的网络 Planner
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: 了解如何使用网络规划器确定 Microsoft 团队的网络要求。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea6a4a5989df0a780f75220ec314439f7dafcbe
ms.sourcegitcommit: 384e123f3b5cf1600ebd5ddd69bd022f9b8ba0f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35861877"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用 Microsoft 团队的网络 Planner

网络规划器是团队管理中心提供的新工具。 可通过转到**组织范围内的设置** > **网络 planner**找到它。 通过以下几个步骤, 网络规划器可以帮助你确定和组织在你的组织中连接 Microsoft 团队用户的网络要求。 当你提供网络详细信息和团队使用情况时, 网络 Planner 会计算你的网络要求, 以便在组织的物理位置部署团队和云语音。

![网络 Planner 的屏幕截图](media/network-planner.png)

网络 Planner 允许您:

- 使用网站和 Microsoft 推荐的角色 (office 工作人员、远程工作人员和团队室系统) 创建组织的表示形式。

    > [!NOTE]
    > 根据团队最佳使用方案和典型使用模式中的数据开发了推荐的角色。 但是, 除了三个推荐的角色外, 你还可以创建最多三个自定义角色。

- 生成报表并计算团队使用情况的带宽要求。

若要使用网络 Planner, 您必须是全局管理员、团队服务管理员或团队通信管理员。

## <a name="create-a-custom-persona"></a>创建自定义角色

请按照以下步骤创建自定义角色:

1. 转到 Microsoft 团队管理中心中的网络 Planner。

2. 在 "**角色**" 选项卡上, 单击 " **+ 自定义角色**"。 

3. 在 "**新建自定义角色**" 窗格中, 为新角色添加名称和说明。

4. 选择此角色将在组织内使用的权限。

5. 单击“**保存**”。

## <a name="build-your-plan"></a>构建你的计划

请按照以下步骤开始构建你的网络计划:

1. 转到 Microsoft 团队管理中心中的网络 Planner。

2. 在 "**网络计划**" 选项卡上, 单击 "**添加网络计划**"。

3. 输入网络计划的名称和说明。 "网络计划" 将显示在可用计划列表中。

4. 单击计划名称以选择新计划。

5. 添加网站以创建组织的网络设置的表示形式。

    根据您所在组织的网络, 您可能希望使用网站来表示建筑物、办公地点或其他内容。 网站可能通过 WAN 连接, 以允许共享 internet 和/或 PSTN 连接。 为获得最佳结果, 请先创建具有本地连接的网站, 然后再创建远程连接到 internet 或 PSTN 的网站。

    要创建网站, 请执行以下操作:

    1. 为您的网站添加名称和说明。

    2. 在 "**网络设置**" 下, 添加该站点上的网络用户数 (必需)。

    3. 添加网络详细信息: 支持 WAN 的、WAN 容量、internet 出口 (**本地**或**远程**) 以及 PSTN 出口 (无、本地或远程)。

      > [!NOTE]
      > 你必须添加 WAN 和 internet 容量数字, 才能在生成报告时查看特定的带宽建议。

    4. 单击“**保存**”。

## <a name="create-a-report"></a>创建报表

添加所有网站后, 您可以创建报表, 如下所示。

1. 在 "**报表**" 选项卡上, 单击 "**开始报表**"。

2. 对于创建的每个网站, 在可用的角色间分配用户数。 如果您使用 Microsoft 推荐的角色, 该号码将自动分发 (80% 的 office 工作人员和 20% 的远程工作人员)。

3. 完成分发后, 单击 "**生成报表**"。

    生成的报表将显示多个不同视图中的带宽要求, 以便你可以清楚地了解输出:
    - 具有单个计算的表将显示每个允许的活动的带宽要求。
    - 其他视图将显示具有建议的整体带宽需求。

4. 单击“**保存**”。 报表将在 "报表" 列表中提供, 供以后查看。

## <a name="example-scenario"></a>示例方案

有关如何使用网络计划程序设置网络计划并使用这些步骤生成报表的示例, 请下载[网络 Planner 的操作方法 PowerPoint 幻灯片](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)(仅限英语版)。
