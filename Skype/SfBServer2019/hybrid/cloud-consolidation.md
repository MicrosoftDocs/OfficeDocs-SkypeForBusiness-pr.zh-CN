---
title: 云整合个团队和 Skype for Business
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文介绍如何实现该合并为与本地 deployment(s) Skype 业务 （或 Lync） 他们希望将移动到团队其 UC 工作负荷和/或业务 online Skype 的组织。
ms.openlocfilehash: 09a19b884b67f9d6c3dbbe552f2576b6b5e68674
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247631"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>云整合个团队和 Skype for Business

> [!Note]
> 这是预览版或早期版本功能。 

许多大型企业具有多个一个内部部署 AD 林，且在某些情况下，客户具有多个 Exchange 和/或 Skype 业务服务器 （或 Lync Server） 部署。 此外，即使组织只有一个内部部署林中具有会发现自己在通过业务合并或收购类似的情况下。 这些客户移动到云，他们想要合并到单个 Office 365 租户到云的本地给定工作负荷的多个实例。 本文介绍如何实现的组织具有多个本地部署的 Skype 业务 （或 Lync） 希望将其 UC 工作负荷移动到 Microsoft 云，例如、 Microsoft 团队和/或业务 online Skype 该合并。

过去，本指南已在此情况下的客户首先合并部署本地和然后移到云中。 虽然这仍是一个选项，本指南介绍了基于新功能，使业务部署多个 Skype 迁移到单个 Office 365 租户，一次一个部署无需执行操作的本地组织的解决方案合并。 请注意，即使使用这一新功能，业务 Online 和 Microsoft 团队的 Skype 不支持多个 Skype 混合模式与单个的 Office 365 租户中的业务/Lync 目录林。 

