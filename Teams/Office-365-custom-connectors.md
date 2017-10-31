---
title: "在 Microsoft Teams 中使用 Office 365 和自定义连接器 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "连接器通过将你常用的服务中的内容和更新传输到频道，使你的团队持续获得最新信息。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 08f2526686c894e44193fb53d51f9f59d6960279
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft Teams 中使用 Office 365 和自定义连接器
=======================================================

连接器通过将你常用的服务中的内容和更新传输到频道，使你的团队持续获得最新信息。 通过使用连接器，你的 Microsoft Teams 可以在其团队的聊天流中接收来自常用服务（例如 Twitter、Trello、Wunderlist、GitHub 和 VSTS）的更新。

团队的任何成员都可以通过连接器将其团队连接到常用云服务，所有团队成员都将收到来自该服务的活动通知。 如果从某个团队中删除某个用户，则由被删除用户添加到该团队的任何连接器都将停止工作。 安排的会议继续有效，因为它们在群组日历上。

Office 365 连接器可以与 Microsoft Teams 和 Office 365 组配合使用，这样，可以轻松地让所有成员保持同步并快速收到相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。

当前，可以使用 Microsoft Teams 桌面和 Web 客户端添加连接器。 但是，可以使用包括移动设备在内的**所有客户端**查看这些连接器发布的信息。

1.  要将连接器添加到频道，请单击频道名称右侧的**省略号 (…)**，然后单击**“连接器”**。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  用户可以从多个可用连接器中选择，然后单击**“添加”**。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  填充选定连接器的所需信息，然后单击**“保存”**。 每个连接器都需要不同的一组信息才能正确使用，有些连接器可能需要你使用连接器配置页面上提供的链接登录服务。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  连接器提供的数据会自动发布到频道。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>开发自定义连接器
-----------------------------

开发可以集成到你的业务线 (LOB) 应用中的自定义连接器非常容易。 你可以使用内置**传入 Webhook** 连接器为频道创建终结点，该连接器使用 HTTP Post 方法从任何应用中提取数据。

1.  像任何其他连接器一样添加**传入 Webhook**。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  要创建 Webhook，请指定**名称**、更新 Webhook 图片（如果需要），然后单击**“创建”**。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  向此频道推送数据的应用需要 Webhook 连接器 URL。 你创建 **Webhook** 时，系统创建**唯一的 URL**。 向你的开发人员提供此 URL，以便他们可以根据需要配置其应用以推送数据。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  外部应用向连接器推送数据时，将在频道对话列表中显示消息，这是名为**连接器卡**消息的特殊消息。

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

开发人员可以通过向 Microsoft Team 的 Webhook 地址（向导提供的终结点的唯一 URL）发送包含简单 JSON 有效负载的 HTTP 请求，来配置其应用以创建这些卡。 请你的开发人员参阅 Microsoft Developer Network 上的[开始使用适用于 Microsoft Teams 的 Office 365 连接器](https://go.microsoft.com/fwlink/?linkid=855783)，其中提供了详细的说明和连接器示例。 其他资源包括[在 Outlook 中将应用连接到你的组](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)和 [Office 开发人员中心 - Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784)。
