---
title: 使用 Microsoft 团队的网络 planner
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理员可以了解如何使用网络规划器确定 Microsoft 团队的网络要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14bdc08656cdce18fc25b38ca8d226ac0e70cf27
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030618"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用 Microsoft 团队的网络 planner

网络规划器是团队管理中心提供的新工具。 可通过 **planner**  >  **网络 planner** 找到它。 通过以下几个步骤，网络规划器可以帮助你确定和组织在你的组织中连接 Microsoft 团队用户的网络要求。 当你提供网络详细信息和团队使用情况时，网络 Planner 会计算你的网络要求，以便在组织的物理位置部署团队和云语音。

![网络 planner 的屏幕截图](media/network-planner.png)

网络 planner 允许您：

- 使用网站和 Microsoft 推荐的角色 (office 工作人员、远程工作人员和团队间系统) 来创建组织的表示形式。

    > [!NOTE]
    > 根据团队最佳使用方案和典型使用模式中的数据开发了推荐的角色。 但是，除了三个推荐的角色外，你还可以创建最多三个自定义角色。

- 生成报表并计算团队使用情况的带宽要求。

若要使用网络 planner，您必须是全局管理员、团队服务管理员或团队通信管理员。

## <a name="create-a-custom-persona"></a>创建自定义角色

请按照以下步骤创建自定义角色：

1. 转到 Microsoft 团队管理中心中的网络 planner。

2. 在 " **角色** " 选项卡上，单击 " **+ 自定义角色** "。 

3. 在 " **新建自定义角色** " 窗格中，为新角色添加名称和说明。

4. 选择此角色将在组织内使用的权限。

5. 单击“ **保存** ”。

## <a name="build-your-plan"></a>构建你的计划

请按照以下步骤开始构建你的网络计划：

1. 转到 Microsoft 团队管理中心中的网络 planner。

2. 在 " **网络计划** " 选项卡上，单击 " **添加网络计划** "。

3. 输入网络计划的名称和说明。 "网络计划" 将显示在可用计划列表中。

4. 单击计划名称以选择新计划。

5. 添加网站以创建组织的网络设置的表示形式。

    根据您所在组织的网络，您可能希望使用网站来表示建筑物、办公地点或其他内容。 网站可能通过 WAN 连接，以允许共享 internet 和/或 PSTN 连接。 为获得最佳结果，请先创建具有本地连接的网站，然后再创建远程连接到 internet 或 PSTN 的网站。

    要创建网站，请执行以下操作：

    1. 为您的网站添加名称和说明。

    2. 在 " **网络设置** " 下，将该网站上的网络用户数量添加 (必需的) 。

    3. 添加网络详细信息：支持 WAN、WAN 容量、internet 出口 ( **本地** 或 **远程** ) 以及 PSTN 出局 (无、本地或远程) 。

      > [!NOTE]
      > 你必须添加 WAN 和 internet 容量数字，才能在生成报告时查看特定的带宽建议。

    4. 单击“ **保存** ”。

## <a name="create-a-report"></a>创建报表

添加所有网站后，您可以创建报表，如下所示。

1. 在 " **报表** " 选项卡上，单击 " **开始报表** "。

2. 对于创建的每个网站，在可用的角色间分配用户数。 如果你使用 Microsoft 推荐的角色，该数字将自动分发 (80% office 工作线程和20% 的远程工作) 。

3. 完成分发后，单击 " **生成报表** "。

    生成的报表将显示多个不同视图中的带宽要求，以便你可以清楚地了解输出：
    - 具有单个计算的表将显示每个允许的活动的带宽要求。
    - 其他视图将显示具有建议的整体带宽需求。

4. 单击“ **保存** ”。 报表将在 "报表" 列表中提供，供以后查看。

## <a name="example-scenario"></a>示例方案

有关如何使用网络计划程序设置网络计划并使用这些步骤生成报表的示例，请下载 [网络 planner How-To PowerPoint 幻灯片](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) "仅 (英语") 。