> [!Important]
> 之前配置使用本指南，请务必查看并了解的[限制](#limitations)，因为它们会影响您的组织。

## <a name="overview-of-cloud-consolidation"></a>云整合的概述

如果满足以下主要要求，从内部部署的所有用户整合到单个 Office 365 租户中的云可以实现具有多个 Skype 业务部署任何组织：

- 必须有最一个 Office 365 租户涉及。 不支持合并方案中的与多个 Office 365 租户。
- 在任何给定时间，仅具有一个内部部署业务林的 Skype 可以在混合模式下 （共享 SIP 地址空间）。 业务林中的所有其他内部部署 Skype 必须保留本地 （并且可能与每个其他联盟）。 请注意，这些其他内部部署组织*可以*同步到 AAD 如果需要使用[新功能，以禁用联机 SIP 域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps)截止年 12 月 2018年可用。

客户的 Skype for Business 中的多林部署必须完全将单个混合 Skype 业务林的所有用户分别都迁移到 Office 365 租户使用共享 SIP 地址空间功能，然后禁用的混合在本地部署中之前移动迁移下本地 Skype 业务部署。 正在迁移到云中之前, 在本地用户保持联盟状态与未表示同一个用户的本地目录中的任何用户。  

## <a name="canonical-example-of-cloud-consolidation"></a>云整合的规范示例

请考虑使用两个单独联盟的本地部署的 Skype for Business 内想要合并其 online 中的 Microsoft 团队或 Skype 业务 online 组织。


|原始状态详细信息 |所需的状态详细信息 |
|---------|---------|
|<ul><li>2 独立 Skype for Business 部署在单独的 AD 林中部署<li>最多 1 林的是与业务 online Skype 混合中 <li> 与每个其他联盟的部门 <li>用户不在这些林中已同步<li> 组织可能具有 Office 365 租户，并且可能同步其目录到 Azure AD</ul>|<ul> <li>1 的 office 365 租户<li>更多的本地部署中，因此任何剩余的混合<li>从本地的所有用户都驻留在 Skype 业务 online 和还可以选择仅团队用户 <li>不在本地占地面积 for Business 的 Skype 的任意位置 <li>用户仍具有本地身份验证</ul> |

![合并两个单独联盟的本地部署](../media/cloudconsolidationfig1.png)  

从原始状态获取所需的最终状态的基本步骤如下所示。  请注意，某些组织可能会发现其起始点位于中间这些步骤。 请参阅本文后面的[其他切入点](#other-starting-points)。 最后，在某些情况下顺序可以调整，根据需要。 稍后介绍[键约束和限制](#limitations)。

1.  如果尚不存在，则获取 Office 365 租户。
2.  请确保跨两个本地部署中所有相关的 SIP 域都已验证的 Office 365 域。
3.  选取一个 Skype 将与 Office 365 的混合的业务部署。 本示例中，我们将使用 OriginalCompany。<span>com。
4.  [为林启用 AAD 连接](configure-azure-ad-connect.md)首先将成为混合 (OriginalCompany。<span>com)。 
5.  如果您将到您的组织推出团队，为[TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) SfBWithTeamsCollab 或其他 SfB 模式 （SfBOnly 或 SfBWithTeamsCollabAndMeetings） 的一个租户范围的策略。 这是关键以确保路由的呼叫，将移动到团队仅向保持在本地用户的用户聊天。
6.  它是此时建议 （但尚未要求之前步骤 11） 要[支持 AAD 连接的其他林](cloud-consolidation-aad-connect.md)(AcquiredCompany。<span>com)。 假定在两个林启用了 AAD 连接后，组织看起来像**[图](#figure-a)**，这可能是一些控制的组织的常见起始点。 
7.  对其他内部部署由承载任何 SIP 域 (在此情况下，AcquiredCompany。<span>com)，[禁用这些 Skype 业务 online 中的 SIP 域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)使用`Disable-CsOnlineSipDomain`在 PowerShell 中。 （这是截止年 12 月 2018年的新功能）。
8.  OriginalCompany 的[业务混合配置 Skype](configure-federation-with-skype-for-business-online.md) 。<span>com （仍已启用联机 SIP 域的一个部署）。
9.  在混合部署中 (OriginalCompany。<span>com)，启动[移动用户从内部部署到云的业务的 Skype](move-users-between-on-premises-and-cloud.md) (是否工作组只有或不)，以便为业务 Online 帐户驻留在 Skype。 现在组织看起来像**[图 B](#figure-b)**。从图 A 的关键更改是：
    - 用户从两个内部部署目录现在在 AAD。
    - AcquiredCompany。<span>com 是禁用的联机 SIP 域。
    - 某些已移动用户联机到任一 Skype 业务联机或团队。 （请参阅紫色用户 a。）
10. 一旦所有用户都迁移到云中，[禁用与 Skype 的业务内部部署混合](cloud-consolidation-disabling-hybrid.md)OriginalCompany。<span>com 从 Office 365:  
    - 禁用 Office 365 租户中的拆分域。
    - 禁用的功能与 Office 365 中 OriginalCompany 进行通信。<span>com 本地。
    - 为 OriginalCompany 更新 DNS 记录。<span>com 以指向 Office 365。
11. 如果没有完成操作，[启用 AAD 连接的下一个林](cloud-consolidation-aad-connect.md)的将转混合 (AcquiredCompany。<span>com)。 此时，组织类似于**[图 C](#figure-c)**。这可能是对于某些组织的另一个通用的起始点。 
12. 在 PowerShell 中，[启用 SIP 域下一步的本地部署](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps)的将转混合 AcquiredCompany。<span>com。 这是使用`Enable-CsOnlineSipDomain`，这是截止年 12 月 2018年可用的新功能。
13. 如果您使用关闭联合身份验证，则必须添加任何 SIP 域 (但不包括 *。 microsoftonline.com) 为允许的域中**同一个**Office 365 的纯 online 租户。 请注意，可能需要一些时间才能更改生效并没有什么伤害的早期，这样，我们建议您执行此操作，以便之前将移至步骤 14。
14. 更新内部部署环境以接受从 online 租户，任何 SIP 域，因此它们匹配。
    - [更新中所有的边缘证书的 SAN](cloud-consolidation-edge-certificates.md)像以前一样，为相同的值再加上的任何现有的联机 SIP 域的值 (除 *。 microsoftonline.com)，在这种情况下，Sip.OriginalCompany。<span>com。
    - 请确保 OriginalCompany。<span>com 是[允许的域](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain)在本地部署中，AcquiredCompany。 添加允许的域。
15. 在本地 AcquiredCompany 之间[启用业务混合的 Skype](configure-federation-with-skype-for-business-online.md) 。<span>com 和云。
16. 为所需，[迁移用户从内部部署到云](move-users-between-on-premises-and-cloud.md)。 可以将用户迁移可以直接到[TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)模式也可以将其迁移前到 Skype 业务 online。 在此状态下，组织类似于**[图 D](#figure-d)**。
17. 一旦所有用户都将都迁移，为*使组织纯云*[禁用与内部部署环境的混合](cloud-consolidation-disabling-hybrid.md)！

下图显示在此过程中在各种关键点配置。

##### <a name="figure-a"></a>图答：

- 通过 AAD 连接，因此 AAD 现在有同时从所有用户这两个组织同步的本地部署。
- 所有用户都驻留在本地。  
- Skype*业务混合尚未配置*。
- 如果任一部署中的用户使用团队，他们也不能与每个其他 （或任何组织），联盟，也不能将具有业务用户的任何 Skype 的互操作性。 在此阶段，Microsoft 建议仅为通道使用团队。<br><br>
    ![图 A 关系图](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>图 b:

- AcquiredCompany。<span>com 是[禁用](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)联机 SIP 域。 所有用户都都在本地。 如果他们使用团队它们没有联盟或互操作性。 在此阶段，Microsoft 建议仅为通道使用团队。
- Skype 业务混合已启用内部部署组织之一。
- 混合组织中的某些用户移动到云 （用户 A 由紫色底纹）。 这些用户可以是联机业务用户的 Skype 或团队只有具有完全的互操作性和联合身份验证支持的用户。<br><br>
    ![图 B 关系图](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>图 c:

- 从 OriginalCompany 的所有用户。<span>com 现在位于云 （驻留在 Skype 业务 online）。 建议，它们也是仅团队。
- 与 OriginalCompany 业务混合配置 Skype。<span>com 部署已被禁用。 在本地部署不存在。
- 如果 AcquiredCompany。<span>com 以前未同步到 AAD，继续从此处它必须立即同步。 但它还未混合 （共享 SIP 地址空间） 以便联机团队用户能与其通信纯内部部署组织 (AcquiredCompany.com) 的联机 SIP 域准备要迁移到混合组织之前，应保持禁用状态，内部部署用户。<br><br>
    ![图 C 关系图](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>图 d:

- AcquiredCompany。<span>com 现在启用为联机 SIP 域。
- 在本地将更新以接受 OriginalCompany。<span>com。 （同时允许的域，并更新边缘证书）。
- AcquiredCompany 间启用了共享 SIP 地址空间。<span>com 和 Office 365 租户。
- 混合组织中的某些用户可能已移到云中，如下面的用户 D （由紫色底纹）。<br><br>
    ![图 D 关系图](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他的起始点

上面的规范示例中的步骤假定组织启动与没有 Office 365 状态的两个联合的本地部署。 但是，某些组织可能具有现有的 Office 365 足迹，并且可以有不同的入口点上面的顺序。 有四个典型的配置：

- 与没有 Office 365 租户的多个联盟的内部部署组织。 在这种情况下，从步骤 1 开始。
- 已同步业务林的多个 Skype 到单个 Azure AD 的多个联盟的内部部署组织租户。 此类组织类似于图，其中已完成步骤 1-6，应开始在步骤 7 中的假设组织。
- 与 1 建立联盟的混合组织或多个其他纯内部部署组织，都不同步到 AAD。 此类组织将类似于**图 E**，如下所示中假想的组织。
    - 此组织内容类似于图 B，已完成步骤 1-9，除外：
        - 对于业务部署其非混合 Skype 是*不*尚未同步到 Azure AD。
        -  联机 SIP 域未尚未被禁用。 
    - 这些组织应具有下列任一：
        - 完成迁移现有的混合组织并输入上面的顺序在 10 个步骤。  OR
        - 如果需要进行任何其他同步到 AAD 之前完成迁移的混合组织，则组织必须执行的业务林的 Skype 步骤的 7 （禁用所有联机中将业务部署的任何其他本地 Skype 的 SIP 域同步到 AAD） 和启用 AAD 连接，再继续执行步骤 10 （停用原始的混合部署）。       
                **图 E**<br>
                ![图 E 关系图](../media/cloudconsolidationfige.png)
- 业务 Online 组织的联盟 （其中，也可能没有使用团队） 与 Business 组织的本地单独 Skype 纯 Skype。 此组织禁用内部部署组织的联机 SIP 域并启用 Business 组织的内部部署 Skype AAD 连接后，它类似于**[图 C](#figure-c)** 已完成步骤中所示假想的组织1-11。

## <a name="limitations"></a>限制

- 必须有最一个 Office 365 租户涉及。 不支持合并方案中的与多个 Office 365 租户。
- 仅具有一个内部部署业务林的 Skype 一次可以是在混合模式下 （共享 SIP 地址空间）。 所有其他内部部署业务林的 Skype 必须保持纯粹本地，并且应与每个其他和 Office 365 租户联盟。
- 正在迁移到云中之前, 没有在此部署中，用户不对称体验因为 online 中的并非所有用户都都表示为本地：
    - 可以如下所示总结了体验：
        - 联机驻留任何用户，如果用户是混合将与内部部署混合环境中的用户进行交互。
        - 在混合部署中的内部部署用户将交互，就像混合其本地目录中都表示联机用户。 
        - 本地混合部署中的用户将交互联机用户不会出现在内部部署 AD 如联盟。
    - 在**[图 D](#figure-d)** 上面，用户 E 是内部 AcquiredCompany 中。<span>com。  E 用户将交互用户 D （联机宿主） 使用标准混合体验，但用户 E 将具有联盟与 A、 B 和 C 的用户体验，因为它们不在内部部署目录表示。 但是，如同中混合用户 A、 B 和 C 的用户将交互用户 E。
    - 正在与联合身份验证的混合的交互的影响：
        - 状态未自动订阅的联盟用户除非用户被标记为联系人。
        - 呼叫转接联盟域之间都不起作用。
        - 呼叫转接方案是更有限的。
        - 限制可以应用于联盟通信。
- 给定此非对称的体验，在跨内部部署方案之间的内部部署用户和云用户的呼叫功能的正式支持不在本地目录中仅限于仅对等。 
    - 呼叫转接、 转接呼叫的队列，不支持这些用户之间等。
    - 这些不受支持的呼叫方案仍会显示已启用，但在许多情况下它们将失效不可预知的方式。 
    - 在**[图 D](#figure-d)** 上面，用户电子内部部署，并将只能作为对等支持与 A、 B 或 C 的用户的呼叫。 （与用户 D 的呼叫不会支持限制。） 但是，在本地用户 E 移到云之后，此限制不再适用。
- 如果您有多个部署 Skype 业务服务器 2019年环境中，可以配置的这些部署仅为 1 为使用组织的自动助理，因为该功能需要 Skype Business Server 混合配置。 
- 可调整的一些前面的步骤顺序。 必须满足的主要要求是，如果所有这些都是，则返回 true:
    - 多个本地 Skype 的业务林同步到单个 AAD 租户
    - 与一个内部部署林中启用拆分域
    - 混合组织中的至少一个用户已迁移到云中<br>   然后，您*必须*禁用所有其他联机 SIP 域从业务林的任何其他本地 Skype。 否则，在其他组织中的混合组织和本地用户 online 用户之间的联盟将中断一个方向。

## <a name="implications"></a>含义

- 有限制以支持高级呼叫功能如上所述，因为**组织应视为这些非对称状态暂时迁移的一部分和不稳定状态为使用这些**。  
- 以便整合可以继续，与业务部署多个本地 Skype 的组织通常应开始可以完全迁移到云的部署。 了解在某些情况下将会出现的某些用户组为其它尚未可行将移动到团队 holdouts。 如果是在方案中涉及的业务林的多个 Skype 考虑，启动迁移与不具有这些限制，如果可能的另一个林中。
- 从内部部署迁移到云，当用户具有委派关系和/或通常所涉及应作为一个整体一起移动方案的呼叫转接。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>用于移动到 TeamsOnly 模式的注意事项

混合环境中的云到本地移动用户，则可以将其移到任一 Skype 仅业务或 TeamsOnly 模式。 *如果您计划将用户移至 TeamsOnly 模式，请务必先阅读本部分。*

- 时为用户分配 TeamsOnly 模式，所有聊天室和与任何其他用户的呼叫将都位于该用户的工作组客户端中。 
- 以确保正确的路由的聊天和呼叫 TeamsOnly 用户和用户仍在 for Business 本地情况下，使用 Skype 之间您必须确保内部部署用户具有 TeamsUpgradePolicy 与其中一个 SfB 模式中，而不是群岛 （这是默认值). 
    - 为此，*您必须首先将设置您的租户全局实例 TeamsUpgradePolicy 为下列值之一*：
        - SfBWithTeamsCollab （推荐）
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 您可以使用此命令将授予租户范围的策略：<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注意： 目前，您必须执行此操作在租户范围级别因为策略不能分配给单个用户不具有联机目录中的 SIP 地址。 时为您的本地纯 deployment(s) 禁用了联机 SIP 域，这些域中的用户不会根据设计的联机目录中有 SIP 地址。 因此，将策略应用于这些内部部署用户的唯一方法是通过租户级别的分配。 相比之下，在混合部署用户将具有的 SIP 地址联机目录中以便他们可以向其明确分配策略如果需要拥有的值不同租户全局策略。
- 团队客户端 UX 不尚未遵守 TeamsUpgradePolicy SfB 的模式。 例如，在这些模式，团队中的呼叫和聊天启动是当前有可能，但将来的不会出现这种情况。 这会导致用户之间的混淆，因为答复有时可能会根据情况位于团队和 Skype for Business，有时中。 建议您单独禁用呼叫并为仍在本地用户通过 TeamsMessagingPolicy 和 TeamsCallingPolicy 聊天。

## <a name="see-also"></a>另请参阅

[更新边缘证书](cloud-consolidation-edge-certificates.md)

[更新 AAD 连接到包含多个林](cloud-consolidation-aad-connect.md)

[禁用混合完成迁移到云中](cloud-consolidation-disabling-hybrid.md)