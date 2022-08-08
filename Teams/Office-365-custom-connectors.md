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
description: 了解连接器如何通过经常将内容和更新直接传送到你所使用的 Teams 频道来保持团队更新。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9bfc425fbabc5270a3b24cfa2248a9ee2eb7b833
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267607"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理 Microsoft 365 和自定义连接器

为了使团队保持更新，连接器会将常用内容和服务更新直接传送到 Teams 频道。 通过使用连接器，你的 Teams 用户可以接收来自常用服务（例如 Trello、奇妙清单、GitHub 和 Azure DevOps 服务）的更新。 更新将直接发布到其团队的聊天流中。

Microsoft 365 连接器会同时用于 Microsoft Teams 和 Microsoft 365 组。 它们使所有成员都能够轻松保持同步并快速接收相关信息。 可以在 Microsoft Teams 和 Microsoft Exchange 中使用相同的连接器。 但是，如果禁用为 Microsoft 365 组配置的任何连接器，它还会禁用 Microsoft 365 组创建连接器的功能。

如果团队权限允许，团队的任何成员都可以使用连接器将其团队连接到常用云服务，并且所有团队成员都会收到来自该服务的活动通知。 最初设置连接器的成员离开后，连接器将继续工作。 具有添加或删除权限的任何团队成员都可以修改其他成员设置的连接器。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中启用或禁用连接器

The Exchange Online PowerShell V2 模块使用新式身份验证并使用多重身份验证 (MFA) 连接到 Microsoft 365 中所有与 Exchange 相关 PowerShell 环境。 管理员可以使用 Exchange Online PowerShell 禁用整个租户或特定组邮箱的连接器，从而影响该租户或邮箱中的所有用户。 无法对少数特定用户禁用。 此外，默认情况下，政府社区云 (GCC 租户) 禁用连接器。

> [!NOTE]
> 默认情况下，政府云社区 (GCC) 环境中禁用连接器。 若要启用这些参数，请将 `ConnectorsEnabled` 或 `ConnectorsEnabledForTeams` 参数设置为 `$true` 使用 `SetOrganizationConfig` .cmdlet。 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)。

租户设置将替代组设置。 例如，如果管理员为组启用连接器并对租户禁用连接器，则会禁用该组的连接器。 要在 Teams 中启用连接器，请使用新式身份验证（无论是否使用 MFA）[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

若要启用或禁用连接器，请在 Exchange Online PowerShell 中执行以下命令：

* 要禁用租户的连接器：`Set-OrganizationConfig -ConnectorsEnabled:$false`。
* 要禁用租户的可操作消息：`Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`。
* 若要为 Teams 启用连接器，请执行以下命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

有关 PowerShell 模块交换的详细信息，请参阅 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 要启用或禁用 Microsoft Outlook 连接器，[将应用连接到 Outlook 中的组](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

## <a name="publish-connectors-for-your-organization"></a>为组织发布连接器

若要使自定义连接器可供组织的用户使用，请将自定义连接器应用上传到组织的应用目录。 组织内的最终用户可以在团队中安装、配置和使用连接器。

> [!IMPORTANT]
> 自定义连接器在政府社区云 (GCC)、政府社区云-High (GCCH) 和国防部 (DOD) 环境中不可用。

若要在团队或频道中使用连接器，请从频道右上角打开“更多选项”菜单。 从菜单中选择“**连接器** ”，然后找到或搜索所需的连接器。 如有必要，请配置所选连接器。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="从频道右上角的“更多”选项将连接器添加到 Teams 中的频道。":::

## <a name="update-url-of-a-connector"></a>更新连接器的 URL

Teams 连接器正在转换为新的 URL 以增强安全性。 在转换期间，你将收到更新配置的连接器的通知。 尽早更新连接器，以防止对连接器服务造成任何中断。 若要更新连接器，请执行以下承租人：

1. 在连接器配置页面中，检查配置的连接器旁边是否有“**需要注意**”消息。

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="“需要注意”消息的屏幕截图。":::

1. 若要重新创建传入 Webhook 连接器的连接，请选择“**更新 URL**”并使用生成的 Webhook URL。

   :::image type="content" source="media/teams-update-url-option.png" alt-text="“更新 URL”按钮的屏幕截图。":::

1. 对于其他连接器类型，请删除连接器并重新创建连接器配置。 将显示“**URL 是最新**”消息。

   :::image type="content" source="media/teams-url-updated.png" alt-text="“URL 是最新”消息的屏幕截图。":::

## <a name="related-articles"></a>相关文章

* [自定义连接器和 Webhook 概述](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [创建 Office 365 连接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
