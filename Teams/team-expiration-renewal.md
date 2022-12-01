---
title: Microsoft Teams 中的团队过期和续订
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
description: 了解团队过期和续订，以及如何使用 Microsoft 365 组过期策略自动清理 Microsoft Teams 中未使用的团队。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4f56c8cbb2d25b05d6c87fa2862e56244d6b9c8
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198794"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams 中的团队过期和续订

拥有大量团队的组织通常具有从未实际使用过的团队。 出现这种情况的原因有多种，包括产品试验、短期团队协作或团队所有者离开组织。 随着时间的推移，此类团队可能会累积并给租户资源带来负担。  

若要限制未使用团队的数量，管理员可以使用 [Microsoft 365 组过期策略](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)自动清理未使用的团队。 由于团队由组提供支持，因此组过期策略也会自动应用于团队。

向团队应用过期策略时，团队所有者会在团队到期日期前 30 天、15 天和 1 天收到团队续订通知。 当团队所有者收到通知时，他们可以在团队设置中单击“ **立即续订** ”来续订团队。

![用于在团队设置中续订团队的“立即续订”按钮的屏幕截图。](media/team-expiration.png "用于在团队设置中续订团队的“立即续订”按钮的屏幕截图")

如果团队所有者未续订团队，并且团队在过期策略结束之前没有进一步的活动，则团队将处于“软删除”状态，这意味着它可以在未来 30 天内还原。

## <a name="team-auto-renewal"></a>团队自动续订

有时，团队所有者可能无法续订团队，可能是因为他们忘记续订，或者在续订到期时离开。 在这些方案中，由于适用于团队的过期策略，活动使用中的团队可能会被删除。  

为了防止意外删除，组过期策略中会自动为团队启用自动续订。 设置组过期策略后，在到期日期之前，任何团队成员至少有一次频道访问的团队都会自动续订，而无需团队所有者进行任何手动干预。

## <a name="known-issues"></a>已知问题

**团队和基础组的到期日期不匹配**

在团队续订之前，首先会续订该团队的组。 作为续订的一部分，在组上为将来的日期设置新的到期日期。 此新日期可能不会立即在 Teams 中显示。 同步最长可能需要 24 小时。如果看到团队与其基础组的到期日期之间存在差异，请等待 24 小时，再寻求进一步的支持。