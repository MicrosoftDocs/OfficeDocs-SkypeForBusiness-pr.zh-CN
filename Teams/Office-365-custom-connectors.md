---
title: 使用 Microsoft 365 和自定义连接器
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 连接器通过将你常用的服务中的内容和更新传输到频道，使你的团队持续获得最新信息。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076414"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft Teams 中使用 Microsoft 365 和自定义连接器
=======================================================

连接器将常用内容和服务更新直接交付到频道中，让团队保持最新状态。 使用连接器，Microsoft Teams 用户可以在其团队的聊天流中接收来自常用服务（如 Trello、Wunderlist、GitHub 和 Azure DevOps Services）的更新。

如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到常用云服务，并且所有团队成员都会收到该服务的活动通知。 即使最初设置连接器的成员已离开，连接器仍将正常运行。 任何有权添加\删除的团队成员都可以修改其他成员设置的连接器。

Microsoft 365 连接器可以与 Microsoft Teams 和 Microsoft 365 组一起使用，使所有成员能够更轻松地保持同步并快速接收相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。 但值得注意的是，禁用团队所依赖的 Microsoft 365 组的连接器也会禁用为该团队创建连接器的能力。

<a name="add-a-connector-to-a-channel"></a>将连接器添加到通道
----------------------------

目前，可以使用 Microsoft Teams 桌面和 Web 客户端添加连接器。 但是，可以在所有客户端（包括移动客户端）中查看这些连接器 **发布** 的信息。

1. 若要向通道添加连接线，请单击 **(...)** 的省略号，然后单击"连接 **线"。**

    > [!div class="mx-imgBorder"]
    > ![Teams 界面的屏幕截图，其中已选中"连接器"选项。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 可以从各种可用的连接器中选择，然后单击"添加 **"。**

    > [!div class="mx-imgBorder"]
    > ![显示可用连接器的"连接器"对话框的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填充选定连接器的所需信息，然后单击 **“保存”**。 每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。

    > [!div class="mx-imgBorder"]
    > ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 连接器提供的数据会自动发布到频道。

    > [!div class="mx-imgBorder"]
    > ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **连接器 URL 更新通知**
>
> Teams 连接器正在过渡到新的 URL 以增强安全性。 在此转换过程中，将收到某些通知，将配置的连接器更新为使用新 URL。 强烈建议立即更新连接器，以防止对连接器服务造成任何中断。 需要执行以下步骤来更新 URL：
> 1. 在连接器配置页中，需要更新的连接的"管理"按钮下会显示"需要注意"消息。
> !["需要注意"消息的屏幕截图。](media/Teams_Attention_Required_message.png)
> 2. 对于传入的 Webhook 连接器，用户只需选择更新 **URL，** 然后使用新生成的 Webhook URL 即可重新创建连接。
> !["更新 URL"按钮的屏幕截图。](media/Teams_update_URL_button.png)
> 3. 对于其他连接器类型，用户需要删除连接器并重新创建连接器配置。
> 4. 成功更新 URL 后，会看到一条消息"URL 为最新"。
> !["URL 为最新"消息的屏幕截图。](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>开发自定义连接器
----------------------------

还可以生成自定义连接器，以及传入和传出 Webhook。 有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。
