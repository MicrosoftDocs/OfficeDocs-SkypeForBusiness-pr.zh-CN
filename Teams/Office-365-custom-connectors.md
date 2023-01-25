---
title: 管理 Microsoft 365 连接器和自定义连接器
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解连接器如何通过经常将内容和更新直接传送到你所使用的服务的 Teams 频道来使团队保持最新状态。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983680"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>管理 Microsoft 365 连接器和自定义连接器

Microsoft Teams 中的连接器将内容和服务更新直接从第三方服务传送到 Teams 频道。 使用连接器，用户可以从 Trello、奇妙清单、GitHub 和 Azure DevOps Services 等常用服务接收更新。 更新将直接发布到聊天流中。 这样，所有成员都可以轻松保持同步并快速接收相关信息。

Microsoft 365 连接器与 Teams 和 Microsoft 365 组一起使用。 可以在 Teams 和 Microsoft Exchange 中使用相同的连接器。 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

如果团队权限允许，团队的任何成员都可以在团队中添加连接器，并且所有团队成员都会收到来自该服务的活动的通知。 具有添加或删除权限的任何团队成员都可以修改其他成员设置的连接器。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中启用或禁用连接器

Exchange Online PowerShell v2 模块使用新式身份验证，并与多重身份验证 (MFA) 配合使用，以连接到 Microsoft 365 中所有与 Exchange 相关的 PowerShell 环境。 管理员可以使用 Exchange Online PowerShell 禁用整个租户或特定组邮箱的连接器，从而影响该租户或邮箱中的所有用户。 无法对少数特定用户禁用。

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

## <a name="considerations-when-using-connectors-in-teams"></a>在 Teams 中使用连接器时的注意事项

* 默认情况下，政府云社区 (GCC) 环境中禁用连接器。 若要启用这些参数，请将 `ConnectorsEnabled` 或 `ConnectorsEnabledForTeams` 参数设置为 `$true` 使用 `SetOrganizationConfig` .cmdlet。 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)。

* 如果向团队添加连接器的用户离开团队，连接器将继续工作。

* 以下连接器从 2023 年 1 月起不可用：

  * 哈哈
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * 青苗
  * BITBUCKET
  * BITBUCKETSERVER
  * 伙计
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * 槽
  * HEROKU
  * HONEYBADGER
  * 对讲机
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * 信号
  * 哨兵
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * 颠覆
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>相关文章

* [自定义连接器和 Webhook 概述](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [如何创建Office 365连接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
