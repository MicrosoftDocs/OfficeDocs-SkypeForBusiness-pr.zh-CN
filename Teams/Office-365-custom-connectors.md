---
title: 使用Microsoft 365连接器和自定义连接器
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
description: 连接器可将内容和更新从你经常使用的服务直接传递到频道中，从而使你的团队能够获得最新内容。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77b1c99847ca35de51af5e062593a29c18e98999
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855791"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="ce6a1-103">在 Microsoft 365 中使用 Microsoft Teams 和自定义连接器</span><span class="sxs-lookup"><span data-stu-id="ce6a1-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="ce6a1-104">连接器将常用内容和服务更新直接交付到频道，使团队保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="ce6a1-105">使用连接器，Microsoft Teams用户可以在其团队的聊天流中接收来自常用服务（如 Trello、奇妙清单、GitHub 和 Azure DevOps Services）的更新。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="ce6a1-106">如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到热门云服务，并通知所有团队成员该服务的活动。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="ce6a1-107">即使最初设置连接器的成员已离开，连接器仍将正常运行。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="ce6a1-108">任何有权添加\删除的团队成员都可以修改其他成员设置的连接器。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="ce6a1-109">Microsoft 365连接器可以与 Microsoft Teams Microsoft 365 组一起使用，使所有成员可以更轻松地保持同步并快速接收相关信息。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members to stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="ce6a1-110">Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="ce6a1-111">但值得注意的是，禁用团队所依赖的 Microsoft 365 组的连接器也会禁用为该团队创建连接器的能力。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="ce6a1-112">默认情况下，连接器在 GCC禁用。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-112">Connectors are disabled by default in GCC environments.</span></span> <span data-ttu-id="ce6a1-113">如果需要启用它们，请设置 ConnectorsEnabled 或 ConnectorsEnabledForTeams 参数$true [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span> <span data-ttu-id="ce6a1-114">以前需要连接到[PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-114">You previously need to [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="ce6a1-115">在政府云环境环境中，连接器Community (GCC) 禁用。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-115">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="ce6a1-116">如果需要启用它们，请设置 ConnectorsEnabled 或 ConnectorsEnabledForTeams 参数$true [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-116">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="ce6a1-117">以前需要连接到[PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-117">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="ce6a1-118">将连接器添加到通道</span><span class="sxs-lookup"><span data-stu-id="ce6a1-118">Add a connector to a channel</span></span>

<span data-ttu-id="ce6a1-119">目前，可以使用桌面和 Web 客户端Microsoft Teams连接器。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-119">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="ce6a1-120">但是，可以在所有客户端（包括移动客户端）中查看这些连接器 **发布** 的信息。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-120">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="ce6a1-121">若要将连接器添加到通道，请单击 **(...)** 的省略号，在通道名称的右侧，然后单击"**连接器"。**</span><span class="sxs-lookup"><span data-stu-id="ce6a1-121">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ce6a1-122">!["连接Teams"选项的"连接线"界面的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-122">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="ce6a1-123">可以从各种可用的连接器中选择，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ce6a1-123">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ce6a1-124">![显示可用连接器的"连接器"对话框的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-124">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="ce6a1-125">填充选定连接器的所需信息，然后单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-125">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="ce6a1-126">每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-126">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ce6a1-127">![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-127">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="ce6a1-128">连接器提供的数据会自动发布到频道。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-128">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ce6a1-129">![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-129">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="ce6a1-130">**连接器 URL 更新通知**</span><span class="sxs-lookup"><span data-stu-id="ce6a1-130">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="ce6a1-131">连接器Teams转换到新的 URL 以增强安全性。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-131">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="ce6a1-132">在此转换过程中，将收到某些通知，将配置的连接器更新为使用新 URL。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-132">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="ce6a1-133">强烈建议立即更新连接器，以防止连接器服务发生任何中断。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-133">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="ce6a1-134">需要执行以下步骤来更新 URL：</span><span class="sxs-lookup"><span data-stu-id="ce6a1-134">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="ce6a1-135">在连接器配置页中，需要更新的连接的"管理"按钮下会显示"需要注意"消息。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-135">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="ce6a1-136">!["需要注意"消息的屏幕截图。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-136">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="ce6a1-137">对于传入的 Webhook 连接器，用户只需选择"更新 **URL"，** 然后使用新生成的 Webhook URL 即可重新创建连接。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-137">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="ce6a1-138">!["更新 URL"按钮的屏幕截图。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-138">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="ce6a1-139">对于其他连接器类型，用户需要删除连接器并重新创建连接器配置。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-139">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="ce6a1-140">成功更新 URL 后，会看到一条消息"URL 是最新的"。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-140">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="ce6a1-141">!["URL 是最新的"消息的屏幕截图。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="ce6a1-141">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="ce6a1-142">开发自定义连接器</span><span class="sxs-lookup"><span data-stu-id="ce6a1-142">Develop custom connectors</span></span>


<span data-ttu-id="ce6a1-143">还可以生成自定义连接器，以及传入和传出 Webhook。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-143">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="ce6a1-144">有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)”。</span><span class="sxs-lookup"><span data-stu-id="ce6a1-144">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
