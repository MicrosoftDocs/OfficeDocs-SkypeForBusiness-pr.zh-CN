---
title: 在Teams中管理一线试用版
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何为组织一线工作人员设置为期 90 天的Teams试用版。
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758291"
---
# <a name="manage-the-frontline-trial-in-teams"></a>在Teams中管理一线试用版

> [!NOTE]
> 此试用体验即将推出。 可以通过在Microsoft 365 管理[中心的消息中心](https://go.microsoft.com/fwlink/p/?linkid=2070717)查找消息来检查组织何时可以使用此信息。

Microsoft Teams一线试用体验允许组织中Teams的用户为整个一线团队启动Teams体验，只要其他成员Azure Active Directory (Azure AD) 。 可以使用 [AllowSelfServicePurchase PowerShell 模块](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)为组织中的用户禁用此功能。

## <a name="what-services-are-included"></a>包括哪些服务

试用版包含[Microsoft 365 F3许可证](https://www.microsoft.com/microsoft-365/enterprise/f3)中的所有内容，但存在以下异常：

- 前线审判包括Exchange基金会，而不是Exchange展台。 由于此更改，用户可能缺少其他Teams功能。

## <a name="eligibility"></a>资格

> [!NOTE]
> 可以通过在Microsoft 365 管理[中心的消息中心](https://go.microsoft.com/fwlink/p/?linkid=2070717)查找公告来检查组织是否属于试用试点。 组织需要成为试用试点的一部分，用户才能启动或参与试用版。 本优惠不适用于 GCC、GCC High、DoD 或 EDU 客户。

一线试用版每个试用版最多可容纳 300 个用户。

如果用户：

- 有一个活动许可证，允许他们访问Teams。
- 以前还没有开始一线工作人员试用。

> [!IMPORTANT]
> 如果启动试用版的用户在试用期结束前离开你的组织，你作为管理员将需要监视试用版，与团队联系，看看谁从这些功能中获益，并决定需要升级到付费许可证的用户。

如果用户具有托管Azure Active Directory域电子邮件地址，则可以参与一线工作者试用版。

如果用户以前已启动试用版，但无法启动另一个试用版，则可以参与。

> [!NOTE]
> 没有现有Teams访问权限的用户只能在团队创建时添加到试用团队。 创建团队后，仍可将现有Teams用户添加到试用版中。

## <a name="set-up-the-trial"></a>设置试用版

符合条件的用户可以通过从桌面或 [Web 应用](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks)Teams登录到 Tasks 应用来启动一线试用版。 目前，不支持通过移动方式启动一线试用版。 启动试用版后，将自动为整个团队分配一线试用版许可证。 拥有现有付费许可证的用户，可以访问Teams也将分配试用许可证，但在整个试用期内将保留其现有许可证的功能，并在试用结束后保留其现有的付费许可证。 开始试用的用户将在试用过程中收到电子邮件通知。

## <a name="manage-the-frontline-trials-experience"></a>管理一线试用体验

管理员可以使用 **AllowSelfServicePurchase** PowerShell 模块阻止最终用户在其组织内启动一线试用版。 这仅适用于试用许可证。 [了解如何使用 AllowSelfServicePurchase PowerShell 模块](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)。

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>为拥有一线试用版许可证的用户管理Teams

你可以管理拥有一线试用版许可证的用户，就像管理具有常规付费许可证的用户一样。 有关详细信息，请参阅[为你的组织管理 Teams 设置](/microsoftteams/manage-teams-overview)。

### <a name="remove-a-trial-license"></a>删除试用许可证

可以通过 PowerShell 或Microsoft 365 管理中心删除一线试用版许可证。

[了解如何使用 PowerShell 删除](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。

[了解如何在管理中心中删除](/microsoft-365/admin/add-users/delete-a-user)。

## <a name="upgrade-users-from-frontline-trial"></a>从一线试用版升级用户

当试用期结束时，用户可能会与你联系以请求许可证。 需要管理员权限才能升级用户。

### <a name="when-to-upgrade"></a>何时升级

在 90 天试用期接近尾声时，需要与用户核实，看看谁需要继续使用付费许可证。 请务必在一线试用版订阅过期之前执行此操作，以避免对用户体验造成任何干扰。

> [!IMPORTANT]
> 如果一线试用版许可证结束，并且未立即为用户分配包含Teams的许可证，他们将失去对Teams的访问权限。 30 天后，它们的数据 (文件、消息和更多) 被删除。 用户仍存在于 Azure Active Directory 中。 如果将新许可证分配给用户以在 30 天内启用Teams功能，则其所有内容Teams仍将存在。

### <a name="choose-an-upgrade-path"></a>选择升级路径

> [!TIP]
> 前线试用版基于[Microsoft 365 F3许可证](https://www.microsoft.com/microsoft-365/enterprise/f3)。

根据组织当前拥有的订阅，有三种方法可以从一线试用版升级到付费许可证：

- **升级现有 Microsoft 365 订阅。** 如果组织具有不包括 Teams 在内的其他 Office 产品订阅，请使用此选项。 有关详细信息，请参阅 [升级到其他计划](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan)。 若要查看现有订阅的活动用户，请转到 **用户>** Microsoft 365 管理中心中的 [活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822)。

- **将用户添加到现有 Microsoft 365 订阅。** 如果你的组织没有足够的付费Teams许可证来覆盖你的一线团队，请使用此选项。 有关详细信息，请参阅 [购买或删除许可证](/microsoft-365/commerce/licenses/buy-licenses)。 要将用户添加到已有足够可用许可证的现有订阅，请参阅 [将用户移动到其他订阅](/microsoft-365/commerce/subscriptions/move-users-different-subscription)。 若要查看现有订阅的活动用户，请转到 **用户>** Microsoft 365 管理中心中的 [活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822)。

- **购买新的 Microsoft 365 订阅。** 如果你的组织没有任何现有订阅来Office产品，或者你的组织想要购买不同于其现有订阅的订阅来覆盖一线用户，请使用此选项。 有关详细信息，请参阅[一线工作人员Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline)。

如果不确定要升级到哪个Microsoft 365订阅，请参阅[一线工作人员的Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline)。 如果需要其他帮助来选择订阅，或者组织需要超过 300 个许可证，请联系 [Microsoft 合作伙伴](https://www.microsoft.com/solution-providers/home) 或 Microsoft 帐户代表。

### <a name="assign-paid-licenses"></a>分配付费许可证

要分配新获取的许可证，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。  

分配新许可证后，取消分配 Teams 探索许可证。 有关详细信息，请参阅 [取消向用户分配的许可证](/microsoft-365/admin/manage/remove-licenses-from-users)。

## <a name="faq"></a>常见问题

**试用期持续多久** <br>
前线审判持续90天。

**在 90 天的前线试用体验结束时，管理员应该怎么做？** <br>
在 90 天的试用期结束时，需要与用户核实，看看谁需要继续使用付费许可证。 然后，需要 [升级用户](#upgrade-users-from-frontline-trial)。

**如果启动试用版的用户离开你的组织，会发生什么情况？** <br>
你作为管理员需要监视 90 天剩余时间的试用版，并在试用期结束后升级到需要试用版的用户的付费许可证。

**什么是数据保留策略？** <br>
可以从[Microsoft 365订阅信息](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?)中了解数据保留。

**如果用户在启动前线试用版时遇到错误，该怎么办？** <br>
确保组织、开始试用的用户以及添加到试用版中的用户符合 [资格标准](#eligibility)。