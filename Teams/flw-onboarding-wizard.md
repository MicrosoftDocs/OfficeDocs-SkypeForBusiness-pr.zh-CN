---
title: 使用"一线工作人员载入向导"使一线工作人员启动并运行
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用"一线员工加入向导"在Teams为组织中一线员工和经理量身定制的体验。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f8994ecc5c7aef610e040f30b43803f03c6844
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "61993188"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用"一线工作人员载入向导"使一线工作人员启动并运行

## <a name="overview"></a>概述

"一线员工加入向导"Microsoft 365 管理中心简化了将一线员工加入组织。 通过向导，可以在专为一线员工Microsoft Teams部署体验。 使用向导，可以轻松开始为组织的一线Teams部署用户。

该向导为一线员工设置一个团队，并将许可证和 [策略包](manage-policy-packages.md) 分配给每个团队成员。 可以从头开始或从团队模板创建团队，然后[](get-started-with-teams-templates-in-the-admin-console.md)添加用户并分配角色。 该角色确定向导分配给每个用户的策略包。

目前，该向导支持每次运行它时添加 100 个用户。 我们正在努力很快增加每运行一次的用户数。 请返回此处查看最新更新。

该向导可供至少具有一个 F 许可证的所有 [组织使用](https://www.microsoft.com/microsoft-365/enterprise/frontline)。 可以多次运行向导，以在整个组织的不同位置或Teams一线员工推出该向导。

观看此简短视频，大致了解如何运行向导来培训一线员工。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> 通过此向导，可以快速培训一线员工，Teams通过Microsoft 365 管理中心。 有关如何使用脚本Teams一线员工的信息，请参阅如何为Teams[员工大规模预配服务](flw-scripted-deployment.md)。

> [!NOTE]
> 该向导尚不支持 [敏感度标签](sensitivity-labels.md) 。 如果你的组织需要敏感度标签来创建团队，则你不会在向导的Microsoft 365 管理中心。

## <a name="run-the-wizard"></a>运行向导

1. 在左侧导航栏中，[Microsoft 365 管理中心](https://admin.microsoft.com/)设置 **"**。 转到" **应用和电子邮件** "部分，然后在"让 **一** 线员工启动并运行"下，选择"查看 **"**。 可以在此处详细了解为一线Microsoft 365提供的功能。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text=""一线员工"加入体验详细信息页的屏幕截图Microsoft 365 管理中心" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 准备就绪后，选择 **"开始"以** 运行向导。

3. 输入团队的名称，添加一个或多个团队所有者，然后选择隐私设置。 然后，选择是从头开始创建团队，还是从团队模板创建团队。 团队模板具有预定义的频道和选项卡，可优化团队，从而符合特定的业务需求或项目。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="向导的"设置团队"页面的屏幕截图" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. 将用户添加到团队。 还可以添加组。 如果添加组，请记住，许可证和策略包是直接分配给该组中的每个用户，而不是组本身。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="向导的"添加用户"页的屏幕截图，你将用户和组添加到团队" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 向每个团队成员分配以下角色之一：一线员工、前端经理、无。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="向导的"分配作业角色"页的屏幕截图，其中向团队成员分配角色、位置和许可证" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    通过分配一个"前端辅助角色"或"前端管理员"角色，该用户将收到一个策略包。 策略包将创建一个Teams角色定制的应用体验。 此体验包括用于正常一线辅助角色和经理通信和协作的预固定应用和策略。

    接下来，选择一个位置，并为每个Microsoft 365分配一个 F 许可证。 如果没有足够的许可证，可以选择"购买更多许可证 **"以购买** 更多许可证。  

6. 选择在向导完成后接收状态电子邮件的人。 电子邮件包含有关向导&mdash;执行的操作的成功和失败信息，包括创建团队、添加团队成员以及向每个团队成员分配许可证和策略包。 使用此信息对可能发生的任何错误进行故障排除。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="向导的"添加状态电子邮件收件人"页的屏幕截图" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 查看选择，然后选择"确认 **"**。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="向导的"审阅团队"页面的屏幕截图，您可以在其中查看团队设置" lightbox="media/flw-onboarding-wizard-review-team.png":::

    向导将创建团队，并将许可证和策略包分配给团队成员。 可能需要几分钟才能完成，之后你选择的收件人会收到状态电子邮件。

8. 你已上路，但尚未完成！ 接下来，请查看 [本文运行向导后要](#what-to-do-after-running-the-wizard) 执行什么操作部分。

## <a name="what-to-do-after-running-the-wizard"></a>运行向导后要执行什么操作

运行向导后，必须：

- 让你的一线员工和经理知道他们被分配了Teams许可证。
- 如果使用共享设备，请确保Teams设备上安装有共享设备。 如果你的组织使用"自带设备"模型，请让你的一线员工和经理知道他们必须下载并安装Teams设备。

当一线员工Teams时，他们将收到定制的首次运行体验，包括聊天和频道、呼叫和任务管理，全部在 Teams。

## <a name="related-articles"></a>相关文章

- [在 Teams 中管理策略包](manage-policy-packages.md)
- [使用管理中心Teams模板](get-started-with-teams-templates-in-the-admin-console.md)
