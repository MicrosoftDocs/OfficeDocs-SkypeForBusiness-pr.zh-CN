---
title: Teams 和 Skype for Business 云合并
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文介绍如何为希望将其 UC 工作负载移动到 Teams 和/或 Skype for Business Online 的具有本地部署 () 或 Lync (或 Lync) 的组织实现合并。
ms.openlocfilehash: 5533b1780edd2ab8a997d0f04665876c2f85f149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119021"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>针对 Teams 和 Skype for Business 的云整合

许多大型企业拥有一个以上的本地 AD 林，在某些情况下，客户拥有多个 Exchange 和/或 Skype for Business Server（或 Lync Server）部署。 此外，即使只有一个本地林的组织也可能通过企业并购兼并或收购发现自己遇到了类似的情况。 当这些客户移动到云时，他们希望将给定本地工作负载的多个实例合并到云中，加入单个 Microsoft 365 或 Office 365 组织。 本文介绍如何为具有 Skype for Business (或 Lync) 的多个本地部署的组织实现合并，这些组织希望将其 UC 工作负载移动到 Microsoft 云，例如 Microsoft Teams 和/或 Skype for Business Online。

以往，在这种情况下，建议客户先合并本地部署，然后再迁移到云。 虽然这仍是一个选项，但本文介绍的基于新功能的解决方案使具有多个 Skype for Business 部署的组织能够一次将一个部署迁移到单个 Microsoft 365 或 Office 365 组织中，而无需执行本地合并。 请注意，即使具有这一新功能，Skype for Business Online 和 Microsoft Teams 也不支持使用单个 Microsoft 365 或 Office 365 组织的混合模式中的多个 Skype for Business/Lync 林。 

