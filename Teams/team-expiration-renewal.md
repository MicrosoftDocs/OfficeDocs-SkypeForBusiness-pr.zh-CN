---
title: Microsoft Teams 中的团队过期和续订
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解团队过期和续订，以及如何使用 Microsoft 365 组过期策略自动清理 Microsoft Teams 中未使用的团队。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809402"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams 中的团队过期和续订

具有大量团队的组织通常拥有从未真正使用过的团队。 发生这种情况的原因有多种，包括产品试验、短期团队协作或团队所有者离开组织。 随着时间的推移，此类团队可能会不断累积，给租户资源带来负担。  

若要减少未使用的团队数，作为管理员，可以使用 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 组过期策略自动清理未使用的团队。 由于团队由组支持，因此组过期策略也会自动应用于团队。

向团队应用过期策略时，团队所有者将在团队到期日期之前 30 天、15 天和 1 天收到有关团队续订的通知。 当团队所有者收到通知时，他们可以在团队设置中单击"立即续订"以续订团队。

![在团队设置中续订团队的"立即续订"按钮的屏幕截图](media/team-expiration.png "在团队设置中续订团队的"立即续订"按钮的屏幕截图")

如果团队所有者未续订团队，并且直到过期策略结束，团队不再有进一步的活动，则团队将置于"软删除"状态，这意味着它可以在接下来 30 天内还原。

## <a name="team-auto-renewal"></a>团队自动续订

有时，团队所有者可能因为忘记续订或续订到期时离开而无法续订团队。 在这些情况下，由于适用于该团队的过期策略，可能会删除使用中的团队。  

为了防止意外删除，会自动为组过期策略中的团队启用自动续订。 设置组过期策略后，在过期日期之前至少具有任何团队成员的一个频道访问的任何团队都会自动续订，无需团队所有者的任何手动干预。

## <a name="known-issues"></a>已知问题

**团队和基础组的到期日期不匹配**

在续订团队之前，先续订支持团队的组。 作为续订的一部分，将组上设置新的到期日期，以在将来的日期。 此新日期可能不会立即显示在 Teams 中。 同步可能最多需要 24 小时。如果发现团队及其基础组的到期日期存在差异，请等待 24 小时，然后寻求进一步支持。
