---
title: Microsoft Teams 电话资源帐户许可证
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- admindeeplinkMAC
description: 了解如何将Microsoft Teams 电话资源帐户许可证分配给组织中自动助理和呼叫队列的资源帐户。
ms.openlocfilehash: bba516249ec1b30e0361e2f9a6be003343f9c892
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377360"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 电话资源帐户许可证

在 Microsoft Teams 中，所有自动助理和呼叫队列都需要关联的资源帐户。 必须为每个资源帐户分配 **一个Microsoft Teams 电话资源帐户** 许可证，以确保系统正确标识它们并正常运行，*而不考虑是否为资源帐户分配电话号码*。 具有包含 Teams Phone 的订阅的组织会自动分配一定数量的 **Teams 电话资源帐户** 许可证，而无需额外付费。  除非你希望能够使用该资源帐户进行拨号，否则不需要 Microsoft 呼叫计划。 有关详细信息，请参阅 [规划 Teams 自动助理和呼叫队列](../plan-auto-attendant-call-queue.md#prerequisites)。

> [!NOTE]
> 以前，仅在将电话号码分配给资源帐户时，才需要 **Teams 电话资源帐户** 许可证 (一次称为 **虚拟用户** 许可证) 。 现在，必须为所有资源帐户分配 **Teams 电话资源帐户** 许可证，而不考虑是否为其分配电话号码。 此外，请勿将 **Teams 电话标准版** 许可证分配给资源帐户。 如果当前已使用 **Teams 电话标准版** 许可证配置了资源帐户，则必须切换到 **Teams 电话资源帐户** 许可证，如下所述。
 

## <a name="resource-account-license-allocation"></a>资源帐户许可证分配

组织根据其整体大小分配 Teams **电话资源帐户** 许可证。 任何具有电话系统功能订阅的组织（例如 **，Teams 电话标准版** 和 **具有通话套餐许可证的 Teams 电话**）都可免费分配 25 个 **Teams 电话资源帐户** 许可证。 

对于组织中每 10 **个具有** 通话套餐的Teams 电话标准版或 **Teams 电话** 用户许可证，就会有一个 **Teams 电话资源帐户** 许可证可用。  根据此缩放计划，大多数组织将有足够的 **Teams 电话资源帐户** 许可证。 如果需要更多的 **Teams 电话资源帐户** 许可证，则可以通过 Microsoft 帐户代表购买超出标准分配的更多 **Teams 电话资源帐户** 许可证。

### <a name="license-allocation-example"></a>许可证分配示例

Contoso， Inc. 为每个员工) 购买了 600 个许可证，其中包括电话系统 (一个。 Contoso 分配了初始 25 个加 60 个 **Teams 电话资源帐户** 许可证，总共 85 个。 他们的组织有 90 个呼叫队列和自动助理。 他们需要分配所有 **Teams 电话资源帐户** 许可证，并购买五个额外的 **Teams 电话资源帐户** 许可证。 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>如何获取Microsoft Teams 电话资源帐户许可证

1. 登录到[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
2. 转到 **“** > 计费 [**购买服务**](https://go.microsoft.com/fwlink/p/?linkid=868433) > **”加载项**。
3. 滚动查找 **Microsoft Teams 电话资源帐户** 许可证。 **立即选择“购买**”。

   > [!NOTE]
   > 请记住，即使你在分配范围内，即使许可证的成本为零，你仍必须 **购买** 许可证。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>更改现有资源帐户以使用Microsoft Teams 电话资源帐户许可证

如果现有资源帐户使用 **Teams 电话标准版** 许可证，则必须切换到 Teams **电话资源帐户** 许可证：

1. 获取新的 **Teams 电话资源帐户** 许可证。
2. 按照Microsoft 365 管理中心中的链接步骤[将用户移动到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除 **Teams 电话标准版** 许可证，并在同一许可证活动中分配 **Teams 电话资源帐户** 许可证。 如果删除旧许可证、保存帐户更改、添加新许可证，并再次保存帐户设置，资源帐户可能不再按预期运行，例如组织的自动助理和呼叫队列不再正常工作。
>
> 如果发生这种情况，建议使用 **Teams 电话资源帐户** 许可证创建新的资源帐户，并删除损坏的资源帐户。

## <a name="related-information"></a>相关信息

[自动助理和呼叫队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)
