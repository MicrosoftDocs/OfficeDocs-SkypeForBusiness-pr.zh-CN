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
ms.openlocfilehash: e704dd6a9a796be4f9e361972cd2e6b38e48ce51
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582469"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="8f9e7-103">在 Microsoft 团队中使用 Microsoft 365 和自定义连接线</span><span class="sxs-lookup"><span data-stu-id="8f9e7-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="8f9e7-104">连接器将经常使用的内容和服务更新直接提供给频道，从而使你的团队保持最新。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="8f9e7-105">通过连接器，你的 Microsoft 团队用户可以从其团队中的聊天流内的受欢迎的服务（如 Twitter、Trello、奇妙清单、GitHub 和 Azure DevOps 服务）中接收更新。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="8f9e7-106">如果团队权限允许，团队的任何成员都可以将其团队与常用云服务连接起来，并且所有团队成员都将收到来自该服务的活动的通知。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="8f9e7-107">即使最初设置连接器的成员已离开，连接器仍可继续运行。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="8f9e7-108">具有 add\remove 权限的任何团队成员都可以修改其他成员的连接器设置。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="8f9e7-109">Microsoft 365 连接器可与 Microsoft 团队和 Microsoft 365 组一起使用，使所有成员能够更轻松地保持同步和快速接收相关信息。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="8f9e7-110">Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="8f9e7-111">但值得注意的是，禁用团队依赖的 Microsoft 365 组的连接器将禁用为该团队创建连接器的功能。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="8f9e7-112">向通道添加连接线</span><span class="sxs-lookup"><span data-stu-id="8f9e7-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="8f9e7-113">当前，你可以使用 Microsoft 团队桌面和 web 客户端添加连接器。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="8f9e7-114">但是，可以在包括手机在内的**所有客户端**中查看由这些连接器发布的信息。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="8f9e7-115">若要将连接线添加到通道，请单击频道名称右侧的**省略号 " ( ... ) "** ，然后单击 "**连接线**"。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![选择了 "连接线" 选项的 "团队" 界面的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="8f9e7-117">您可以从各种可用的连接线中进行选择，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    !["连接线" 对话框的屏幕截图，显示可用连接线。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="8f9e7-119">填充选定连接器的所需信息，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="8f9e7-120">每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="8f9e7-122">连接器提供的数据会自动发布到频道。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="8f9e7-124">开发自定义连接器</span><span class="sxs-lookup"><span data-stu-id="8f9e7-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="8f9e7-125">您还可以构建自定义连接器以及传入和传出 webhooks。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="8f9e7-126">有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。</span><span class="sxs-lookup"><span data-stu-id="8f9e7-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