> [!Important]
> 在将本指南用于配置之前，请务必查看并了解 [限制](#limitations)，因为它们可能会影响你的组织。

## <a name="overview-of-cloud-consolidation"></a>云整合概述

对于具有多个 Skype for Business 部署的任何组织，只要满足以下关键要求，就可以将所有用户从本地合并到单个 Microsoft 365 或 Office 365 组织中云中：

- 最多必须涉及一个 Microsoft 365 或 Office 365 组织。 不支持在具有多个组织的方案中进行合并。
- 在任意给定时间，仅有一个本地 Skype for Business 林可处于混合模式（共享 SIP 地址空间）。 所有其他本地 Skype for Business 林必须保留在本地（并且可能相互联合）。 请注意，如果需要，这些其他本地组织可以同步到 AAD，并新增功能以禁用自 2018 年 12 月起可用的联机[SIP](/powershell/module/skype/disable-csonlinesipdomain)域。

在多个林中部署 Skype for Business 的客户必须使用共享 SIP 地址空间功能将单个混合 Skype for Business 林的所有用户分别迁移到 Microsoft 365 或 Office 365 组织，然后禁用与本地部署的混合，然后再继续迁移下一个本地 Skype for Business 部署。 在迁移到云之前，本地用户与未在同一用户本地目录中表示的任何用户保持联盟状态。  

## <a name="canonical-example-of-cloud-consolidation"></a>云合并的规范示例

请考虑具有两个单独的 Skype for Business 联合本地部署的组织，它们想要将它们联机合并到 Microsoft Teams 或 Skype for Business Online 中。


|原始状态详细信息 |所需状态详细信息 |
|---------|---------|
|<ul><li>2 个独立的 Skype for Business 本地部署，分别位于单独的 AD 林中<li>最多 1 个林与 Skype for Business Online 混合使用 <li> 组织相互联盟 <li>用户未跨这些林同步<li> 组织可能拥有 Microsoft 365 或 Office 365 组织，并且可能正在将他们的目录同步到 Azure AD</ul>|<ul> <li>1 Microsoft 365 或 Office 365 组织<li>没有更多的本地部署，因此没有混合剩余<li>本地所有用户都位于 Skype for Business Online 中，并且可以选择是仅 Teams 用户 <li>Skype for Business 在任意位置没有本地占用空间 <li>用户仍具有本地身份验证</ul> |

![合并两个单独的联合本地部署](../media/cloudconsolidationfig1.png)  

下面是从原始状态进入所需结束状态的基本步骤。  请注意，某些组织可能会发现其起点位于这些步骤的中间位置。 请参阅 [本文稍后部分的其他](#other-starting-points)起始点。 最后，在某些情况下，可以根据需要调整顺序。 [稍后将介绍关键](#limitations) 约束和限制。

1.  获取 Microsoft 365 或 Office 365 组织（如果尚不存在）。
2.  确保跨两个内部部署的所有相关 SIP 域都经过 Microsoft 365 或 Office 365 域验证。
3.  选择一个将与 Microsoft 365 或 Office 365 混合的 Skype for Business 部署。 本示例中，我们将使用 OriginalCompany。 <span>com.
4.  [为将首先成为](configure-azure-ad-connect.md) 混合林的林启用 AAD Connect (OriginalCompany。 <span>com) 。 
5.  如果要将 Teams 引入你的组织，将 [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) 的租户范围策略设置为 SfBWithTeamsCollab 或其他 SfB 模式之一 (SfBOnly 或 SfBWithTeamsCollabAndMeetings) 。 这一点对于确保将来自仅移动到 Teams 的用户的呼叫和聊天路由到保留在本地的用户至关重要。
6.  此时，建议 (步骤 11) 为 AcquiredCompany 的其他林启用 [AAD](cloud-consolidation-aad-connect.md) (。 <span>com) 。 假设在两个林中都启用了 AAD Connect，则组织将类似于图 **[A，](#figure-a)** 这在某些组织可能是一个常见起点。 
7.  对于由其他本地部署托管的任何 SIP 域， (为 AcquiredCompany。 <span>com) ，在 [PowerShell](/powershell/module/skype/disable-csonlinesipdomain) 中使用 禁用 Skype for Business Online 中的这些 SIP `Disable-CsOnlineSipDomain` 域。  (这是自 2018 年 12 月起的新) 
8.  [为](configure-federation-with-skype-for-business-online.md) OriginalCompany 配置 Skype for Business 混合。 <span>com (一个仍启用了联机 SIP 域的) 。
9.  在混合部署中 (OriginalCompany。 <span>com) ， start [moving users from Skype for Business on premises to the cloud](move-users-between-on-premises-and-cloud.md) (whether teams Only or not) so that account is homed in Skype for Business Online. 现在，组织如图 **[B 所示](#figure-b)**。图 A 中的主要更改是：
    - 来自两个本地目录的用户现在位于 AAD 中。
    - AcquiredCompany。 <span>com 是已禁用的联机 SIP 域。
    - 某些用户已联机移动到 Skype for Business Online 或 Teams。  (请参阅紫色用户 A.) 
10. 将所有用户移动到云后，禁用与 [OriginalCompany 的 Skype for Business](cloud-consolidation-disabling-hybrid.md) 本地部署混合。 <span>office 365 中的 com：  
    - 在 Microsoft 365 或 Office 365 组织中禁用拆分域。
    - 禁用在 OriginalCompany 中与 Microsoft 365 或 Office 365 进行通信的能力。 <span>com 本地。
    - 更新 OriginalCompany 的 DNS 记录。 <span>com 指向 Microsoft 365 或 Office 365。
11. 如果尚未完成，请为下一个将在 AcquiredCompany 中实现混合 ([AAD](cloud-consolidation-aad-connect.md) Connect。 <span>com) 。 此时，组织如图 **[C 所示](#figure-c)**。这可能是某些组织的另一个常见起点。 
12. 在 PowerShell [中，为](/powershell/module/skype/enable-csonlinesipdomain) 将进行混合部署的下一个本地部署启用 SIP 域 AcquiredCompany。 <span>com. 这是通过使用 完成 `Enable-CsOnlineSipDomain` ，这是自 2018 年 12 日起提供的新功能。
13. 如果使用封闭联盟，则必须添加任何 SIP 域， (\* Microsoft 365 或 Office 365 中作为允许域的纯联机租户的 .microsoftonline.com) 除外。 请注意，更改可能需要一些时间才能生效，而且提前执行此操作没有坏处，因此我们建议在移动到步骤 14 之前先执行此操作。
14. 更新本地环境以接受来自联机租户的任何 SIP 域，以便它们相匹配。
    - 将所有边缘证书中的[SAN](cloud-consolidation-edge-certificates.md)更新为与之前相同的值，以及除 *.microsoftonline.com) 之外的任何现有联机 SIP 域 (（在这种情况下为 Sip.OriginalCompany）的值。 <span>com.
    - 确保 OriginalCompany。 <span>com 是 [本地部署](/powershell/module/skype/new-csalloweddomain) AcquiredCompany 中允许的域。 添加允许的域。
15. [在本地](configure-federation-with-skype-for-business-online.md) AcquiredCompany 之间启用 Skype for Business 混合。 <span>com 和云。
16. 如果需要， [将用户从本地迁移到云](move-users-between-on-premises-and-cloud.md)。 你可以将用户直接迁移到 [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) 模式，也可以先将其迁移到 Skype for Business Online。 在此状态中，组织如图 **[D 所示](#figure-d)**。
17. 迁移所有用户后，禁用与本地环境的混合 [，](cloud-consolidation-disabling-hybrid.md) 使 *组织成为纯云*！

下图显示了此过程中各个关键点的配置。

##### <a name="figure-a"></a>图 A：

- 这两个组织均通过 AAD Connect 进行同步，因此 AAD 现在具有来自两个本地部署的所有用户。
- 所有本地用户。  
- 尚未配置 Skype  for Business 混合。
- 如果任一部署中的用户使用 Teams，他们将无法相互联盟 (或任何组织) ，也无法与任何 Skype for Business 用户进行互操作。 在此阶段中，Microsoft 建议仅对频道使用 Teams。<br><br>
    ![图：图表](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>图 B：

- AcquiredCompany。 <span>com 是 [已禁用](/powershell/module/skype/disable-csonlinesipdomain) 的联机 SIP 域。 所有用户都是本地用户。 如果他们使用 Teams，它们没有联盟或互操作性。 在此阶段中，Microsoft 建议仅对频道使用 Teams。
- 其中一个本地组织已启用 Skype for Business 混合。
- 混合组织中某些用户已移动到云 (用户 A，如紫色底纹) 。 这些用户可以是 Skype for Business Online 用户或仅 Teams 用户，具有完全互操作性和联合身份验证支持。<br><br>
    ![图 B 图表](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>图 C：

- OriginalCompany 中的所有用户。 <span>com 现在托管在 (Skype for Business Online) 。 建议它们也是"仅 Teams"。
- 具有 OriginalCompany 的 Skype for Business 混合配置。 <span>com 部署已禁用。 本地部署已消失。
- 如果 AcquiredCompany。 <span>com 以前未同步到 AAD，若要继续，需要立即同步。 但它尚不是混合 (共享 SIP 地址空间) ，在组织准备移动到混合环境之前，纯本地组织 (AcquiredCompany.com) 的联机 SIP 域应保持禁用状态，以便联机 Teams 用户可以与本地用户进行通信。<br><br>
    ![图 C 图表](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>图 D：

- AcquiredCompany。 <span>com 现已启用为联机 SIP 域。
- 本地更新为接受 OriginalCompany。 <span>com.  (允许的域和边缘证书都更新) 。
- 在 AcquiredCompany 之间启用共享 SIP 地址空间。 <span>com 和 Microsoft 365 或 Office 365 组织。
- 混合组织中某些用户可能已被移动到云，如下面的用户 D (紫色底纹) 。<br><br>
    ![图 D 图表](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他起点

以上规范示例中的步骤假定组织从两个没有 Microsoft 或 Office 365 状态的联合本地部署开始。 但是，某些组织可能有现有的 Microsoft 365 或 Office 365 占用，并且上述序列中可能有不同的入口点。 有四种典型的配置：

- 没有 Microsoft 365 或 Office 365 组织的多个联合本地组织。 在这种情况下，请从步骤 1 开始。
- 多个已同步多个 Skype for Business 林到单个 Azure AD 租户的联合本地组织。 此类组织类似于图 A 中的假设组织，该组织已完成步骤 1-6，应从步骤 7 开始。
- 与 1 个或多个其他纯本地组织联盟的混合组织，其中没有任何组织与 AAD 同步。 此类组织类似于图 **E** 中的假设组织，如下所示。
    - 此组织类似于图 B，它已完成步骤 1-9，但：
        - 其非混合 Skype for Business 部署 *尚未* 同步到 Azure AD。
        -  联机 SIP 域尚未禁用。 
    - 这些组织应：
        - 完成现有混合组织的迁移，在步骤 10 中输入上述顺序。  或者，
        - 如果在完成混合组织的迁移之前，需要将任何其他 Skype for Business 林同步到 AAD，则组织必须执行步骤 7 (禁用任何其他本地 Skype for Business 部署中将同步到 AAD) 并随后启用 AAD Connect 的所有联机 SIP 域，然后才继续步骤 10 (停用原始混合部署) 。       
                **图 E**<br>
                ![图 E 图表](../media/cloudconsolidationfige.png)
- 纯 Skype for Business Online 组织 (可能正在使用或不在使用 Teams) 与单独的本地 Skype for Business 组织联盟。 一旦此组织为内部部署组织禁用联机 SIP 域并启用本地 Skype for Business 组织的 AAD Connect，它类似于图 **[C](#figure-c)** 中所示的已完成步骤 1-11 的假设组织。

## <a name="limitations"></a>限制

- 最多必须涉及一个 Microsoft 365 或 Office 365 组织。 不支持在具有多个组织的方案中进行合并。
- 一次只能将一个本地 Skype for Business 林 (共享 SIP 地址) 混合模式。 所有其他本地 Skype for Business 林必须完全保留在本地，并且应该相互以及 Microsoft 365 或 Office 365 组织联盟。
- 在迁移到云之前，此部署中的用户体验是非对称的，因为并非所有在线用户都表示在本地：
    - 该体验可以总结如下：
        - 任何在线用户都将与混合环境中本地用户进行交互，就像用户是混合用户一样。
        - 混合部署中的本地用户将与在本地目录中表示的联机用户进行交互，就像他们是混合用户一样。 
        - 混合部署中的本地用户将与未在本地 AD 中表示为联合的联机用户进行交互。
    - 在 **[上图 D](#figure-d)** 中，用户 E 在 AcquiredCompany 中位于本地。 <span>com.  用户 E 会使用标准混合体验 (用户 D) 与用户 D 进行交互，但用户 E 将具有与用户 A、B 和 C 的联合体验，因为它们未在本地目录中表示。 但是，用户 A、B 和 C 将与用户 E 进行交互，就像用户是混合用户一样。
    - 混合与联合的交互的含义：
        - 除非将用户标记为联系人，否则不会自动为联盟用户订阅状态。
        - 呼叫转发在联盟域之间不起作用。
        - 呼叫转移方案更加有限。
        - 限制可应用于联盟流量。
- 鉴于这种非对称体验，对本地用户和不在内部部署目录中的云用户之间的跨界方案中调用功能的官方支持仅限于对等。 
    - 不支持在这些用户之间呼叫转接、转接、呼叫队列等。
    - 这些不支持的呼叫方案仍将显示为启用，但在许多情况下，它们以不可预知的方式失败。 
    - 在 **[上图 D](#figure-d)** 中，用户 E 位于本地，与用户 A、B 或 C 的呼叫将仅作为对等方受到支持。  (D 的呼叫将没有支持限制。) 但是，在将本地用户 E 移动到云后，此限制将不再适用。
- 如果你的环境中具有多个 Skype for Business Server 2019 部署，则只能将其中 1 个部署配置为使用组织 自动助理，因为该功能需要 Skype for Business Server 混合配置。 
- 可以调整上述某些步骤的顺序。 必须满足的关键要求是，如果满足以下所有条件：
    - 多个本地 Skype for Business 林同步到单个 AAD 租户
    - 使用一个本地林启用拆分域
    - 混合组织中至少有一个用户已迁移到云<br>   然后， *你必须禁用* 任何其他本地 Skype for Business 林中的所有其他联机 SIP 域。 否则，混合组织中联机用户与其他组织中本地用户之间的联盟将在一个方向中断。

## <a name="implications"></a>含义

- 由于上述对高级呼叫功能的支持存在一些限制，因此组织应该将这些非对称状态视为迁移的一部分，而不是将它们视为稳定 **状态**。  
- 具有多个本地 Skype for Business 部署的组织通常应从可以完全迁移到云的部署开始，以便可以继续合并。 可以理解为，在某些情况下，某些用户组的保留状态尚未可行，无法移动到 Teams。 在涉及多个 Skype for Business 林的方案中考虑这一点时，如果可能，请开始迁移另一个没有这些限制的林。
- 从本地迁移到云时，具有委派关系和/或通常参与呼叫转移方案的用户应作为一个单元一起移动。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>迁移到 TeamsOnly 模式的注意事项

在混合环境中将用户从本地移动到云时，你可以将其移动到 Skype for Business Only 或 TeamsOnly 模式。 *如果你计划将用户移动到 TeamsOnly 模式，请务必先阅读本部分。*

- 将 TeamsOnly 模式分配给用户时，来自任何其他用户的所有聊天和通话都将进入该用户的 Teams 客户端。 
- 如果本地使用 Skype for Business 的用户主要使用 Skype for Business 客户端，而不是 Teams，请考虑设置 TeamsUpgradePolicy，以便路由到这些本地用户始终登录 Skype for Business，而不是 Teams。 为确保 TeamsOnly 用户与仍在本地使用 Skype for Business 的用户之间的聊天和呼叫正确路由，本地用户必须具有 TeamsUpgradePolicy 的有效值，其中一种是 SfB 模式，而不是作为默认) 的 Islands (。 
    - 为此，你必须先将租户的 *TeamsUpgradePolicy* 全局实例设置为以下值之一：
        - SfBWithTeamsCollab (推荐) 
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 可以使用此命令授予租户范围策略：<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注意：必须在租户范围内级别进行此操作，因为无法将策略分配给在联机目录中没有 SIP 地址的单个用户。 虽然已针对纯本地部署禁用联机 SIP 域 () ，但根据设计，这些域中的用户在联机目录中没有 SIP 地址。 因此，将策略应用于这些本地用户的唯一方式是在租户级别分配策略。 相比之下，在混合部署中，用户在联机目录中将拥有 SIP 地址，因此，如果需要他们具有与租户全局策略不同的值，可以明确分配策略。
- Teams 客户端 UX 尚不遵守 TeamsUpgradePolicy 的 SfB 模式。 例如，在这些模式下，Teams 中的通话和聊天启动当前可能可行，尽管将来不会如此。 这可能会导致用户混淆，因为回复有时可能登录 Teams，有时也可能登录 Skype for Business，具体取决于情况。 建议为仍在本地的用户单独禁用通过 TeamsMessagingPolicy 和 TeamsCallingPolicy 的通话和聊天。

## <a name="see-also"></a>另请参阅

[更新 Microsoft Edge 证书](cloud-consolidation-edge-certificates.md)

[将 AAD Connect 更新为包含多个林](cloud-consolidation-aad-connect.md)

[禁用混合以完成到云的迁移](cloud-consolidation-disabling-hybrid.md)