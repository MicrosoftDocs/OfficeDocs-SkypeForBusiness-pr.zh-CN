---
title: 从服务器升级到 pstN Teams PSTN Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams 的语音注意事项
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4024e62c90ef99f3280d5aec15cd718b3d2b6de
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796816"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>从本地Teams升级到 Skype for Business PSTN 注意事项

本文介绍 PSTN (电话交换) 时需要考虑的Teams。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

此外，以下文章介绍重要的升级概念和共存行为：

- [Teams 和 Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - 仅电话系统模式Teams用户帐户分配升级策略时，才支持Teams策略Teams策略。  
 > - 只有在电话系统 SfB Skype for Business为用户帐户分配了一个Teams策略时，才支持将 Skype for Business 与应用一起使用。 
 > - 电话系统为用户帐户分配了一个使用Teams升级策略时，不支持此策略。
 > - 系统不会迁移来自 Skype for Business 的任何呼叫转发、团队呼叫组和委派设置，需要重新重新创建Teams。
 > - 有关云语音Microsoft Teams的一般概述，并帮助确定哪个 Microsoft 语音解决方案适合你的组织，请参阅规划你的Teams[解决方案](cloud-voice-landing-page.md)。


## <a name="pstn-calling-scenarios"></a>PSTN 呼叫方案

迁移到 TeamsOnly 模式时，有四种可能的调用方案：

- [具有 Microsoft 呼叫Skype for Business的 Skype for Business Online 中的用户](#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续拥有 Microsoft 呼叫计划。

- [使用 Skype for Business Online](#from-skype-for-business-online-with-on-premises-voice)的用户，通过本地或云连接器Skype for Business本地语音功能。 用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。

- [在本地使用 Skype for Business 的用户企业语音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)该用户将移动到联机并保留本地 PSTN 连接。  将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。 

- [在本地使用 Skype for Business 的用户企业语音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)该用户将移动到联机状态，使用 Microsoft 呼叫计划。  将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。

本文仅提供高级概述。 有关详细信息，请参阅直接电话系统[和](direct-routing-landing-page.md)[呼叫计划](calling-plan-landing-page.md)。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>从 Skype for Business Online 与 Microsoft 呼叫计划 

这是涉及语音的最简单升级方案。 

1. 确保为用户分配了一个Teams许可证。 默认情况下，分配 Microsoft 365 或 Office 365 许可证时，Teams启用，因此，除非以前禁用了 Teams 许可证，否则不需要任何操作。

2.  如果用户已经有一个包含电话号码的 Microsoft 呼叫计划，则只需在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。  在分配 TeamsOnly 模式之前，传入的 PSTN 呼叫将进入用户Skype for Business客户端。 升级到 TeamsOnly 模式后，传入的 PSTN 呼叫将进入用户Teams客户端。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>使用Skype for Business语音从 Skype for Business Online

在此方案中，用户已使用 Skype for Business Online，但其 PSTN 连接是本地的，使用混合Skype for Business Server云连接器版本。 使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着支持直接路由，其中 PSTN 中继通过本地会话边界控制器 (SBC) 直接连接到云中的直接路由服务。

下面列出了基本步骤。  步骤 1-4 在建议的顺序中列出，但可以按任何顺序完成。 关键是，所有这些操作都应在步骤 5 之前完成。

1. 如果要将租户范围策略设置为其中一种Skype for Business模式，请确保通过显式分配任何现有群岛用户来委派他们，如前面所述。

2. 为租户配置直接路由。 请参阅 [Direct Routing 的按租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 这随时都可以完成，但是，如果你想要确保在用户升级时具有正确的配置，最好在用户升级到 TeamsOnly 模式之前这样做。

4. 为语音迁移准备选择用户： 
   - 如有必要，请分配Teams许可证。  假设用户已在 Skype for Business Online 本地语音中正常运行，则用户已有Skype for Business计划 2 和Microsoft 电话系统。 让这两个计划保持启用状态，Skype for Business Online 计划 2 许可证。  
   - 分配所需的 OnlineVoiceRoutingPolicy。 

5. 升级用户：这些步骤应进行协调。 

   - 在 Microsoft 365 或 Office 365 中，使用 Grant-CsTeamsUpgradePolicy (将用户升级到 TeamsOnly) 。
   - 在 SBC 上，将语音路由配置为通过向直接路由而不是本地中介服务器发送呼叫来启用传入呼叫。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>从Skype for Business Server到本地，使用 企业语音，到直接路由

在此方案中，用户仍位于本地Skype for Business，其 PSTN 连接也在本地。 使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着启用直接路由，然后将用户移动到云。 
 
下面列出了基本步骤。  步骤 1-5 在建议的顺序中列出，但可以按任何顺序完成。 关键是应在步骤 6 之前完成所有这些操作。

1. 如果要将租户范围策略设置为其中一种 Skype for Business 模式，请确保按前面所述显式分配现有群岛用户来配置这些用户。

2. 如果尚未这样做，请为组织配置Skype for Business[混合 。](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. 为租户配置直接路由。 请参阅 [Direct Routing 的按租户配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 这可随时完成，但如果希望确保用户在升级时具有正确的配置，最好是在用户升级到 TeamsOnly 之前这样做。

5. 如有必要，Microsoft 365或Office 365许可证。  用户应同时拥有 Teams 和 Skype for Business Online 计划 2 以及 电话系统。 如果Skype for Business计划 2，请重新启用它。  

6. 升级用户：这些步骤应进行协调。 

   - 使用本地部署Skype for Business，使用 -MoveToTeams Move-CsUser运行脚本。 如果使用不支持 -MoveToTeams 开关的 Skype for Business Server 版本，请首先运行 Move-CsUser，然后在租户远程 PowerShell 或 Teams 管理控制台中分配 TeamsOnly 模式。

   - 在 SBC 上，将语音路由配置为通过向直接路由而不是本地中介服务器发送呼叫来启用传入呼叫。 

   - 在Microsoft 365或Office 365：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>从Skype for Business Server本地，使用 企业语音，到 Microsoft 呼叫计划

在此方案中，用户仍位于本地Skype for Business，其 PSTN 连接也在本地。 使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式意味着将用户移动到云，或者将其号码从旧运营商移植到 Microsoft 呼叫计划或为用户分配新号码。 

下面列出了基本步骤。步骤 1-5 在建议的顺序中列出，但可以按任何顺序完成。 关键是应在步骤 6 之前完成所有这些操作。 

1. 如果要将租户范围策略设置为其中一种 Skype for Business 模式，请确保按前面所述显式分配现有群岛用户来配置这些用户。 

2. 如果尚未这样做，请为组织配置Skype for Business[混合 。](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. 如果需要，请为这些Teams配置各种策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 这可随时完成，但如果希望确保用户在升级时具有正确的配置，最好是在用户升级到 TeamsOnly 之前这样做。 

4. 如有必要，Microsoft 365或Office 365许可证。用户应同时拥有 Teams 和 Skype for Business Online 计划 2 以及 电话系统。 如果Skype for Business计划 2，请重新启用它。  

5. 获取用户的电话号码。  (有关详细信息，请参阅 [管理](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)组织的电话号码 .) 

   - 如果要重新使用号码，请向运营商提交移植请求。  
   - 或者，可以直接从 Microsoft 获取新号码。 

6. 升级用户，并根据需要分配 LineUri。 使用本地 Skype for Business 工具，使用 Move-CsUser -MoveToTeams 开关运行脚本。  

    - 如果要将号码移植到 Microsoft，应协调发生端口时此操作的计时。 

    - 如果使用来自 Microsoft 的新号码，则需要更改用户的 LineUri。 必须使用 Set-CsOnlineVoiceUser 将用户联机移动后完成此操作。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的按租户配置摘要 

1. 查看此列表，确保直接路由 (SBC) 的会话边界 [控制器](direct-routing-border-controllers.md)。 此外，必须确保固件版本正确。  

2. 将本地 SBC 与 Teams直接路由服务配对。 有关详细信息，请参阅将 SBC 与 电话系统[的直接路由服务](direct-routing-configure.md)配对。 

3. 此配置实质上是本地配置的镜像。 联机配置包括： 
   - 如果从 Skype for Business Online 迁移用户，则 OnlineVoiceRoutingPolicy (基于本地 VoiceRoutingPolicy;如果使用 企业语音) 从本地迁移用户，则基于 VoicePolicy。
   - OnlinePSTNUsage 对象 (本地 PSTN 使用情况) 。 
   - OnlineVoiceRoute 对象 (本地 VoiceRoute) 。 

有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在迁移期间管理 EnterpriseVoiceEnabled 属性 

无论使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中拥有 EnterpriseVoiceEnabled=true，用户必须具有 PSTN 功能。  EnterpriseVoiceEnabled ("已启用 EV") 是一个属性 (，而不是存在于本地目录和云中的策略) 。 云中的值对于云Teams。  启用 EV 的方式设置为 true 的确切逻辑取决于以下方案： 

- 如果用户在本地 Skype for Business Server 中启用了 EV，并且使用 Move-CsUser 将用户移动到云之前，向用户分配了 电话系统 许可证，则联机用户将预配 EV-enabled=true。 

- 如果为现有 TeamsOnly 或 Skype for Business Online 用户分配了 电话系统 许可证，则启用 EV 的 默认设置为 true。  如果在分配本地用户许可证之前将本地用户移到云中，电话系统这种情况。 在任一情况下，管理员必须指定以下 cmdlet： 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相关链接

[规划Teams语音解决方案](cloud-voice-landing-page.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
