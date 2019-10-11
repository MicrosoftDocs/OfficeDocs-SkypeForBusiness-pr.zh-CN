---
title: 仅 Teams 模式注意事项
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 准备升级到 "仅 Microsoft 团队" 模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81609298a580594e8c54d185d7dea3be86824139
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435107"
---
# <a name="teams-only-mode-considerations"></a>仅 Teams 模式注意事项

如果你是 Office 365 租户上的管理员，则你现在将在 Microsoft 团队管理中心中看到 "升级到仅团队" 模式的选项。 利用此功能，你可以升级单个用户，或者升级整个租户。  

升级到 "仅团队" 模式可为用户提供 Microsoft 团队的全部好处，即 Office 365 中团队协作的全部好处，通过单个客户端体验。 此外，"仅工作组" 模式中的用户将收到团队中的所有通话和聊天，无论发件人是使用 Skype for Business 还是团队，都可以通过互操作和联合支持获得好处。

虽然数以千计的客户成功升级到 Microsoft 团队，但仍有可能会影响组织的升级时间线和用户体验。 特别是，选择升级选项并不一定意味着你的组织已准备好进行此更改。 为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。 

> [!IMPORTANT]
> 如果您刚刚开始升级规划，请务必查看我们的完整升级指南和规划资源。 [从这里开始](upgrade-start-here.md)。 

**共存注意事项**：已使用 Skype For business Online 和/或 Skype For business 服务器的组织可以按满足其需求的节奏将团队引入到其环境中。 组织可以根据需要以增量方式向所需的一组用户推出团队，并且使用团队的用户可以与使用 Skype for Business 的用户进行通信，反之亦然。 为管理此体验，管理员使用共存模式，这些模式定义了最终用户客户体验、传入聊天和通话的传送行为，以及团队或 Skype for business 中是否安排新会议。 如果用户仅升级到**团队**，则用户可以与其他组织中的用户联盟;但是，当两个用户都使用团队时，将提供最佳体验。 已升级到团队的用户仍可加入 Skype for Business 会议。 

> [!NOTE]
> 升级到团队的用户仅无法与使用 Skype for 消费者的用户通信。

> [!IMPORTANT]
> 有关共存的更多详细信息，请参阅[了解 Microsoft 团队和 Skype for business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 

**租户范围内的注意事项**：我们正在致力于在以下环境中启用团队;但是，现在，如果其 Skype for Business 租户托管在以下环境之一中，则管理员不应升级其组织中的任何用户：

 - 政府社区云高
 - 政府社区云 DoD
 - 由世纪互联运营的 Office 365
 - Office 365 德国
 - Skype for business 租户托管于韩国 **，** 组织要求团队数据存储在韩国。 目前，存储在韩国的 Skype for business 数据的组织将其团队数据存储在亚洲数据中心区域，而不是在韩国数据中心区域中。

**特定于用户的注意事项**：某些用户方案仍在发展，管理员可能决定在升级组织中的其他用户时临时推迟某些用户的升级。 特别是，我们仍在针对其主要设备基于 VDI 的用户处理方案。 请监控[Office 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap)网站，了解公告。

> [!NOTE]
> 在移动到 "仅团队" 模式之前，你需要替换或更新不支持团队的设备。 

> [!IMPORTANT]
> **请记住**：迁移到团队不仅仅是技术迁移。 成功的升级会评估技术准备和最终用户准备情况。 查看我们的 Skype for Business 到团队[升级指南](upgrade-framework.md)，了解有关规划实施团队升级的详细信息。  
