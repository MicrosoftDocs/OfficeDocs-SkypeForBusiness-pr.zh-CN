---
title: 针对团队和 Skype for Business 的云整合
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文介绍了如何通过要移动到团队和/或 Skype for business Online 的 Skype for Business (或 Lync) 的内部部署 (即 Lync) 组织实现该合并。
ms.openlocfilehash: 46e84f9a65ec7626c5285196af83d63baa46c15e
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "36160472"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>针对团队和 Skype for Business 的云整合

许多大型企业具有多个本地 AD 林, 在某些情况下, 客户具有多个 Exchange 和/或 Skype for business Server (或 Lync Server) 部署。 此外, 即使只有一个本地林的组织, 也可以通过业务合并或收购在类似情况下找到自己。 当这些客户迁移到云时, 他们希望将给定本地工作负载的多个实例合并到一个 Office 365 租户中的云中。 本文介绍了如何通过多个将其 UC 工作负载的 Skype for Business (或 Lync) 部署到 Microsoft 云 (例如, Microsoft 团队和/或 Skype for business Online) 的组织实现这种合并。

以前, 在这种情况下, 为客户提供的指导可先将部署整合到本地, 然后再迁移到云。 虽然这仍是一个选项, 但本文介绍了一个基于新功能的解决方案, 该解决方案使具有多个 Skype for Business 部署的组织能够一次将一个部署迁移到一个 Office 365 租户, 而无需执行本地计算. 请注意, 即使使用此新功能, Skype for Business Online 和 Microsoft 团队也不会在具有单个 Office 365 租户的混合模式中支持多个 Skype for Business/Lync 林。 

