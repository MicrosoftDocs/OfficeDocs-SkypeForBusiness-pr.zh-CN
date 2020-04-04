---
title: 使用 Office 365 和自定义连接器
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6726507b0dd6c0ca0067bf19a3f9a2c37f727c53
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136502"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="4a892-103">在 Microsoft Teams 中使用 Office 365 和自定义连接器</span><span class="sxs-lookup"><span data-stu-id="4a892-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="4a892-104">连接器将经常使用的内容和服务更新直接提供给频道，从而使你的团队保持最新。</span><span class="sxs-lookup"><span data-stu-id="4a892-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="4a892-105">通过连接器，你的 Microsoft 团队用户可以从其团队中的聊天流内的受欢迎的服务（如 Twitter、Trello、奇妙清单、GitHub 和 Azure DevOps 服务）中接收更新。</span><span class="sxs-lookup"><span data-stu-id="4a892-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="4a892-106">如果团队权限允许，团队的任何成员都可以将其团队与常用云服务连接起来，并且所有团队成员都将收到来自该服务的活动的通知。</span><span class="sxs-lookup"><span data-stu-id="4a892-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="4a892-107">即使最初设置连接器的成员已离开，连接器仍可继续运行。</span><span class="sxs-lookup"><span data-stu-id="4a892-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="4a892-108">具有 add\remove 权限的任何团队成员都可以修改其他成员的连接器设置。</span><span class="sxs-lookup"><span data-stu-id="4a892-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="4a892-109">Office 365 连接器可以与 Microsoft Teams 和 Office 365 组配合使用，这样，可以更轻松地让所有成员保持同步并快速收到相关信息。</span><span class="sxs-lookup"><span data-stu-id="4a892-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="4a892-110">Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。</span><span class="sxs-lookup"><span data-stu-id="4a892-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="4a892-111">但值得注意的是，禁用团队所依赖的 Office 365 组的连接器将禁用为该团队创建连接器的功能。</span><span class="sxs-lookup"><span data-stu-id="4a892-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="4a892-112">向通道添加连接线</span><span class="sxs-lookup"><span data-stu-id="4a892-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="4a892-113">当前，你可以使用 Microsoft 团队桌面和 web 客户端添加连接器。</span><span class="sxs-lookup"><span data-stu-id="4a892-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="4a892-114">但是，可以在包括手机在内的**所有客户端**中查看由这些连接器发布的信息。</span><span class="sxs-lookup"><span data-stu-id="4a892-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="4a892-115">若要向通道添加连接线，请单击通道名称右侧的**省略号（...）** ，然后单击 "**连接线**"。</span><span class="sxs-lookup"><span data-stu-id="4a892-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![选择了 "连接线" 选项的 "团队" 界面的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="4a892-117">您可以从各种可用的连接线中进行选择，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="4a892-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    !["连接线" 对话框的屏幕截图，显示可用连接线。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="4a892-119">填充选定连接器的所需信息，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="4a892-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="4a892-120">每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。</span><span class="sxs-lookup"><span data-stu-id="4a892-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="4a892-122">连接器提供的数据会自动发布到频道。</span><span class="sxs-lookup"><span data-stu-id="4a892-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="4a892-124">开发自定义连接器</span><span class="sxs-lookup"><span data-stu-id="4a892-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="4a892-125">您还可以构建自定义连接器以及传入和传出 webhooks。</span><span class="sxs-lookup"><span data-stu-id="4a892-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="4a892-126">有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。</span><span class="sxs-lookup"><span data-stu-id="4a892-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
