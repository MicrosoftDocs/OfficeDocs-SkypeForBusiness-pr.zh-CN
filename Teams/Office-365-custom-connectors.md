---
title: 管理Microsoft 365和自定义连接器
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
ms.openlocfilehash: 2dea5ee50d75ff8913bc88f2f3947d9f665cb4dd
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137013"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理Microsoft 365和自定义连接器

为了使团队保持更新，连接器会将常用的内容和服务更新直接传送到Teams通道。 使用连接器，Teams用户可以从热门服务（如 Trello、奇妙清单、GitHub 和Azure DevOps Services）接收更新。 更新将直接发布到其团队中的聊天流中。

Microsoft 365连接器用于Microsoft Teams组和Microsoft 365组，使所有成员能够更轻松地保持同步并快速接收相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。 但是，如果禁用为Microsoft 365组配置的任何连接器，也会禁用Microsoft 365组创建连接器的功能。

如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到常用云服务，并且所有团队成员都会收到来自该服务的活动通知。 最初设置连接器的成员离开后，连接器将继续工作。 任何有权添加或删除的团队成员都可以修改其他成员设置的连接器。

## <a name="enable-or-disable-connectors-in-teams"></a>在Teams中启用或禁用连接器

Exchange Online PowerShell V2 模块使用新式身份验证并使用多重身份验证（称为 MFA）连接到Microsoft 365中所有Exchange相关 PowerShell 环境。 管理员可以使用 Exchange Online PowerShell 禁用整个租户或特定组邮箱的连接器，从而影响该租户或邮箱中的所有用户。 无法对少数特定用户禁用。 此外，默认情况下，政府社区云（称为GCC租户）禁用连接器。

租户设置将替代组设置。 例如，如果管理员为组启用连接器并在租户上禁用连接器，则会禁用该组的连接器。 若要在 Teams 中启用连接器，请使用新式身份验证（无论是否使用 MFA）[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

若要启用或禁用连接器，请在 Exchange Online PowerShell 中执行以下命令：

* 若要禁用租户的连接器，请执行以下操作： `Set-OrganizationConfig -ConnectorsEnabled:$false`
* 若要禁用租户的可操作消息，请执行以下操作： `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`
* 若要为Teams启用连接器，请执行以下命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

有关 PowerShell 模块交换的详细信息，请参阅 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 若要启用或禁用Outlook连接器，请[将应用连接到Outlook中的组](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>为组织发布连接器

如果希望自定义连接器仅对组织中的用户可用，则可以将自定义连接器应用上传到组织的应用目录。 上传应用包后，最终用户可以从组织的应用目录安装连接器，并且可以在团队中配置和使用连接器。

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> 自定义连接器在 政府社区云 (GCC) 、GCC-High 和国防部 (DOD) 中不可用。

若要在团队或频道中使用连接器，请从频道右上角打开“更多选项”菜单。 从菜单中选择 **连接器** ，然后找到或搜索所需的连接器应用。 如果需要，请配置所选连接器。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="从通道右上角的“更多”选项将连接器添加到通道Teams。":::

## <a name="update-url-of-a-connector"></a>更新连接器的 URL

Teams连接器正在转换为新的 URL 以提高安全性。 在转换期间，你将收到更新配置的连接器的通知。 尽早更新连接器，以防止对连接器服务造成任何中断。 若要更新连接器，

1. 在连接器配置页中，检查配置的连接器旁边是否有 **“需要注意** ”消息。

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="“需要注意”消息的屏幕截图。":::

1. 若要重新创建传入 Webhook 连接器的连接，请选择 **“更新 URL** ”并使用生成的 Webhook URL。

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="“更新 URL”按钮的屏幕截图。":::

1. 对于其他连接器类型，请删除连接器并重新创建连接器配置。 **URL 显示最新** 消息。

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="URL 是最新消息的屏幕截图。":::

## <a name="see-also"></a>另请参阅

* [自定义连接器和 Webhook 概述](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [创建Office 365连接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
