---
title: Microsoft Teams 中的团队到期和续订
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
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116950"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams 中的团队到期和续订

具有大量团队的组织通常拥有从未实际使用的团队。 发生这种情况的原因有多种，包括产品试验、短期团队协作或团队所有者离开组织。 随着时间的推移，此类团队可能会累积，给租户资源带来负担。  

若要减少未使用的团队数，作为管理员，可以使用 [Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 组过期策略自动清理未使用的团队。 由于团队受组支持，因此组过期策略也会自动应用于团队。

向团队应用过期策略时，团队所有者将在团队到期日期之前 30 天、15 天和 1 天收到团队续订通知。 当团队所有者收到通知时，他们可以在团队设置中单击"立即续订"以续订团队。

![在团队设置中续订团队的"立即续订"按钮的屏幕截图](media/team-expiration.png "在团队设置中续订团队的"立即续订"按钮的屏幕截图")

如果团队所有者未续订团队，且在过期策略结束之前团队中没有任何进一步的活动，则团队将置于"软删除"状态，这意味着它可以在接下来 30 天内还原。

## <a name="team-auto-renewal"></a>团队自动续订

有时，团队所有者可能因为忘记续订或续订到期时离开而无法续订团队。 在这些情况下，由于适用于该团队的过期策略，活动使用中的团队可能会被删除。  

为了防止意外删除，将自动为组过期策略中的团队启用自动续订。 设置组过期策略后，在到期日期之前至少具有任何团队成员的一个频道访问的任何团队都会自动续订，无需团队所有者的任何手动干预。

## <a name="known-issues"></a>已知问题

**团队和基础组的到期日期不匹配**

在续订团队之前，先续订支持该团队的组。 作为续订的一部分，将针对组设置新的过期日期作为未来日期。 此新日期可能不会立即显示在 Teams 中。 同步最多可能需要 24 小时。如果发现团队及其基础组的到期日期存在差异，请等待 24 小时，然后寻求进一步的支持。