---
title: Microsoft 团队中的团队过期和续订
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解有关团队过期和续订以及如何使用 Microsoft 365 组过期策略自动清理 Microsoft 团队中未使用的团队的信息。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868519"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft 团队中的团队过期和续订

具有大量团队的组织通常会有团队，这些团队永远不会真正使用。 出现这种情况的原因有多种，其中包括产品实验、短期团队协作或团队所有者离开组织。 随着时间的推移，此类团队可以积累和创造对租户资源的负担。  

若要将未使用的团队的数量与管理员进行路管理，您可以使用[Microsoft 365 组过期策略](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)自动清理未使用的团队。 由于团队由组支持，组过期策略也会自动应用到团队。

当你将过期策略应用到团队时，团队所有者将在团队的到期日期之前的30天、15天和1天内收到团队续订通知。 当团队所有者收到通知时，他们可以单击 "团队设置" 中的 "**立即续订**" 以续订团队。

!["立即续订" 按钮的屏幕截图，用于在团队设置中续订团队](media/team-expiration.png ""立即续订" 按钮的屏幕截图，用于在团队设置中续订团队")

如果团队所有者不续订团队，则会将团队置于 "软删除" 状态，这意味着它可以在未来30天内还原。

## <a name="team-auto-renewal"></a>团队自动续订

有时团队所有者无法续订团队，可能是因为他们忘记续订或在续订到期时离开。 在这些情况下，由于适用于团队的过期策略，活动团队可能会被删除。  

为了防止意外删除，将自动为组过期策略中的团队启用自动续订。 设置组过期策略时，在其到期日期之前至少拥有一个频道访问的任何团队将自动续订，并且不会与团队所有者进行任何手动干预。

## <a name="known-issues"></a>已知问题

**团队和基础组的到期日期不匹配**

在续订团队之前，先续订支持团队的组。 作为续订的一部分，将在组中为未来日期设置新的到期日期。 在团队中，此新日期可能不会立即显示。 同步最多可能需要24小时。如果你看到团队及其基础组的到期日期之间的差异，请等待24小时，然后再寻求进一步支持。
