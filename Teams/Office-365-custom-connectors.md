---
title: 在 Microsoft Teams 中使用 Office 365 和自定义连接器
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: cc65939048fd8e54bd122a4dc52d2a611b8453cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834372"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft Teams 中使用 Office 365 和自定义连接器
=======================================================

连接器将经常使用的内容和服务更新直接提供给频道，从而使你的团队保持最新。 通过连接器，你的 Microsoft 团队用户可以从其团队中的聊天流内的受欢迎的服务（如 Twitter、Trello、奇妙清单、GitHub 和 Azure DevOps 服务）中接收更新。

如果团队权限允许，团队的任何成员都可以将其团队与常用云服务连接起来，并且所有团队成员都将收到来自该服务的活动的通知。 即使最初设置连接器的成员已离开，连接器仍可继续运行。 具有 add\remove 权限的任何团队成员都可以修改其他成员的连接器设置。

Office 365 连接器可以与 Microsoft Teams 和 Office 365 组配合使用，这样，可以更轻松地让所有成员保持同步并快速收到相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。 但值得注意的是，禁用团队所依赖的 Office 365 组的连接器将禁用为该团队创建连接器的功能。

<a name="add-a-connector-to-a-channel"></a>向通道添加连接线
----------------------------

当前，你可以使用 Microsoft 团队桌面和 web 客户端添加连接器。 但是，可以在包括手机在内的**所有客户端**中查看由这些连接器发布的信息。

1. 若要向通道添加连接线，请单击通道名称右侧的**省略号（...）** ，然后单击 "**连接线**"。

    ![选择了 "连接线" 选项的 "团队" 界面的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 您可以从各种可用的连接线中进行选择，然后单击 "**添加**"。

    !["连接线" 对话框的屏幕截图，显示可用连接线。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填充选定连接器的所需信息，然后单击 **“保存”**。 每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。

    ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 连接器提供的数据会自动发布到频道。

    ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>开发自定义连接器
----------------------------

您还可以构建自定义连接器以及传入和传出 webhooks。 有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。
