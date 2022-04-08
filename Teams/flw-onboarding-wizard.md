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
description: 了解如何使用一线工作人员加入向导快速部署为组织中一线工作人员和经理量身定制的Teams体验。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac4db418927c34920614c65d6f94a400ff116a91
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703678"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>使用"一线工作人员载入向导"使一线工作人员启动并运行

## <a name="overview"></a>概述

Microsoft 365 管理中心中的一线工作人员载入向导简化了将一线工作人员加入你的组织。 通过该向导，你可以快速部署为一线员工量身定制的Microsoft Teams体验。 使用该向导，可以轻松地为组织中的一线工作人员启动Teams的试点部署。

向导为一线工作人员设置团队，并向每个团队成员分配许可证和 [策略包](manage-policy-packages.md) 。 可以从头开始或从 [团队模板创建团队](get-started-with-teams-templates-in-the-admin-console.md)，然后添加用户并分配角色。 该角色确定向导分配给每个用户的策略包。

目前，向导支持每次运行时添加 100 个用户。 我们正在努力尽快增加每次运行的用户数。 请返回此处了解最新更新。

该向导适用于具有至少一个 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline)的所有组织。 可以根据需要运行向导多次，向组织中不同地点或站点的一线员工推出Teams。

查看此简短视频，了解如何运行向导以加入一线员工。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> 通过此向导，你可以快速加入一线员工，以便通过Microsoft 365 管理中心Teams。 有关如何使用脚本将Teams部署到一线员工的信息，[请参阅如何大规模为一线工作人员预配Teams](flw-scripted-deployment.md)。

> [!NOTE]
> 该向导尚不支持 [敏感度标签](sensitivity-labels.md) 。 如果组织需要敏感度标签来创建团队，则不会在Microsoft 365 管理中心中看到向导。

## <a name="run-the-wizard"></a>运行向导

1. 在 [Microsoft 365 管理中心](https://admin.microsoft.com/)的左侧导航栏中，选择 **"设置**"。 转到 **"应用和电子邮件** "部分，然后在 **"让一线员工启动并运行**"下，选择 **"视图**"。 在这里，你可以详细了解Microsoft 365一线工作人员提供的功能。

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 管理中心中一线辅助角色载入体验的详细信息页的屏幕截图" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 准备好后，选择 **开始** 运行向导。

3. 输入团队的名称，添加一个或多个团队所有者，然后选择隐私设置。 然后，选择是从头开始还是从团队模板创建团队。 团队模板附带预定义的频道和选项卡，可针对特定的业务需求或项目优化团队。

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="向导的&quot;设置团队&quot;页的屏幕截图" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. 将用户添加到团队。 还可以添加组。 如果添加组，请记住，许可证和策略包直接分配给组中的每个用户，而不是组本身。

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="向导的&quot;添加用户&quot;页面的屏幕截图，向团队添加用户和组" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 将以下角色之一分配给每个团队成员：一线工作者、前线经理、无。 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="向导的&quot;分配作业角色&quot;页的屏幕截图，向团队成员分配角色、位置和许可证" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    通过分配一线辅助角色或一线管理员角色，该用户将收到策略包。 策略包将在根据角色定制的Teams中创建体验。 此体验包括预固定的应用和策略，用于健康的一线员工以及经理的沟通和协作。

    接下来，选择一个位置，并向每个团队成员分配Microsoft 365 F 许可证。 如果没有足够的许可证，可以选择 **购买更多许可证** 以购买更多许可证。  

6. 选择在向导完成后接收状态电子邮件的用户。 电子邮件包含有关向导&mdash;创建团队、添加团队成员以及向每个团队成员分配许可证和策略包的操作的成功和失败信息。 使用此信息对可能发生的任何错误进行故障排除。

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="向导的&quot;添加状态电子邮件收件人&quot;页的屏幕截图" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 查看所选内容，然后选择 **"确认**"。

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="查看团队设置的向导的&quot;评审团队&quot;页面的屏幕截图" lightbox="media/flw-onboarding-wizard-review-team.png":::

    向导创建团队，并向团队成员分配许可证和策略包。 可能需要几分钟才能完成，之后选择的收件人将收到状态电子邮件。

8. 你在路上， 但你还没有完成！ 接下来，查看运行本文 [的向导部分后要执行](#what-to-do-after-running-the-wizard) 的操作。

## <a name="what-to-do-after-running-the-wizard"></a>运行向导后要执行的操作

运行向导后，请务必执行以下操作：

- 让一线员工和经理知道他们已获得Teams许可证。
- 如果组织使用共享设备，请确保在这些设备上安装Teams。 添加到团队的用户将收到一封欢迎电子邮件，提示他们打开Teams。
- 如果组织使用 BYOD) 模型 ("自带设备"，请让添加到团队的每个用户知道他们必须下载并安装Teams到其设备。 他们还会收到一封欢迎电子邮件，提示他们下载Teams。

    > [!NOTE]
    > 请记住，拥有 F1 许可证的用户不会收到欢迎电子邮件，因为 F1 许可证不包括电子邮件访问权限。  

当一线员工首次打开Teams时，他们将获得量身定制的首次运行体验，其中包括聊天和频道、呼叫和任务管理，所有体验都在Teams中。

## <a name="related-articles"></a>相关文章

- [在 Teams 中管理策略包](manage-policy-packages.md)
- [在Teams管理中心使用团队模板](get-started-with-teams-templates-in-the-admin-console.md)
