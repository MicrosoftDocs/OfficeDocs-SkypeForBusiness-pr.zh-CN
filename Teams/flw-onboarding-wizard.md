---
title: 使用"一线员工加入向导"让一线员工启动并运行
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用"一线员工加入向导"在Teams为组织中一线员工和经理量身定制的体验。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 461e73a4c4008d028e564c25b5842c7b59e2a57b
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365912"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用"一线员工加入向导"让一线员工启动并运行

> [!NOTE]
> 本文介绍尚未发布的功能。 即将推出。 如果你是管理员，你可以了解此功能何时将在消息中心消息中心 (中[Microsoft 365 管理中心) 。](https://portal.office.com/adminportal/home) 若要随时了解即将推出的Teams功能，请查看"Microsoft 365[路线图"。](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>概述

"一线员工加入"向导Microsoft 365 管理中心简化了将一线员工加入组织。 通过向导，可以在专为一线员工Microsoft Teams部署体验。 使用向导，可以轻松开始试点部署Teams组织中一线员工部署。

该向导为一线员工设置一个团队，并将许可证和 [策略包](manage-policy-packages.md) 分配给每个团队成员。 可以从头开始或从团队模板创建团队，然后[](get-started-with-teams-templates-in-the-admin-console.md)添加用户并分配角色。 该角色确定向导分配给每个用户的策略包。

该向导适用于至少具有一个 F 许可证Microsoft 365组织。 可以多次运行该向导，以向Teams或组织中不同位置的一线员工推出该向导。

> [!NOTE]
> 通过此向导，可快速载入一线Teams通过 Microsoft 365 管理中心。 有关如何使用脚本将 Teams部署到一线员工，请参阅如何为Teams工作人员大规模[预配服务](flw-scripted-deployment.md)。

## <a name="run-the-wizard"></a>运行向导

1. 在左侧导航栏中 [Microsoft 365 管理中心，选择](https://admin.microsoft.com/)"设置 **"。** 转到"**应用和电子邮件**"部分，然后在"让 **一** 线员工启动并运行"下，选择"查看 **"。** 可以在此处详细了解为一线Microsoft 365提供的功能。

2. 准备就绪后，选择 **"开始"以** 运行向导。

3. 输入团队的名称，选择隐私设置，并添加一个或多个团队所有者。 然后，选择是从头开始创建团队，还是从团队模板创建团队。 团队模板具有预定义的频道和选项卡，可优化团队，从而符合特定的业务需求或项目。

4. 将用户添加到团队。 还可以添加组。 如果添加组，请记住，许可证和策略包是直接分配给该组中的每个用户，而不是组本身。

5. 向每个团队成员分配以下角色之一。

    - 一线辅助角色
    - 前端管理器
    - 无

    通过分配一个"前端辅助角色"或"前端管理员"角色，该用户Teams角色量身定制的体验。 这包括用于正常一线辅助角色和经理通信和协作的预固定应用和策略。

    接下来，为每个Microsoft 365分配一个 F 许可证。 如果没有足够的许可证，可以选择"购买更多许可证 **"以购买** 更多许可证。  

6. 选择在向导完成后接收状态电子邮件的人。 电子邮件包含有关向导创建团队、添加团队成员以及向每个团队成员分配许可证和策略包的操作的成功和 &mdash; 失败信息。 使用此信息对可能发生的任何错误进行故障排除。

7. 查看你的选择，然后选择"确认 **"。**

    向导将创建团队，并将许可证和策略包分配给团队成员。 这可能需要几分钟才能完成，之后你选择的收件人会收到状态电子邮件。

8. 你已上路，但尚未完成！ 接下来，请查看 [本文运行向导后要](#what-to-do-after-running-the-wizard) 执行什么操作部分。

## <a name="what-to-do-after-running-the-wizard"></a>运行向导后要执行什么操作

运行向导后，必须：

- 让你的一线员工和经理知道他们被分配了Teams许可证。
- 如果使用的是共享设备，请确保Teams设备上安装有共享设备。 如果你的组织使用"自带设备"模型，请让你的一线员工和经理知道他们必须下载并安装Teams设备。

当一线员工Teams时，他们将收到定制的首次运行体验，包括聊天和频道、呼叫和任务管理，全部在 Teams。

## <a name="related-articles"></a>相关文章

- [在 Teams 中管理策略包](manage-policy-packages.md)
- [使用管理中心Teams模板](get-started-with-teams-templates-in-the-admin-console.md)