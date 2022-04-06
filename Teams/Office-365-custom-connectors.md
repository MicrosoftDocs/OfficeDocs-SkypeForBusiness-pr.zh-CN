---
title: 使用Microsoft 365连接器和自定义连接器
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.openlocfilehash: 7fef0b28d9663cdb472f4daf79076c2d4eefcd66
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64642976"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft 365 中使用 Microsoft Teams 和自定义连接器

为了让团队保持更新，连接器将常用内容和服务更新直接传送至Teams频道。 使用连接器，Teams用户可以从常用服务（如 Trello、奇妙清单、GitHub 和 Azure DevOps Services）接收更新。 更新将直接发布在团队的聊天流中。

Microsoft 365连接器同时用于Microsoft Teams组Microsoft 365组，使所有成员能够更轻松地保持同步并快速接收相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。 但值得注意的是，禁用团队所依赖的 Microsoft 365 组的连接器也禁用了为该团队创建连接器的能力。

如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到热门云服务，并通知所有团队成员该服务的活动。 在最初设置连接器的成员离开后，连接器将继续工作。 具有添加或删除权限的任何团队成员都可以修改其他成员设置的连接器。

> [!NOTE]
> 在政府云环境环境中，连接器Community (GCC) 禁用。 若要启用这些参数，请通过 `ConnectorsEnabled` `$true` `SetOrganizationConfig` cmdlet 将 或 `ConnectorsEnabledForTeams` 参数设置为 。 连接 [PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)

## <a name="add-a-connector-to-a-channel"></a>将连接器添加到通道

目前，可以使用桌面和 Web 客户端Microsoft Teams连接器。 但是，可以在所有客户端（包括移动客户端）中查看这些连接器 **发布** 的信息。

1. 若要向通道添加连接线，请单击 ( **...)** 的省略号，在通道名称的右侧单击"连接器 **"**。

    > [!div class="mx-imgBorder"]
    > !["连接Teams"选项的"连接线"界面的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 可以从各种可用的连接器中选择，然后单击"添加 **"**。

    > [!div class="mx-imgBorder"]
    > ![显示可用连接器的"连接器"对话框的屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填充选定连接器的所需信息，然后单击 **“保存”**。 每个连接器都需要一组不同的信息才能正常运行，有些连接器可能会要求你使用连接器配置页面上提供的链接登录服务。

    > [!div class="mx-imgBorder"]
    > ![RSS 连接器的配置页面屏幕截图。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 连接器提供的数据会自动发布到频道。

    > [!div class="mx-imgBorder"]
    > ![Teams 界面屏幕截图，显示一个频道中的一个对话。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete --->

> [!IMPORTANT]
> **连接器 URL 更新通知**
>
> 这些Teams连接器正在转换到新的 URL，以增强安全性。 在此转换过程中，将收到某些通知，将配置的连接器更新为使用新 URL。 强烈建议立即更新连接器，以防止连接器服务发生任何中断。 需要执行以下步骤来更新 URL：
>
> 1. 在连接器配置页中，需要更新的连接的"管理"按钮下会显示"需要注意"消息。
> !["需要注意"消息的屏幕截图。](media/Teams_Attention_Required_message.png)
> 2. 对于传入的 Webhook 连接器，用户只需选择"更新 **URL** "，然后使用新生成的 Webhook URL 即可重新创建连接。
> !["更新 URL"按钮的屏幕截图。](media/Teams_update_URL_button.png)
> 3. 对于其他连接器类型，用户需要删除连接器并重新创建连接器配置。
> 4. 成功更新 URL 后，会看到一条消息"URL 是最新的"。
> !["URL 是最新的"消息的屏幕截图。](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>另请参阅

* [生成自定义连接器和 Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
