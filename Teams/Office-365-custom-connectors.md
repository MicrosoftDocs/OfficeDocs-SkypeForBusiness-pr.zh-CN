---
title: 管理 Microsoft 365 和自定义连接器
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
description: 了解连接器如何通过经常将内容和更新直接传送到 Teams 频道以供你使用的服务来使团队保持更新。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb056cbee4dc1d56a6cd967d3f46c3f0680e9b73
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880226"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理 Microsoft 365 和自定义连接器

为了使团队保持更新，连接器会将常用的内容和服务更新直接传送到 Teams 频道。 使用连接器，Teams 用户可以从热门服务（如 Trello、奇妙清单、GitHub 和 Azure DevOps Services）接收更新。 更新将直接发布到其团队中的聊天流中。

Microsoft 365 连接器与 Microsoft Teams 和 Microsoft 365 组一起使用，使所有成员能够更轻松地保持同步并快速接收相关信息。 Microsoft Teams 和 Exchange 使用相同的连接器模型，这样，你可以在两个平台中使用相同的连接器。 但是，如果禁用为 Microsoft 365 组配置的任何连接器，也会禁用 Microsoft 365 组创建连接器的功能。

如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到常用云服务，并且所有团队成员都会收到来自该服务的活动通知。 最初设置连接器的成员离开后，连接器将继续工作。 任何有权添加或删除的团队成员都可以修改其他成员设置的连接器。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中启用或禁用连接器

Exchange Online PowerShell V2 模块使用新式身份验证并使用多重身份验证（称为 MFA）连接到 Microsoft 365 中所有与 Exchange 相关的 PowerShell 环境。 管理员可以使用 Exchange Online PowerShell 禁用整个租户或特定组邮箱的连接器，从而影响该租户或邮箱中的所有用户。 无法对少数特定用户禁用。 此外，默认情况下，政府社区云（称为 GCC 租户）禁用连接器。

租户设置将替代组设置。 例如，如果管理员为组启用连接器并在租户上禁用连接器，则会禁用该组的连接器。 若要在 Teams 中启用连接器，请使用采用或不使用 MFA 的新式身份验证[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

若要启用或禁用连接器，请在 Exchange Online PowerShell 中执行以下命令：

* 若要禁用租户的连接器，请执行以下操作： `Set-OrganizationConfig -ConnectorsEnabled:$false`
* 若要禁用租户的可操作消息，请执行以下操作： `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`
* 若要为 Teams 启用连接器，请执行以下命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

有关 PowerShell 模块交换的详细信息，请参阅 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 若要启用或禁用 Outlook 连接器，请 [将应用连接到 Microsoft Outlook 中的组](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

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
> 政府社区云 (GCC) 、政府社区Cloud-High (GCCH) 和国防部 (DOD) 中不提供自定义连接器。

若要在团队或频道中使用连接器，请从频道右上角打开“更多选项”菜单。 在菜单中，选择 **“连接器”** ，然后找到或搜索所需的连接器。 如有必要，请配置所选连接器。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="从通道右上角的“更多”选项将连接器添加到 Teams 中的频道。":::

## <a name="update-url-of-a-connector"></a>更新连接器的 URL

Teams 连接器正在转换为新的 URL 以增强安全性。 在转换期间，你将收到更新配置的连接器的通知。 尽早更新连接器，以防止对连接器服务造成任何中断。 若要更新连接器，

1. 在连接器配置页中，检查配置的连接器旁边是否有 **“需要注意** ”消息。

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="“需要注意”消息的屏幕截图。":::

1. 若要重新创建传入 Webhook 连接器的连接，请选择 **“更新 URL** ”并使用生成的 Webhook URL。

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="“更新 URL”按钮的屏幕截图。":::

1. 对于其他连接器类型，请删除连接器并重新创建连接器配置。 **URL 显示最新** 消息。

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="URL 是最新消息的屏幕截图。":::

## <a name="related-articles"></a>相关文章

* [自定义连接器和 Webhook 概述](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [创建Office 365连接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
