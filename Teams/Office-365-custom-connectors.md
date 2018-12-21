---
title: 在 Microsoft Teams 中使用 Office 365 和自定义连接器
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: lucarras
search.appverid: MET150
description: 连接器通过将你常用的服务中的内容和更新传输到频道，使你的团队持续获得最新信息。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d8209b8652bb20b560606cfe4cc5cd34716853f
ms.sourcegitcommit: b67c2cb5ffd6d27cc9257c5e81ee1ea494ef8bd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "27382619"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="f0cd9-103">在 Microsoft Teams 中使用 Office 365 和自定义连接器</span><span class="sxs-lookup"><span data-stu-id="f0cd9-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="f0cd9-104">连接器通过将你常用的服务中的内容和更新传输到频道，使你的团队持续获得最新信息。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-104">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="f0cd9-105">通过使用连接器，你的 Microsoft Teams 用户可以在其团队的聊天流中接收来自常用服务（例如 Twitter、Trello、Wunderlist、GitHub 和 VSTS）的更新。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="f0cd9-106">工作组中的任何成员可以连接到使用连接器的常用云服务其工作组，如果团队权限允许，并且所有团队成员都通知的活动从该服务。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="f0cd9-107">连接器将继续在最初安装连接器已离开的成员后正常工作。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="f0cd9-108">添加/删除对具有权限的任何团队成员可以修改连接器设置其他成员。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="f0cd9-109">Office 365 连接器可以与 Microsoft Teams 和 Office 365 组配合使用，这样，可以更轻松地让所有成员保持同步并快速收到相关信息。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="f0cd9-110">Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="f0cd9-111">值得注意，禁用 Office 365 组团队所依赖的连接器将禁用创建连接器以及该团队的功能。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<span data-ttu-id="f0cd9-112">当前，可以使用 Microsoft Teams 桌面和 Web 客户端添加连接器。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-112">Currently, connectors can be added by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="f0cd9-113">但是，可以使用包括移动设备在内的**所有客户端**查看这些连接器发布的信息。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-113">However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="f0cd9-114">要将连接器添加到频道，请单击频道名称右侧的**省略号 (…)**，然后单击 **“连接器”**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-114">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![选择了一个频道名称并选择了“连接器”选项的 Teams 界面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="f0cd9-116">用户可以从多个可用连接器中选择，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-116">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![“连接器”对话框屏幕截图，显示可用于添加的连接器。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="f0cd9-118">填充选定连接器的所需信息，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-118">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="f0cd9-119">每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-119">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="f0cd9-121">连接器提供的数据会自动发布到频道。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-121">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="f0cd9-123">开发自定义连接器</span><span class="sxs-lookup"><span data-stu-id="f0cd9-123">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="f0cd9-124">开发可以集成到你的业务线 (LOB) 应用中的自定义连接器非常容易。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-124">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications.</span></span> <span data-ttu-id="f0cd9-125">你可以使用内置**传入 Webhook** 连接器为频道创建终结点，该连接器使用 HTTP Post 方法从任何应用中提取数据。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-125">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="f0cd9-126">像任何其他连接器一样添加**传入 Webhook**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-126">Add the **Incoming Webhook** like any other connector.</span></span>

    ![用于添加传入 Webhook 连接器的选项屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="f0cd9-128">要创建 Webhook，请指定**名称**、更新 Webhook 图片（如果需要），然后单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-128">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![<span data-ttu-id="f0cd9-129">传入 Webhook 连接器的配置页面屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-129">Screenshot of the configuration page for the Incoming Webhook connector.</span></span> ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="f0cd9-130">向此频道推送数据的应用需要 Webhook 连接器 URL。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-130">Applications that push data to this channel, require the Webhook connector URL.</span></span> <span data-ttu-id="f0cd9-131">你创建 **Webhook** 时，系统会创建**唯一的 URL**。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-131">A **unique URL** is created when you created the **Webhook**.</span></span> <span data-ttu-id="f0cd9-132">向你的开发人员提供此 URL，以便他们可以根据需要配置其应用以推送数据。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-132">Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![Webhook 的唯一 URL 屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="f0cd9-134">外部应用向连接器推送数据时，将在频道对话列表中显示消息，这是名为**连接器卡**消息的特殊消息。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-134">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Teams 界面屏幕截图，显示一条连接器卡消息。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="f0cd9-136">开发人员可以通过向 Microsoft Team 的 Webhook 地址（向导提供的终结点的唯一 URL）发送包含简单 JSON 有效负载的 HTTP 请求，来配置其应用以创建这些卡。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-136">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="f0cd9-137">请你的开发人员参阅 Microsoft Developer Network 上的[开始使用适用于 Microsoft Teams 的 Office 365 连接器](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)，其中提供了详细的说明和连接器示例。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-137">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, with detailed instructions and connector samples.</span></span> <span data-ttu-id="f0cd9-138">其他资源包括[在 Outlook 中将应用连接到你的组](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)和 [Office 开发人员中心 - Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784)。</span><span class="sxs-lookup"><span data-stu-id="f0cd9-138">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
