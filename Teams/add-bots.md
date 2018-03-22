---
title: 在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
description: 了解如何在 Microsoft Teams 中为私人聊天和频道添加聊天机器人、创建自定义聊天机器人以及为私人聊天侧向加载你自己的聊天机器人。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50abaf5e6fb15451bfa1695ab2a16e0ce1747232
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。 聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。 适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成， 可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。 有关详细信息，请参阅[Office 365 提供组织中的管理 Microsoft 小组功能](enable-features-office-365.md)。

当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。 管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span>

可以在 Microsoft Teams 中利用由社区开发的聊天机器人。 必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。 可以在私人聊天或频道中使用聊天机器人。 对于频道，团队所有者或成员可以添加聊天机器人。

有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)中的“使用聊天机器人”一节。 




<a name="create-custom-bots-for-microsoft-teams"></a>为 Microsoft Teams 创建自定义聊天机器人
--------------------------------------

你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。 请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。

创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。 如果不发布，则聊天机器人保持专用状态。 你还可以要求你的用户先登录才能使用聊天机器人。 要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。 请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。

可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。

<a name="side-load-your-own-bot-for-private-chat"></a>为私人聊天侧向加载你自己的聊天机器人
---------------------------------------

1.  创建聊天机器人后，转到你开发的聊天机器人的**“聊天机器人仪表板”**[页面](https://go.microsoft.com/fwlink/?linkid=854374)，然后在**“详细信息”**下复制**“Microsoft 应用 ID”**。![突出显示 Microsoft 应用 ID 的聊天机器人的详细信息页面屏幕截图。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png) 



2.  在 Microsoft Teams 中的**“聊天”**窗格上，选择**添加聊天图标**。 将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到**“至:”**。 ![具有“添加聊天”图标且“至:”行中突出显示了 Microsoft 应用 ID 的聊天窗格屏幕截图。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。
