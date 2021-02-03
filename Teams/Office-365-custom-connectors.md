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
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="48e78-103">在 Microsoft Teams 中使用 Microsoft 365 和自定义连接器</span><span class="sxs-lookup"><span data-stu-id="48e78-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="48e78-104">连接器将常用内容和服务更新直接交付到频道中，让团队保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="48e78-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="48e78-105">使用连接器，Microsoft Teams 用户可以在其团队的聊天流中接收来自常用服务（如 Trello、Wunderlist、GitHub 和 Azure DevOps Services）的更新。</span><span class="sxs-lookup"><span data-stu-id="48e78-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="48e78-106">如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到常用云服务，并且所有团队成员都会收到该服务的活动通知。</span><span class="sxs-lookup"><span data-stu-id="48e78-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="48e78-107">即使最初设置连接器的成员已离开，连接器仍将正常运行。</span><span class="sxs-lookup"><span data-stu-id="48e78-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="48e78-108">任何有权添加\删除的团队成员都可以修改其他成员设置的连接器。</span><span class="sxs-lookup"><span data-stu-id="48e78-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="48e78-109">Microsoft 365 连接器可以与 Microsoft Teams 和 Microsoft 365 组一起使用，使所有成员能够更轻松地保持同步并快速接收相关信息。</span><span class="sxs-lookup"><span data-stu-id="48e78-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="48e78-110">Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。</span><span class="sxs-lookup"><span data-stu-id="48e78-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="48e78-111">但值得注意的是，禁用团队所依赖的 Microsoft 365 组的连接器也会禁用为该团队创建连接器的能力。</span><span class="sxs-lookup"><span data-stu-id="48e78-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="48e78-112">将连接器添加到通道</span><span class="sxs-lookup"><span data-stu-id="48e78-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="48e78-113">目前，可以使用 Microsoft Teams 桌面和 Web 客户端添加连接器。</span><span class="sxs-lookup"><span data-stu-id="48e78-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="48e78-114">但是，可以在所有客户端（包括移动客户端）中查看这些连接器 **发布** 的信息。</span><span class="sxs-lookup"><span data-stu-id="48e78-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="48e78-115">若要向通道添加连接线，请单击 **(...)** 的省略号，然后单击"连接 **线"。**</span><span class="sxs-lookup"><span data-stu-id="48e78-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="48e78-116">![Teams 界面的屏幕截图，其中已选中"连接器"选项。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="48e78-117">可以从各种可用的连接器中选择，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="48e78-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="48e78-118">![显示可用连接器的"连接器"对话框的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="48e78-119">填充选定连接器的所需信息，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="48e78-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="48e78-120">每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。</span><span class="sxs-lookup"><span data-stu-id="48e78-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="48e78-121">![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="48e78-122">连接器提供的数据会自动发布到频道。</span><span class="sxs-lookup"><span data-stu-id="48e78-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="48e78-123">![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="48e78-124">**连接器 URL 更新通知**</span><span class="sxs-lookup"><span data-stu-id="48e78-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="48e78-125">Teams 连接器正在过渡到新的 URL 以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="48e78-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="48e78-126">在此转换过程中，将收到某些通知，将配置的连接器更新为使用新 URL。</span><span class="sxs-lookup"><span data-stu-id="48e78-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="48e78-127">强烈建议立即更新连接器，以防止对连接器服务造成任何中断。</span><span class="sxs-lookup"><span data-stu-id="48e78-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="48e78-128">需要执行以下步骤来更新 URL：</span><span class="sxs-lookup"><span data-stu-id="48e78-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="48e78-129">在连接器配置页中，需要更新的连接的"管理"按钮下会显示"需要注意"消息。</span><span class="sxs-lookup"><span data-stu-id="48e78-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="48e78-130">!["需要注意"消息的屏幕截图。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="48e78-131">对于传入的 Webhook 连接器，用户只需选择更新 **URL，** 然后使用新生成的 Webhook URL 即可重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="48e78-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="48e78-132">!["更新 URL"按钮的屏幕截图。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="48e78-133">对于其他连接器类型，用户需要删除连接器并重新创建连接器配置。</span><span class="sxs-lookup"><span data-stu-id="48e78-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="48e78-134">成功更新 URL 后，会看到一条消息"URL 为最新"。</span><span class="sxs-lookup"><span data-stu-id="48e78-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="48e78-135">!["URL 为最新"消息的屏幕截图。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="48e78-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="48e78-136">开发自定义连接器</span><span class="sxs-lookup"><span data-stu-id="48e78-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="48e78-137">还可以生成自定义连接器，以及传入和传出 Webhook。</span><span class="sxs-lookup"><span data-stu-id="48e78-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="48e78-138">有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。</span><span class="sxs-lookup"><span data-stu-id="48e78-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
