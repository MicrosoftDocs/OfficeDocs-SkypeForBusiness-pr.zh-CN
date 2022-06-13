---
title: 使用网络规划器进行Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理员可以了解如何使用网络规划器来确定Microsoft Teams的网络要求。
ms.localizationpriority: medium
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
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045551"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用网络规划器进行Microsoft Teams

网络规划器是在Teams管理中心提供的新工具。 可以通过转到 **规划** > **网络规划器** 来找到它。 只需几个步骤，网络规划器就可以帮助你确定和组织网络要求，以便在组织中连接Microsoft Teams用户。 只要您提供网络的详细信息和 Teams 的使用场景，网络规划器便会计算出在您组织的所有地点部署 Teams 和云语音的网络要求。

![网络规划器的屏幕截图。](media/network-planner.png)

网络规划器允许执行以下操作：

- 使用网站和 Microsoft 推荐的人员 (办公室工作人员、远程工作人员和Teams会议室系统) 创建组织的表示形式。

    > [!NOTE]
    > 建议的人物是根据Teams最佳使用方案和典型使用模式中的数据开发的。 但是，除了三个推荐角色之外，最多可以创建三个自定义角色。

- 生成报表并计算Teams使用情况的带宽要求。

若要使用网络规划器，必须是全局管理员、Teams管理员或Teams通信管理员。

## <a name="create-a-custom-persona"></a>创建自定义角色

按照以下步骤创建自定义角色：

1. 转到Microsoft Teams管理中心的网络规划器。

2. 在 **“角色”** 选项卡上，单击 **“+ 自定义角色**”。 

3. 在 **“新建自定义角色** ”窗格中，添加新角色的名称和说明。

4. 选择此角色将在组织中使用的权限。

5. 单击“**保存**”。

## <a name="build-your-plan"></a>生成计划

按照以下步骤开始构建网络计划：

1. 转到Microsoft Teams管理中心的网络规划器。

2. 在“ **网络计划”** 选项卡上，单击 **“添加网络计划**”。

3. 输入网络计划的名称和说明。 网络计划将显示在可用计划的列表中。

4. 单击计划名称以选择新计划。

5. 添加网站以创建组织的网络设置的表示形式。

    根据组织的网络，你可能希望使用网站来表示建筑物、办公地点或其他内容。 站点可能由 WAN 连接，以允许共享 Internet 和/或 PSTN 连接。 为了获得最佳结果，请先创建具有本地连接的站点，然后再创建远程连接到 Internet 或 PSTN 的站点。

    若要创建网站，请执行以下操作：

    1. 添加网站的名称和说明。

    2. 在 **“网络设置**”下，添加该站点的网络用户数 (所需的) 。

    3. 添加网络详细信息：已启用 WAN、WAN 容量、Internet 出口 (**本地** 或 **远程**) ，以及 PSTN 出口 (无、本地或远程) 。

      > [!NOTE]
      > 在生成报表时，必须添加 WAN 和 Internet 容量号才能查看特定带宽建议。

    4. 单击“**保存**”。

## <a name="create-a-report"></a>创建报表

添加所有网站后，可以创建报表，如下所示。

1. 在 **“报** 表”选项卡上，单击 **"开始"菜单报表**。

2. 对于创建的每个网站，跨可用角色分配用户数。 如果使用 Microsoft 推荐的人物，则会自动 (80% 的办公人员和 20% 的远程辅助角色) 分发该数字。

3. 完成分发后，单击 **“生成报表**”。

    生成的报表将在多个不同视图中显示带宽要求，以便可以清楚地了解输出：
    - 具有单个计算的表将显示每个允许活动的带宽要求。
    - 另一个视图将通过建议显示整体带宽需求。

4. 单击“**保存**”。 报表将在报表列表中提供，供以后查看。

## <a name="example-scenario"></a>应用场景示例

有关如何使用网络规划器设置网络计划并使用这些步骤生成报表的示例，请下载网络[规划器How-To PowerPoint只](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (英语) 。
