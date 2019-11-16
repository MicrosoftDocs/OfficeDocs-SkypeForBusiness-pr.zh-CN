---
title: 在 Microsoft Teams 中为私人聊天和频道添加聊天机器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 了解如何在 Microsoft 团队中为个人聊天、群组聊天和频道添加机器人，并上传自己的用于个人聊天、群组聊天和频道的 bot。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "37516158"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>在 Microsoft 团队中添加个人聊天、群组聊天和频道的 bot
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。 聊天机器人允许用户在 Microsoft Teams 中通过聊天对话与云服务（例如，任务管理、计划和轮询）交互。 团队的 bot 基于[Microsoft Bot 框架](https://go.microsoft.com/fwlink/?linkid=854370)构建。 可轻松为团队启用使用此框架开发的 bot。 有关详细信息，请参阅[为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)。

当前，团队在团队中支持个人聊天、群组聊天和频道中的 bot。 管理员可以控制在 Office 365 租户中是允许还是禁止使用聊天机器人。<span id="_T-Bot" class="anchor"></span>

可在团队内利用社区开发的 bot。 必须在租户级别启用 bot 功能和上载自定义应用（也称为旁加载）的功能，才能使自定义机器人工作。 可以在个人聊天、群组聊天和频道中使用机器人。 对于频道，团队所有者或成员可以添加聊天机器人。

有关详细信息，请参阅[应用和服务](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)。

> [!IMPORTANT]
> 对于除测试用途之外的任何内容，建议不要通过 GUID 添加 bot。 这样做会严重限制机器人的功能。 应将生产使用中的 bot 作为应用的一部分添加到团队。 请参阅[创建 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)和[测试和调试 Microsoft 团队 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>为 Microsoft Teams 创建自定义聊天机器人
--------------------------------------

你可以使用 Microsoft Bot Framework 轻松创建要集成到你的 LOB 应用中的聊天机器人。 请参阅[创建和测试 Microsoft 团队的 bot bot](https://go.microsoft.com/fwlink/?linkid=854371)指南，了解如何开发和发布自己的 bot。

创建聊天机器人并向 Bot Framework 注册该聊天机器人时，可以选择是否发布该聊天机器人。 如果不发布，则聊天机器人保持专用状态。 你还可以要求你的用户先登录才能使用聊天机器人。 要求登录可确保在即使聊天机器人的应用 ID 已被其他人获知的情况下，仅贵组织的员工可以访问聊天机器人。 请参阅 GitHub 上的 [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)，获取有关如何使用聊天机器人按照你的 Active Directory 对用户进行身份验证的代码示例。

可以在将聊天机器人部署到你的 Teams 中之前，先使用 [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) 对其进行测试。

<a name="upload-your-bot-for-personal-chat"></a>上载个人聊天机器人
---------------------------------------

1. 创建你的 bot 后，请转到你开发的 bot 的**应用程序设置**，然后在 "**应用设置**" 下复制**MicrosoftAppId**设置的值。![Bot 的 "应用程序设置" 页面的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  在 "团队" 中的 "**聊天**" 窗格上，选择 "**添加聊天" 图标**。 在 "**收件人**" 中，粘贴你的 Bot 的**Microsoft 应用 ID**。 ![突出显示了 Microsoft 应用 ID 的聊天窗格的屏幕截图](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. 应用 ID 将解析为你的**bot 名称，** 然后你可以开始与该 bot 聊天对话。

<a name="upload-your-bot-for-group-chats-or-channels"></a>为群组聊天或频道上载机器人
-----------------------------------

如果你想要与同事共享你的机器人，请按以下方法将其添加到组聊天或不同团队的频道：

1. [为你的 bot 创建应用包](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)后，打开团队并浏览到要在其中上载机器人的团队。
2. 向团队添加**[应用程序 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** 和应用。
3. 在应用程序 Studio 中，选择 "**清单编辑器**" 选项卡。 !["清单编辑器" 选项卡的屏幕截图。](media/Adding_Bot_To_Teams.png)
4. 要在 "功能" 中添加你的机器人，请选择机器人，然后选择添加现有机器人。 然后，选择现有机器人或输入现有机器人的 Id。
![显示选择已创建的 bot。](media/Select_Existing_Bot.png)
5. 通过浏览找到应用包的位置，将其选中，然后单击 "**打开**"。
6. 选择你的 bot 的名称。 （不要忘记选中 "范围" 部分下的 "**群组聊天**或**团队**" 复选框）。
7. 选择 "**测试和分发**"。
8. 选择要将你的 bot 连接到的群组聊天或团队。

    你的 bot 将在团队中的群组聊天或团队中可用。
