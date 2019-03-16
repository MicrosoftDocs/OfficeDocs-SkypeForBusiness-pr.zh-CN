---
title: 仅 Teams 模式注意事项
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: 准备升级到 Microsoft 团队模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd0bf20219b8d213c354f5fc239ae3924a0d21c0
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30649385"
---
# <a name="teams-only-mode-considerations"></a>仅 Teams 模式注意事项

如果您是管理员在 Office 365 租户，现在您会看到升级为仅团队模式的 Microsoft 团队管理中心中的选项。 利用此功能可以升级各个用户，或者此外，整个租户。  

升级到团队仅模式为用户提供用于在 Office 365 中，通过单个客户端体验的团队协作的中心的 Microsoft 团队的全部好处。 此外，仅在工作组模式中的用户将接收所有呼叫和聊天团队，无论发件人是否适用于商务或团队使用 Skype 然后中受益于互操作和联合身份验证支持。

虽然成千上万客户已成功升级到 Microsoft 团队，有可能影响一路将您的组织升级时间线和用户体验的注意事项。 具体而言，具有升级选项并不一定意味着您的组织已准备好进行此更改。 为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。 

> [!IMPORTANT]
> 如果您刚开始升级规划，请务必查看我们完全升级指南和规划资源。 [从这里开始](upgrade-introduction.md)。 

**共存注意事项**： 已使用 Skype 业务 online 和/或 Skype 的业务服务器可以将团队引入满足他们的需求的步调其环境的组织。 组织可以增量推出团队到一组所需的用户根据需要，使用团队的用户通信与用户使用 Skype for Business，反之亦然。 若要管理此体验，管理员使用共存模式，定义的最终用户客户端体验，传入的路由行为聊天和呼叫，以及是否将新会议安排在团队或 for Business 的 Skype。 如果用户升级到**团队仅**;，用户可以与其他组织中用户联盟但是，当两个用户使用团队提供最佳体验。 升级到仅团队的用户仍可以加入 Skype 业务会议。 

> [!NOTE]
> 升级到仅团队的用户无法与使用 Skype 使用者的用户通信。

> [!IMPORTANT]
> 有关共存的详细信息请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 

**租户范围注意事项**： 我们正在在以下环境; 启用团队但是，现在，管理员不应升级其组织中的任何用户如果业务租户其 Skype 承载于以下环境之一：

 - 政府社区云高
 - 政府社区云 DoD
 - Office 365 由 21Vianet
 - Office 365 德国
 - Skype 业务租户位于韩国**和**组织需要团队数据存储中韩国。 当前，与 Skype 的业务数据存储在韩国升级到团队的组织将具有的亚洲数据中心区域，不在韩国数据中心区域中存储其团队数据。

**特定于用户的注意事项**： 一些用户方案仍在发展，以及管理员可以决定暂时将组织中的其他用户升级时推迟升级的特定用户。 我们正在努力解决这些方案;请监视通知的[Office 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap)网站。

| 应用场景 | 备注 |
|----------|-------|
|用户的主工作设备已 Mac，并且用户需要请参阅在 Outlook 中的同事 availability。 | 团队中的 outlook 状态尚不完全支持的 Mac 设备。 |
| 用户定期举行会议与客户或不同的国际区域中的外部合作伙伴。 | 其租户位于不同的地理位置的外部与会者看不到 IM 聊天**联合**会议中。 参与者仍可以加入会议作为匿名用户。 |
| 用户执行 Skype 业务广播的会议。 |  时团队 live 事件 （替换 Skype 广播） 已在公共预览，此用户可能需要总体可用性团队 live 事件之前一直保持 for Business 的 Skype 上。
| 用户的主设备是基于 VDI。 | |
|||

> [!IMPORTANT]
> **记住**： 移动到团队大于技术迁移。 成功升级评估技术的准备情况和最终用户准备情况。 查看业务我们 Skype 到团队[升级指南](upgrade-framework.md)规划实现升级到团队的详细信息。  
