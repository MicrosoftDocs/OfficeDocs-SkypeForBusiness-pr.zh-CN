---
title: 使用网络规划器Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理员可以了解如何使用网络规划器来确定网络Microsoft Teams。
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
ms.openlocfilehash: 08884e7a8cf4aaebf7f2063cec0e80fcf5619ced
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731311"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用网络规划器Microsoft Teams

网络规划器是新的工具，可在 Teams管理中心使用。 可以通过访问规划网络规划器  >  **找到它**。 只需几个步骤，网络规划器就可以帮助你确定和组织连接整个Microsoft Teams用户的网络要求。 只要您提供网络的详细信息和 Teams 的使用场景，网络规划器便会计算出在您组织的所有地点部署 Teams 和云语音的网络要求。

![网络规划器屏幕截图。](media/network-planner.png)

网络规划器允许：

- 使用网站和 Microsoft 推荐角色创建组织的表示形式 (办公室工作人员、远程工作人员以及Teams聊天室系统) 。

    > [!NOTE]
    > 推荐角色是根据最佳使用方案和典型Teams数据开发的。 但是，除了三个推荐角色外，还可以创建最多三个自定义角色。

- 生成报告，并计算Teams带宽要求。

若要使用网络规划器，你必须是全局管理员、Teams管理员或Teams管理员。

## <a name="create-a-custom-persona"></a>创建自定义角色

按照以下步骤创建自定义角色：

1. 转到管理中心内Microsoft Teams规划器。

2. 在"**角色"选项卡上**，单击 **"+ 自定义角色"。** 

3. 在 **"新建自定义角色"** 窗格中，添加新角色的名称和说明。

4. 选择此角色将在组织中使用的权限。

5. 单击“**保存**”。

## <a name="build-your-plan"></a>构建计划

请按照以下步骤开始构建网络计划：

1. 转到管理中心内Microsoft Teams规划器。

2. 在"**网络计划"** 选项卡上，单击 **"添加网络计划"。**

3. 输入网络计划的名称和说明。 网络计划将显示在可用计划列表中。

4. 单击计划名称以选择新计划。

5. 添加网站以创建组织网络设置的表示形式。

    根据组织的网络，你可能希望使用网站来表示建筑物、办公室位置或其他内容。 站点可能通过 WAN 进行连接，以允许共享 Internet 和/或 PSTN 连接。 为获得最佳结果，请创建具有本地连接的网站，然后再创建远程连接到 Internet 或 PSTN 的网站。

    创建网站：

    1. 为网站添加名称和说明。

    2. 在 **"网络** 设置"下，添加该站点上的网络用户 (用户) 。

    3. 添加网络详细信息：启用 WAN、WAN 容量、Internet 出口 (**本地** 或远程 **) ，** 以及 PSTN (无、本地或远程) 。

      > [!NOTE]
      > 必须添加 WAN 和 Internet 容量编号，在生成报告时查看特定的带宽建议。

    4. 单击“**保存**”。

## <a name="create-a-report"></a>创建报表

添加所有网站后，可以创建报表，如下所示。

1. 在"**报表"选项卡** 上，单击 **"启动报表"。**

2. 对于您创建的每个网站，跨可用角色分配用户数。 如果使用 Microsoft 推荐的角色，该数字将自动 (80% 的办公人员以及 20% 的远程) 。

3. 完成分发后，单击"生成 **报表"。**

    生成的报告将在多个不同的视图中显示带宽要求，以便可以清楚地了解输出：
    - 包含单个计算的表将显示每个允许活动的带宽要求。
    - 其他视图会显示总体带宽需求以及建议。

4. 单击“**保存**”。 报表将在报表列表中提供，供以后查看。

## <a name="example-scenario"></a>应用场景示例

有关如何使用网络规划器设置网络计划和使用这些步骤生成报表的示例，请仅下载网络规划器 How-To PowerPoint 幻灯片 (英语[](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)) 。
