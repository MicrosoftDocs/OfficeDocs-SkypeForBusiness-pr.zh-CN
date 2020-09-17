---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940630"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>为 IT 管理员升级到团队时的 PSTN 注意事项 &mdash;

本文介绍升级到团队时 (PSTN) 注意事项的公共交换电话网络。 本文是针对 IT 管理员介绍升级概念和实现的第六个。  

- [概述](upgrade-to-teams-on-prem-overview.md)
- [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [用于管理升级的工具](upgrade-to-teams-on-prem-tools.md)
- [具有 Skype for business 内部部署的组织的其他注意事项](upgrade-to-teams-on-prem-considerations.md)
- [实现升级](upgrade-to-teams-on-prem-implement.md)
- **公共交换电话网络 (PSTN) 注意事项** (本文) 

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > 仅当用户处于 TeamsOnly 模式时，才支持将电话系统与团队配合使用。  如果用户处于 "孤岛" 模式，则只有 Skype for Business 才支持电话系统。 


## <a name="pstn-calling-scenarios"></a>PSTN 呼叫方案

移动到 TeamsOnly 模式时，有四种可能的通话方案：

- [Skype For Business Online 中使用 Microsoft 通话计划的用户](#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 通话计划。

- [Skype for Business Online 中的用户，](#from-skype-for-business-online-with-on-premises-voice) 通过 skype for business 本地或云连接器版本使用本地语音功能。 用户对团队的升级需要与用户迁移以直接路由，以确保 TeamsOnly 用户具有 PSTN 功能。

- [使用企业语音的 Skype For business online 中的用户](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，这些用户将移动到联机状态并保持本地 PSTN 连接。  将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。 

- [使用企业语音的 Skype For business online 中的用户](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，这些用户将移动到联机并使用 Microsoft 通话计划。  将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。

本文仅提供高级别概述。 有关详细信息，请参阅 [电话系统直接路由](direct-routing-landing-page.md) 和 [通话计划](calling-plan-landing-page.md)。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>通过 Microsoft 通话计划从 Skype for Business Online 

这是涉及语音的最简单的升级方案。 

1. 请确保已为用户分配了团队许可证。 默认情况下，当你分配 Microsoft 365 或 Office 365 许可证时，团队已启用，因此除非你以前禁用了团队许可证，否则不需要执行任何操作。

2.  如果用户已有一个包含电话号码的 Microsoft 通话计划，则唯一所需的更改是在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。  在分配 TeamsOnly 模式之前，传入的 PSTN 呼叫将位于用户的 Skype for Business 客户端中。 升级到 TeamsOnly 模式后，传入的 PSTN 呼叫将位于用户的团队客户端。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>通过 Skype for Business Online 与本地语音

在此方案中，用户已在 Skype for business Online 中，但其 PSTN 连接在本地，使用混合模式或云连接器版本中的 Skype for business 服务器。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着可以直接路由，其中 PSTN 中继通过本地会话边界控制器 (SBC) 直接连接到云中的直接路由服务。

下面列出了基本步骤。  步骤1-4 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤5之前完成。

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保通过显式分配任何现有的 grandfather 用户，如前面所述。

2. 为直接路由配置租户。 请参阅 [直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，请为这些用户配置各种团队策略 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 模式之前执行此操作。

4. 准备选择要进行语音迁移的用户： 
   - 如有必要，请分配 "团队" 许可证。  假设用户在本地语音的 Skype for business Online 中已起作用，则用户已经拥有 Skype for business 计划2和 Microsoft Phone 系统。 让这些计划保持启用状态，包括 Skype for Business Online 计划2许可证。  
   - 分配所需的 OnlineVoiceRoutingPolicy。 

5. 升级用户：这些步骤应协调。 

   - 在 Microsoft 365 或 Office 365 中，将用户升级到 TeamsOnly 模式 (授予 CsTeamsUpgradePolicy) 。
   - 在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>从具有企业语音的本地 Skype for Business 服务器到直接路由

在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着为直接路由，然后将用户移动到云。 
 
下面列出了基本步骤。  步骤1-5 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤6之前完成。

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。

2. 如果尚未执行此操作，请 [为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 为直接路由配置租户。 请参阅 [直接路由的每租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，为这些用户配置各种团队策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。

5. 如有必要，请分配 Microsoft 365 或 Office 365 许可证。  用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。 如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。  

6. 升级用户：这些步骤应协调。 

   - 使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。 如果你使用的 Skype for Business Server 版本不支持-MoveToTeams 开关，请先运行 Move Move-csuser，然后在租户远程 PowerShell 或团队管理控制台中分配 TeamsOnly 模式。

   - 在 SBC 上，将语音路由配置为通过将呼叫发送到直接路由（而不是本地中介服务器）来启用传入呼叫。 

   - 在 Microsoft 365 或 Office 365 中：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>从具有企业语音的本地 Skype for Business 服务器到 Microsoft 通话计划

在此方案中，用户仍托管在本地 Skype for business 中，并且其 PSTN 连接也位于本地。 通过 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着将用户移动到云，并将其编号从旧运营商移植到 Microsoft 通话计划，或为用户分配一个新号码。 

下面列出了基本步骤。步骤1-5 按建议的顺序列出，但可以按任意顺序完成。 关键是，所有这些都应在步骤6之前完成。 

1. 如果你要将租户范围内的策略设置为 Skype for Business 模式之一，请确保将现有的 grandfather 用户显式分配给其孤岛模式（如前面所述）。 

2. 如果尚未执行此操作，请 [为 Skype for business 混合配置组织](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如果需要，请为这些用户配置各种团队策略 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 可以随时执行此操作，但如果你希望确保用户在升级时具有正确的配置，最好在将用户升级到 TeamsOnly 之前执行此操作。 

4. 如有必要，请分配 Microsoft 365 或 Office 365 许可证。用户应同时拥有团队和 Skype for business Online 计划2以及电话系统。 如果 "Skype for Business Online 计划 2" 已禁用，请重新启用它。  

5. 为您的用户获取电话号码。  (有关详细信息，请参阅 [管理你的组织的电话号码](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。 ) 

   - 如果您将重新使用这些号码，请向您的运营商提交一个移植请求。  
   - 或者，您可以直接从 Microsoft 获取新号码。 

6. 升级用户，如果需要，请分配 LineUri。 使用本地 Skype for Business 工具，通过-MoveToTeams 开关运行 Move-csuser。  

    - 如果你要将数字移植到 Microsoft，你应该将此操作的计时协调为在端口出现时发生。 

    - 如果您使用的是 Microsoft 的新号码，您需要为用户更改 LineUri。 必须在用户使用 Set-CsOnlineVoiceUser 进行联机移动后执行此操作。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每租户配置摘要 

1. 通过查看 [此列表](direct-routing-border-controllers.md)，确保由直接路由支持 (SBC) 的会话边界控制器。 您还必须确保拥有正确版本的固件。  

2. 将本地 SBC 与团队直接路由服务配对。 有关详细信息，请参阅将 [SBC 与电话系统的直接路由服务配对](direct-routing-configure.md)。 

3. 此配置实质上是本地配置的镜像。 联机配置包括： 
   - OnlineVoiceRoutingPolicy (基于本地 VoiceRoutingPolicy，如果从 Skype for business Online 迁移用户，并且基于 VoicePolicy 将用户从企业语音) 迁移到本地，则基于。
   - OnlinePSTNUsage 对象 (基于本地 PSTN 使用) 。 
   - OnlineVoiceRoute (基于本地 VoiceRoute) 的对象。 

有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>迁移期间管理 EnterpriseVoiceEnabled 属性 

无论使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中具有 EnterpriseVoiceEnabled = true，用户才能拥有 PSTN 功能。  EnterpriseVoiceEnabled ( "EV-enabled" ) 是一个 (在本地目录和云中都不存在的策略) 的属性。 云中的值是团队的重要事项。  如何将 EV 启用的确切逻辑设置为 true 取决于以下方案： 

- 如果用户在本地 Skype for Business 服务器中启用了 EV，并且在将用户移动到云之前使用 Move-Move-csuser 为用户分配了电话系统许可证，则在线用户将预配为 "启用 EV"。 

- 如果现有的 TeamsOnly 或 Skype for business Online 用户分配有电话系统许可证，则默认情况下，启用 EV 不会设置为 true。  如果在分配电话系统许可证之前将本地用户移到云，也会出现这种情况。 在任何一种情况下，管理员都必须指定以下 cmdlet： 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

