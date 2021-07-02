---
title: 从 Teams 探索试用版升级
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: ''
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 将用户从 Teams 探索试用版升级到付费许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: a57a34d23cc779efd1c6c596bc27f2e23d968e89
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230701"
---
# <a name="upgrade-users-from-the-teams-exploratory-trial"></a>从 Teams 探索试用版升级用户

本文概述了如何将用户从 Teams 探索试用版升级到付费 Teams 许可证。

- [步骤 1：何时升级](#step-1-when-to-upgrade)

- [步骤 2：选择升级路径](#step-2-choose-an-upgrade-path)

- [步骤 3：分配付费许可证](#step-3-assign-paid-licenses)

## <a name="step-1-when-to-upgrade"></a>步骤 1：何时升级  

要检查组织的 Teams 探索试用版何时到期以及有多少活跃用户，请在 Microsoft 365 管理中心内转到“**计费”>** <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">“<b>你的产品</b>”</a>。 在 Teams 探索试用版到期之前，你还将收到通知。

> [!IMPORTANT]
> 应当制定计划，以在到期日期之前将用户升级到付费许可证，以免用户失去对 Teams 的访问权限。
>
> 用户在试用版到期日期后 30 天时将失去对 Teams 的访问权限。 只要在到期日期后 60 天内为用户分配付费许可证，他们就可以重新获得对 Teams 的访问权限，并且所有内容仍然存在。 但 60 天后将删除用户的数据。 向用户分配新许可证以启用 Teams 功能后，如果他们是在宽限期内添加的，则保留所有内容。 有关详细信息，请参阅 <a href="/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide" target="_blank">我的订阅结束后对我的数据和访问权限有何影响？</a>

## <a name="step-2-choose-an-upgrade-path"></a>步骤 2：选择升级路径

根据组织当前拥有的订阅，有三种方法可以从 Microsoft Teams 探索试用版升级到付费许可证：

- **升级现有 Microsoft 365 订阅。** 如果组织具有不包括 Teams 在内的其他 Office 产品订阅，请使用此选项。 有关详细信息，请参阅 <a href="/microsoft-365/commerce/subscriptions/upgrade-to-different-plan?view=o365-worldwide" target="_blank">升级到其他商业计划</a>。 要查看现有订阅的活动用户，请在 Microsoft 365 管理中心中转到“**用户”>**<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">“<b>活动用户</b>”</a>。

- **将用户添加到现有 Microsoft 365 订阅。** 如果你的组织未支付足够的费用，请使用此选项。 涵盖 Teams 探索用户的 Teams 许可证。 有关详细信息，请参阅 <a href="/microsoft-365/commerce/licenses/buy-licenses?view=o365-worldwide" target="_blank">购买或删除许可证</a>。 要将用户添加到已有足够可用许可证的现有订阅，请参阅 <a href="/microsoft-365/commerce/subscriptions/move-users-different-subscription?view=o365-worldwide" target="_blank">将用户移动到其他订阅</a>。 要查看现有订阅的活动用户，请在 Microsoft 365 管理中心中转到“**用户”>**<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">“<b>活动用户</b>”</a>。

- **购买新的 Microsoft 365 订阅。** 如果你的组织没有任何 Office 产品的现有订阅，或者要购买不同于其现有订阅的订阅来涵盖 Teams 探索用户，请使用此选项。  有关详细信息，请参阅 <a href="/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide%22%20\#buy-a-different-subscription" target="_blank">购买其他 Microsoft 365 商业订阅</a>。

如果不确定要升级到哪个 Microsoft 365 订阅，请参阅 <a href="https://www.microsoft.com/microsoft-365/business#coreui-heading-hiatrep" target="_blank">Microsoft 365 商业版</a>。 如果需要其他帮助来选择订阅，或者组织需要超过 300 个许可证，请联系 <a href="https://www.microsoft.com/solution-providers/home" target="_blank">Microsoft 合作伙伴</a> 或 Microsoft 帐户代表。

## <a name="step-3-assign-paid-licenses"></a>步骤 3：分配付费许可证

> [!IMPORTANT]
> 在取消分配任何 Teams 探索许可证之前，请将新许可证分配给要升级的所有用户。 否则，在分配付费许可证之前，他们将失去对 Teams 的访问权限。  

要分配新获取的许可证，请参阅 <a href="/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide&viewFallbackFrom=o365-worldwide%22%20%5C" target="_blank">向用户分配许可证</a>。  

分配新许可证后，取消分配 Teams 探索许可证。 有关详细信息，请参阅 <a href="/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide" target="_blank">取消向用户分配的许可证</a>。

### <a name="auto-claim-policies"></a>自动声明策略

下次升级时，使用自动声明策略为组织创建策略，以自动将付费订阅中的许可证分配给尚未获取 Teams 许可证的新用户。 有关详细信息，请参阅 <a href="/microsoft-365/commerce/licenses/manage-auto-claim-policies?view=o365-worldwide" target="_blank">管理自动声明策略</a>。

## <a name="related-topics"></a>相关主题

- [管理 Microsoft Teams 探索许可证](teams-exploratory.md)