> [!Important]
> 在使用本指南进行配置之前, 请务必查看并了解[限制](#limitations), 因为它们可能会影响您的组织。

## <a name="overview-of-cloud-consolidation"></a>云整合概述

将所有用户从本地集成到单个 Office 365 租户中的云, 可以为具有多个 Skype for Business 部署的任何组织实现, 前提是满足以下关键要求:

- 至少必须有一个 Office 365 租户。 不支持在具有多个 Office 365 租户的方案中进行合并。
- 在任何给定时间, 只有一个本地 Skype for Business 林可以处于混合模式 (共享 SIP 地址空间)。 所有其他本地 Skype for business 林必须保持本地 (且大概相互联盟)。 请注意, 如果需要,*可*通过新功能将这些其他内部部署组织同步到 AAD, 以禁用2018年12月提供的[联机 SIP 域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps)。

在多个林中部署 Skype for business 的客户必须将单个混合 Skype for business 林的所有用户分别迁移到使用共享 SIP 地址空间功能的 Office 365 租户中, 然后通过此功能禁用混合本地部署, 在继续迁移下一个本地 Skype for Business 部署之前。 在迁移到云之前, 本地用户将保持与在同一用户的本地目录中未表示的任何用户的联合状态。  

## <a name="canonical-example-of-cloud-consolidation"></a>云整合的规范示例

假设组织有两个独立的 Skype for Business 联合部署, 希望在 Microsoft 团队或 Skype for business Online 中将其联机合并。


|原始状态详细信息 |所需状态详细信息 |
|---------|---------|
|<ul><li>2独立 AD 林中的独立 Skype for business 本地部署<li>最多1个林与 Skype for business Online 混合使用 <li> Emc 相互联合 <li>用户不会在这些林之间同步<li> 组织可能拥有 Office 365 租户, 并且可能会将其目录同步到 Azure AD</ul>|<ul> <li>1 Office 365 租户<li>没有更多的本地部署, 因此不会保留任何混合<li>内部部署中的所有用户都驻留在 Skype for Business Online 中, 也可以选择 "仅限团队用户" <li>Skype for Business anywhere 无本地覆盖 <li>用户仍有本地身份验证</ul> |

![合并两个单独的联合本地部署](../media/cloudconsolidationfig1.png)  

从原始状态到所需结束状态的基本步骤如下所示。  请注意, 一些组织可能会发现, 它们的起始点位于这些步骤中间的某个位置。 请参阅本文稍后介绍的[其他起始点](#other-starting-points)。 最后, 在某些情况下, 可以根据需要调整订单。 后面介绍了[主要约束和限制](#limitations)。

1.  获取 Office 365 租户 (如果尚不存在)。
2.  确保在本地部署中的所有相关 SIP 域都已验证 Office 365 域。
3.  选择一个将与 Office 365 混合使用的 Skype for Business 部署。 在此示例中, 我们将使用 OriginalCompany。<span>com。
4.  为将首先变为混合 (OriginalCompany) 的[林启用 AAD 连接](configure-azure-ad-connect.md)。<span>com)。 
5.  如果您将向您的组织引入团队, 请将[TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)的租户范围的策略设置为 SfBWithTeamsCollab 或其他 SfB 模式 (SfBOnly 或 SfBWithTeamsCollabAndMeetings) 中的一种。 这对于确保仅向仍在本地的用户转移到团队的用户, 确保呼叫和聊天的路由非常关键。
6.  建议在这种情况 (但在第11步之前尚不需要) 为[其他林启用 AAD 连接](cloud-consolidation-aad-connect.md)(AcquiredCompany。<span>com)。 假定在这两个林中都启用了 AAD 连接, 则该组织看起来像**[图 A](#figure-a)**, 这可能是一些 emc 的一个常见的起始点。 
7.  对于由其他本地部署托管的任何 SIP 域 (在此示例中为 AcquiredCompany。<span>com) 中, 使用`Disable-CsOnlineSipDomain`在 PowerShell 中[禁用 Skype for business Online 中的这些 SIP 域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)。 (这是从2018年12月的新功能。)
8.  为 OriginalCompany[配置 Skype For business 混合](configure-federation-with-skype-for-business-online.md)。<span>com (仍然启用了联机 SIP 域的一种部署)。
9.  在混合部署 (OriginalCompany) 中<span> 。com) 中, 开始[将用户从本地 skype For business 移动到云](move-users-between-on-premises-and-cloud.md)(无论是工作组还是不是团队), 以便该帐户托管在 Skype For business Online 中。 现在, 组织如**[图 B](#figure-b)** 所示。图 A 中的关键变化是:
    - 来自本地目录的用户现在位于 AAD 中。
    - AcquiredCompany.<span>com 是一个已禁用的联机 SIP 域。
    - 某些用户已联机移动到 Skype for Business Online 或团队。 (请参阅紫色用户 A。)
10. 将所有用户移动到云后, 请为 OriginalCompany[禁用与 Skype For business 本地部署的混合](cloud-consolidation-disabling-hybrid.md)。<span>Office 365 中的 com:  
    - 在 Office 365 租户中禁用拆分域。
    - 禁用与 OriginalCompany 中的 Office 365 通信的功能。<span>com 本地。
    - 更新 OriginalCompany 的 DNS 记录。<span>指向 Office 365 的 com。
11. 如果尚未执行此操作, 请为将成为混合 (AcquiredCompany 的[下一个林启用 AAD 连接](cloud-consolidation-aad-connect.md)。<span>com)。 在这种情况下, 组织看起来如**[图 C](#figure-c)** 所示。对于某些组织来说, 这可能是另一个常见的起始点。 
12. 在 PowerShell 中, 为下一个将成为混合型 (AcquiredCompany) 的[本地部署启用 SIP 域](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps)。<span>com。 这是通过使用`Enable-CsOnlineSipDomain`, 这是从2018年12月到的新功能提供的。
13. 如果使用的是已关闭的联合身份验证, 则必须在**同一**Office 365 中将纯 online 租户的任何 SIP 域 (不包括 *. microsoftonline.com) 添加为允许的域。 请注意, 在更改生效之前可能需要一段时间, 并且在早期执行此操作时不会有任何损害, 因此我们建议您在迁移到步骤14之前做得好。
14. 将本地环境更新为接受在线租户中的任何 SIP 域, 使其匹配。
    - 将[所有边缘证书中的 SAN 更新](cloud-consolidation-edge-certificates.md)为与之前相同的值, 再加上任何现有 online SIP 域 (在此示例中, 除了 * microsoftonline.com) 的值 (在本例中为 OriginalCompany)。<span>com。
    - 请确保 OriginalCompany。<span>com 是本地部署中的一个[允许的域](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain), AcquiredCompany。 添加允许的域。
15. 在本地 AcquiredCompany 之间[启用 Skype For business 混合](configure-federation-with-skype-for-business-online.md)。<span>com 和云。
16. 根据需要,[将用户从本地迁移到云](move-users-between-on-premises-and-cloud.md)。 您可以直接将用户迁移到[TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)模式, 也可以先将其迁移到 Skype For business Online。 在此状态下, 组织的外观如**[图 D](#figure-d)** 所示。
17. 迁移所有用户后,[通过内部部署环境禁用混合部署](cloud-consolidation-disabling-hybrid.md), 以*使组织成为纯云*!

下图显示了此过程中各个关键点的配置。

##### <a name="figure-a"></a>图 A:

- 这两个组织都通过 AAD Connect 进行同步, 因此 AAD 现在拥有本地部署中的所有用户。
- 驻留在本地的所有用户。  
- 尚未配置 Skype for Business ** 混合。
- 如果两个部署中的用户使用团队, 则他们将无法相互联盟 (或任何组织), 也不会与任何 Skype for Business 用户进行互操作。 在此阶段, Microsoft 建议仅对频道使用团队。<br><br>
    ![图图](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>图 B:

- AcquiredCompany.<span>com 是一个[已禁用](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)的联机 SIP 域。 所有用户都是本地的。 如果他们使用的团队没有联盟或互操作性。 在此阶段, Microsoft 建议仅对频道使用团队。
- 已为其中一个内部部署组织启用 Skype for Business 混合。
- 混合组织中的某些用户已移至云 (用户 A 表示为紫色底纹)。 这些用户可以是 Skype for Business Online 用户, 也可以是只有具有完全互操作性和联合支持的用户。<br><br>
    ![图 B 图表](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>图 C:

- OriginalCompany 中的所有用户。<span>com 现在位于云中 (驻留在 Skype For business Online 中)。 建议他们也只是团队。
- Skype for business 混合配置与 OriginalCompany。<span>com 部署已禁用。 本地部署已丢失。
- 如果 AcquiredCompany。<span>com 以前未同步到 AAD, 若要从此处继续, 则需要立即同步。 但它不是混合 (共享 SIP 地址空间), 在组织准备好迁移到混合后, 纯内部部署组织的 online SIP 域 (AcquiredCompany.com) 应保持禁用状态, 以便用户可以与之通信的联机团队本地用户。<br><br>
    ![图 C 图](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>图 D:

- AcquiredCompany.<span>com 现已作为联机 SIP 域启用。
- 内部部署更新为接受 OriginalCompany。<span>com。 (允许的域和边缘证书均已更新)。
- 在 AcquiredCompany 之间启用共享 SIP 地址空间。<span>Com 和 Office 365 租户。
- 混合组织中的某些用户可能已移至云, 如下面的用户 D (用紫色底纹表示)。<br><br>
    ![图 D 图表](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他起始点

上面规范示例中的步骤假定组织从两个无 Office 365 状态的联合本地部署开始。 但是, 一些组织可能有现成的 Office 365 空间, 并且在上述顺序中可以有不同的入口点。 共有四种典型配置:

- 无 Office 365 租户的多个联合本地组织。 在这种情况下, 从步骤1开始。
- 已将多个 Skype for Business 林同步到单个 Azure AD 租户的多个联合本地组织。 此类组织类似于图 A 中的假想组织, 其中已完成步骤 1-6, 应从步骤7开始。
- 一个与1个或更多其他纯本地组织联合的混合组织, 其中没有一个同步到 AAD。 此类组织与**图 E**中的假想组织类似, 如下所示。
    - 此组织类似于图 B, 它已完成步骤 1-9, 不同之处在于:
        - 其非混合 Skype for Business 部署尚未同步** 到 Azure AD。
        -  联机 SIP 域尚未禁用。 
    - 这些组织应执行以下操作之一:
        - 完成现有混合组织的迁移, 并在步骤10中输入上述顺序。  和
        - 如果需要在完成混合组织的迁移之前将任何其他 Skype for business 林同步到 AAD, 则组织必须执行步骤 7 (在任何其他本地 Skype for Business 部署中禁用所有联机 SIP 域, 这些部署将同步到 AAD), 然后启用 AAD Connect, 仅继续执行步骤 10 (停止原始混合部署)。       
                **图 E**<br>
                ![图 E 图表](../media/cloudconsolidationfige.png)
- 纯 Skype for business Online 组织 (可能会, 也可能不会使用团队) 与独立的本地 Skype for business 组织联合。 一旦此组织禁用内部部署组织的联机 SIP 域并为本地 Skype for Business 组织启用 AAD 连接, 它就类似于**[图 C](#figure-c)** 中已完成步骤的假想组织1-11。

## <a name="limitations"></a>限制

- 至少必须有一个 Office 365 租户。 不支持在具有多个 Office 365 租户的方案中进行合并。
- 一次仅有一个本地 Skype for business 林可以在混合模式 (共享 SIP 地址空间) 中。 所有其他本地 Skype for business 林都必须保持纯内部部署, 并且应相互联合并与 Office 365 租户进行联合。
- 在迁移到云之前, 此部署中的用户无法使用非对称体验, 因为并非联机中的所有用户都在本地表示:
    - 体验可按如下方式汇总:
        - 任何联机用户都将与混合环境中的本地用户交互, 就像该用户是混合环境一样。
        - 混合部署中的本地用户将与其在本地目录中呈现的联机用户进行交互, 就像它们是混合的一样。 
        - 混合部署中的内部部署用户将与在本地 AD 中未表示为联合的联机用户进行交互。
    - 在上面的**[图 D](#figure-d)** 中, 用户 E 在 AcquiredCompany 中是本地的。<span>com。  用户 E 将使用标准混合体验与用户 D (托管联机) 进行交互, 但用户 E 将与用户 A、B 和 C 进行联合体验, 因为它们不在本地目录中表示。 但是, 用户 A、B 和 C 将与用户 E 交互, 就好像用户是在混合环境中一样。
    - 混合与联合的交互的含义:
        - 不会自动为联盟用户订阅状态, 除非将用户标记为联系人。
        - 呼叫转接在联盟域之间不起作用。
        - 呼叫转移方案更有限。
        - 限制可应用于联合流量。
- 鉴于此非对称体验, 在内部部署用户与不在本地目录中的云用户之间的跨内部部署方案中的呼叫功能的正式支持仅限于对等方。 
    - 不支持这些用户之间的呼叫转接、转移、呼叫队列等。
    - 这些不支持的呼叫方案仍将显示为启用状态, 但在很多情况下, 它们将无法以不可预知的方式发生。 
    - 在上面的**[图 D](#figure-d)** 中, 用户 E 是本地的, 并且与用户 A、B 或 C 的呼叫将仅受与对等方的对等客户端的支持。 (与用户 D 的调用不支持限制。) 但是, 在将本地用户 E 移动到云后, 此限制将不再适用。
- 如果您的环境中有多个 Skype for business Server 2019 部署, 则只能将其中一个部署配置为使用组织自动助理, 因为该功能需要 Skype for business Server 混合配置。 
- 可以调整一些前面步骤的顺序。 必须满足的关键要求是, 如果所有这些条件都为真, 则为:
    - 一个以上的本地 Skype for Business 林同步到单个 AAD 租户
    - 使用一个本地林启用拆分域
    - 混合组织中至少有一个用户已迁移到云<br>   然后,*必须*从任何其他本地 Skype for business 林禁用所有其他联机 SIP 域。 否则, 混合组织中的联机用户与其他组织中的本地用户之间的联盟将在一个方向上损坏。

## <a name="implications"></a>方面

- 由于对高级呼叫功能支持的限制如下所述, 因此**组织应将这些非对称状态作为迁移的一部分进行暂时处理, 而不是将其视为稳定状态**。  
- 具有多个本地 Skype for Business 部署的组织通常应从可完全迁移到云的部署开始, 以便可以继续进行合并。 在某些情况下, 在某些情况下, 可能会有一些 holdouts 的用户组不能移动到团队中, 这一点很容易理解。 如果在涉及多个 Skype for Business 林的方案中需要考虑这一点, 请从不具有这些限制的另一个林开始迁移 (如果可能)。
- 从本地迁移到云时, 具有委派关系和/或的用户通常会在呼叫转移方案中参与, 作为一个单元移动。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>移动到 TeamsOnly 模式的注意事项

当您将用户从本地移动到混合环境中的云时, 您可以将它们移动到 "仅 Skype for Business" 或 "TeamsOnly" 模式。 *如果您计划将用户移动到 TeamsOnly 模式, 请务必先阅读本节。*

- 向用户分配 TeamsOnly 模式时, 所有聊天和任何其他用户的呼叫将在该用户的团队客户端中进行陆地。 
- 为了确保在 TeamsOnly 的用户和仍在本地使用 Skype for Business 的用户之间正确路由聊天和呼叫, 您必须确保内部部署用户具有 TeamsUpgradePolicy SfB 模式之一, 而不是使用孤岛 (这是默认值)。). 
    - 若要执行此操作,*必须首先将租户的 TeamsUpgradePolicy 的全局实例设置为以下值之一*:
        - SfBWithTeamsCollab (推荐)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 您可以通过使用以下命令来授予租户范围内的策略:<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注意: 目前, 必须在租户范围级别执行此操作, 因为无法将策略分配给在联机目录中没有 SIP 地址的单个用户。 虽然已为纯本地部署禁用了 online SIP 域, 但这些域中的用户在设计中将不会有 SIP 地址。 因此, 将策略应用于本地用户的唯一方法是在租户级别分配。 相比之下, 在混合部署用户的联机目录中有一个 SIP 地址, 以便在需要与租户全局策略具有不同的值时, 可以明确地为它们分配一个策略。
- 团队客户端 UX 尚未服从 TeamsUpgradePolicy 的 SfB 模式。 例如, 在这两种模式下, 目前可以在团队中进行呼叫和聊天初始, 但在将来不是这样。 这可能会导致用户发生混淆, 因为回复有时可能会在团队中进行, 有时也可能是 Skype for business, 具体取决于环境。 建议您单独禁用对仍在本地的用户的呼叫并通过 TeamsMessagingPolicy 和 TeamsCallingPolicy 聊天。

## <a name="see-also"></a>另请参阅

[更新边缘证书](cloud-consolidation-edge-certificates.md)

[更新 AAD Connect 以包含多个林](cloud-consolidation-aad-connect.md)

[禁用混合以完成到云的迁移](cloud-consolidation-disabling-hybrid.md)
