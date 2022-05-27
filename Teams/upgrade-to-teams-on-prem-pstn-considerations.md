---
title: 从Skype for Business升级到Teams时的 PSTN 注意事项
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从Skype for Business升级到Teams的语音注意事项
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681343"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>从本地Skype for Business升级到Teams的 PSTN 注意事项

本文介绍升级到Teams时公共交换电话网络 (PSTN) 注意事项。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

以下文章介绍了重要的升级概念和共存行为：

- [Teams和Skype for Business共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - 仅当为用户的帐户分配了Teams仅限Teams模式的Teams升级策略时，才支持将电话系统与Teams配合使用。
> - 仅当为用户的帐户分配了具有 SfB 模式的Teams升级策略时，才支持将电话系统与Skype for Business配合使用。
> - 如果为用户的帐户分配了带 Islands 模式的Teams升级策略，则不支持电话系统。
> - 不会迁移来自Skype for Business的任何呼叫转接、团队呼叫组和委派设置，并且需要重新创建Teams。
> - 有关Microsoft Teams云语音功能的一般概述，并帮助确定哪个 Microsoft 语音解决方案适合你的组织，请参阅[规划Teams语音解决方案](cloud-voice-landing-page.md)。

## <a name="pstn-calling-scenarios"></a>PSTN 调用方案

迁移到 TeamsOnly 模式时，有四种可能的调用方案：

- [Skype for Business Online 中的用户，具有 Microsoft 呼叫计划](#from-skype-for-business-online-with-microsoft-calling-plans)。 升级后，此用户将继续具有 Microsoft 呼叫计划。

- [Skype for Business Online 中的用户，](#from-skype-for-business-online-with-on-premises-voice)通过本地或云连接器版本Skype for Business具有本地语音功能。 若要确保 TeamsOnly 用户具有 PSTN 功能，必须协调用户升级，以Teams用户迁移到直接路由。

- [Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)本地企业语音的用户，他们将转到联机并保持本地 PSTN 连接。  若要将此用户迁移到Teams，必须将用户的本地Skype for Business帐户移动到云，并协调用户迁移到直接路由的操作。

- [Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)本地企业语音的用户，他们将转到联机并使用 Microsoft 呼叫计划。  若要将此用户迁移到Teams，必须将用户的本地Skype for Business帐户移动到云。 必须使用 A 协调移动，) 该用户电话号码的端口到 Microsoft 呼叫计划，或者 B) 从可用区域分配新的订阅者号码。

本文仅提供高级概述。 有关详细信息，请参阅[电话系统直接路由](direct-routing-landing-page.md)和[呼叫计划](calling-plan-landing-page.md)。

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>从 Skype for Business Online 与 Microsoft 通话套餐

此方案是涉及语音的最简单的升级方案。

1. 确保为用户分配了Teams许可证。 默认情况下，在分配Microsoft 365或Office 365许可证时，将启用Teams。 除非之前禁用了Teams许可证，否则无需执行任何操作。

2. 如果用户已有包含电话号码的 Microsoft 呼叫计划，则唯一需要的更改是在 TeamsUpgradePolicy 中分配用户 TeamsOnly 模式。 在分配 TeamsOnly 模式之前，传入的 PSTN 调用将进入用户Skype for Business客户端。 升级到 TeamsOnly 模式后，传入的 PSTN 调用将进入用户Teams客户端。

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>使用本地语音从 Skype for Business Online

在此方案中，用户已在 Skype for Business Online 中。 用户的 PSTN 连接位于本地，使用混合模式下的Skype for Business Server或 Cloud Connector Edition。 若要使用 PSTN 功能将这些用户迁移到 TeamsOnly 模式，必须为用户启用直接路由。 通过直接路由，PSTN 中继通过本地会话边界控制器 (SBC) 直接连接到直接路由服务。

下面列出了基本步骤。  步骤 1-4 在建议的序列中列出，但可以按任何顺序完成。 这些步骤应在步骤 5 之前完成。

1. 如果要将租户范围的策略设置为Skype for Business模式之一，请务必通过显式分配现有 Islands 用户来为其分配 Islands 模式，如前所述。

2. 为租户配置直接路由。 请参阅 [直接路由的每个租户配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，请为这些用户配置各种Teams策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 可以随时配置 poicies。 但是，如果要确保用户在升级时具有正确的配置，请在将用户升级到 TeamsOnly 模式之前配置这些策略。

4. 为语音迁移准备选择用户：
   - 如有必要，请分配Teams许可证。  假设用户已在 Skype for Business Online 本地语音中正常工作，则用户已Skype for Business计划 2 和Microsoft 电话系统。 使这两个计划都保持启用状态，包括Skype for Business联机计划 2 许可证。
   - 分配所需的 OnlineVoiceRoutingPolicy。

5. 升级用户：应协调这些步骤。

   - 在Microsoft 365或Office 365中，将用户升级到 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。
   - 在 SBC 上，通过向直接路由而不是本地中介服务器发送呼叫来配置语音路由以启用传入呼叫。

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>从本地Skype for Business Server、企业语音到直接路由

在此方案中，用户仍驻留在本地Skype for Business。 用户的 PSTN 连接也是本地连接。 若要使用 PSTN 功能将此用户迁移到 TeamsOnly 模式，必须为用户启用直接路由，然后将用户移动到云。

下面列出了基本步骤。 步骤 1-5 在建议的序列中列出，但可以按任何顺序完成。 必须在步骤 6 之前完成步骤 1-5。

1. 如果要将租户范围的策略设置为Skype for Business模式之一，请务必通过显式分配现有 Islands 用户来指定这些用户，如前所述。

2. 如果尚未这样做，请为[组织配置Skype for Business混合](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 为租户配置直接路由。 请参阅 [直接路由的每个租户配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，请为这些用户配置各种Teams策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy) 。 可以随时配置策略。 但是，如果要确保用户在升级时具有正确的配置，请在将用户升级到 TeamsOnly 之前配置这些策略。

5. 如有必要，请分配Microsoft 365或Office 365许可证。  用户应同时具有Teams和Skype for Business联机计划 2 和电话系统。 如果禁用Skype for Business联机计划 2，请重新启用它。

6. 升级用户：应协调这些步骤。

   - 使用本地Skype for Business工具，使用 -MoveToTeams 开关运行Move-CsUser。 如果使用的Skype for Business Server版本不支持 -MoveToTeams 开关，请先运行Move-CsUser，然后在租户远程 PowerShell 或 Teams 管理员 控制台中分配 TeamsOnly 模式。

   - 在 SBC 上，通过向直接路由而不是本地中介服务器发送呼叫来配置语音路由以启用传入呼叫。

   - 在Microsoft 365或Office 365中：分配相关的 OnlineVoiceRoutingPolicy 以启用传出呼叫。

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>从本地Skype for Business Server、企业语音到 Microsoft 呼叫计划

在此方案中，用户仍驻留在本地Skype for Business。 用户的 PSTN 连接也是本地连接。 若要使用 PSTN 功能将此用户迁移到 TeamsOnly 模式，必须将用户移动到云，并将其号码从旧运营商移植到 Microsoft 呼叫计划，或向用户分配新号码。

下面列出了基本步骤。 步骤 1-5 在建议的序列中列出，但可以按任何顺序完成。 必须在步骤 6 之前完成步骤 1-5。

1. 如果要将租户范围的策略设置为Skype for Business模式之一，请务必通过显式分配现有 Islands 用户来指定这些用户，如前所述。

2. 如果尚未这样做，请为[组织配置Skype for Business混合](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 如果需要，请为这些用户配置各种Teams策略 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等) 。 可以随时配置策略。 但是，如果要确保用户在升级时具有正确的配置，请在将用户升级到 TeamsOnly 之前配置这些策略。

4. 如有必要，请分配Microsoft 365或Office 365许可证。 用户应同时具有Teams和Skype for Business联机计划 2 和电话系统。 如果禁用Skype for Business联机计划 2，请重新启用它。

5. 获取用户的电话号码。  (有关详细信息，请参阅 [管理组织的电话号码](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。) 

   - 如果要重复使用数字，请向运营商提交移植请求。
   - 或者，可以直接从 Microsoft 获取新号码。

6. 升级用户，并根据需要分配 LineUri。 使用本地Skype for Business工具，使用 -MoveToTeams 开关运行Move-CsUser。

    - 如果要将数字移植到 Microsoft，则应协调此操作在端口发生时发生的时间。

    - 如果使用来自 Microsoft 的新号码，则需要在用户使用 Set-CsPhoneNumberAssignment 联机后更改用户的 LineUri。

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每租户配置摘要

1. 查看 [此列表](direct-routing-border-controllers.md)，确保直接路由支持会话边框控制器 (SBC) 。 另请确保拥有正确的固件版本。

2. 将本地 SBC 与Teams直接路由服务配对。 有关详细信息，请参阅[将 SBC 与 电话系统 的直接路由服务配对](direct-routing-configure.md)。

3. 此配置本质上是本地配置的镜像。 联机配置包括：
   - OnlineVoiceRoutingPolicy (基于本地 VoiceRoutingPolicy（如果将用户从 Skype for Business Online 迁移）和基于 VoicePolicy（如果使用企业语音) 从本地迁移用户）。
   - OnlinePSTNUsage 对象 (基于本地 PSTN 使用情况) 。
   - 基于本地 VoiceRoute)  (OnlineVoiceRoute 对象。

有关详细信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在迁移期间管理 EnterpriseVoiceEnabled 属性

无论是使用直接路由还是 Microsoft 呼叫计划，用户都必须在 Azure AD 中拥有 EnterpriseVoiceEnabled=true，用户才能具有 PSTN 功能。  EnterpriseVoiceEnabled (“已启用 EV”) 是一个属性， (不是存在于本地目录和云中的策略) 。 云中的值对于Teams来说很重要。  启用 EV 的确切逻辑如何设置为 true 取决于以下方案：

- 如果用户在本地Skype for Business Server中启用了 EV，并且在使用 Move-CsUser 将用户移到云之前向用户分配了电话系统许可证，则联机用户将预配 EV-enabled=true。

- 如果为现有 TeamsOnly 或 Skype for Business Online 用户分配了电话系统许可证，则默认情况下不会将启用 EV 的用户设置为 true。 如果在分配电话系统许可证之前将本地用户移到云中，也会出现这种情况。 在任一情况下，管理员都必须指定以下 cmdlet：

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>相关链接

[规划Teams语音解决方案](cloud-voice-landing-page.md)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
