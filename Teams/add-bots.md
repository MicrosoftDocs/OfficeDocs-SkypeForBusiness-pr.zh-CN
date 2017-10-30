---
title: "在 Microsoft Teams 中为私人聊天和频道添加聊天机器人 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Microsoft Teams 中为私人聊天和频道添加聊天机器人、创建自定义聊天机器人以及为私人聊天侧向加载你自己的聊天机器人。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 905a105fba269aebb2b01cbccc1a47e7667ca341
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
==========================================================

聊天机器人是自动化程序，设置它们是为了响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。 聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。 适用于 Microsoft Teams 的聊天机器人基于 [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) 构建而成，可以轻松地为 Microsoft Teams 启用使用此框架开发的聊天机器人。

当前，Microsoft Teams 支持在私人聊天和团队的频道中使用聊天机器人。 管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span>

可以在 Microsoft Teams 中利用由社区开发且已可用的聊天机器人。 必须在租户级别启用聊天机器人的功能和聊天机器人的侧向加载，自定义聊天机器人才能正常运行。 可以在私人聊天或频道中使用聊天机器人。 对于频道，团队所有者或成员可以添加聊天机器人。

<a name="add-bots-for-private-chat-and-channels"></a>为私人聊天和频道添加聊天机器人
--------------------------------------

为私人聊天和频道集成聊天机器人的方式有两种：

1.  为**私人聊天**或**频道**安装公开提供的聊天机器人。 （这是第一种方式。）

2.  或者，要查找聊天机器人，请导航到**“聊天”**，搜索**联系人**，然后单击**“发现应用”**。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  选择你要与其对话的**聊天机器人**，如下所示。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  选择后，为聊天机器人提供**权限**，然后选择是否要**在私人聊天中使用聊天机器人**，或选择要在其中使用聊天机器人的**团队**。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  或者，要在团队的频道中使用聊天机器人，只需单击**“查看团队和聊天机器人”**。 你可以在此处发现其他聊天机器人。

6.  随时可以从团队中删除聊天机器人。 只需单击**“查看团队和聊天机器人”**查看所有聊天机器人，然后**删除**你要删除的聊天机器人。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a>为 Microsoft Teams 创建自定义聊天机器人
--------------------------------------

你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。 请参阅[为 Microsoft Teams 创建和测试聊天机器人](https://go.microsoft.com/fwlink/?linkid=854371)指导，了解如何开发和发布自己的聊天机器人。

创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。 如果不发布，则聊天机器人保持专用状态。 你还可以要求你的用户先登录才能使用聊天机器人。 要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。 请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。

可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。

<a name="side-load-your-own-bot-for-private-chat"></a>为私人聊天侧向加载你自己的聊天机器人
---------------------------------------

1.  创建了你的聊天机器人后，导航到你开发的聊天机器人的**“聊天机器人仪表板”**[页面](https://go.microsoft.com/fwlink/?linkid=854374)，在**“详细信息”**下方，复制**Microsoft 应用 ID**。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  在 Microsoft Teams 中的**“聊天”**窗格上，选择**添加聊天图标**。 将你的聊天机器人的 **Microsoft 应用 ID** 粘贴到**“至:”**。

![](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  应用 ID 将解析为你的**聊天机器人名称**，然后你可以使用该聊天机器人启动聊天对话。
