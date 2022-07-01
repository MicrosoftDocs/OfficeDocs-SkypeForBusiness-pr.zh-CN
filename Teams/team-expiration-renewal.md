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
ms.collection:
- M365-collaboration
description: 了解团队过期和续订，以及如何使用 Microsoft 365 组过期策略自动清理 Microsoft Teams 中未使用的团队。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564170"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams 中的团队过期和续订

拥有大量团队的组织通常具有从未实际使用的团队。 这种情况可能由于多种原因而发生，包括产品试验、短期团队协作或团队所有者离开组织。 随着时间的推移，此类团队可能会累积并给租户资源带来负担。  

若要限制未使用的团队数目，作为管理员，可以使用 [Microsoft 365 组过期策略](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) 自动清理未使用的团队。 由于团队由组提供支持，因此组过期策略也会自动应用于团队。

向团队应用过期策略时，团队所有者会在团队过期日期前 30 天、15 天和 1 天收到团队续订通知。 当团队所有者收到通知时，他们可以立即在团队设置中单击 **“续订** ”以续订团队。

![在团队设置中续订团队的“立即续订”按钮的屏幕截图。](media/team-expiration.png "在团队设置中续订团队的“立即续订”按钮的屏幕截图")

如果团队所有者没有续订团队，并且在到期策略结束之前团队中没有进一步的活动，则团队将处于“软删除”状态，这意味着可以在未来 30 天内还原该团队。

## <a name="team-auto-renewal"></a>团队自动续订

有时，团队所有者可能因为忘记续订或在续约到期时离开而无法续订球队。 在这些情况下，由于适用于团队的过期策略，主动使用的团队可能会被删除。  

为了防止意外删除，组过期策略中的团队会自动启用自动续订。 设置组过期策略后，任何团队成员在到期日期之前至少访问过一个频道的团队都会自动续订，而无需团队所有者的任何手动干预。

## <a name="known-issues"></a>已知问题

**团队和基础组的到期日期不匹配**

在续订团队之前，将首先续订支持团队的组。 作为续订的一部分，将在组上为将来的日期设置新的到期日期。 此新日期可能无法在 Teams 中立即显示。 最多可能需要 24 小时才能同步。如果发现团队的到期日期与其基础组之间存在差异，请等待 24 小时，然后再寻求进一步的支持。