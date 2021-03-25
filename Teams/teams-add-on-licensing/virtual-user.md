---
title: Microsoft 365 手机系统 - 虚拟用户许可证
ms.author: dstrome
author: dstrome
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 了解如何向组织的资源帐户分配免费的电话系统-虚拟用户许可证或付费电话系统用户许可证。
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116920"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 手机系统 - 虚拟用户许可证

具有手机系统许可用户的组织可以将免费的 Microsoft 365 电话系统 - 虚拟用户许可证或付费电话系统用户许可证分配给资源帐户。 呼叫计划不是必需的。 所有自动助理或呼叫队列都需要关联的资源帐户。 需要电话号码的资源帐户需要免费的 Microsoft 365 电话系统 - 虚拟用户许可证或付费电话系统用户许可证，才能将电话号码应用到资源帐户。

> [!TIP]
> 对于将用于嵌套自动助理或未分配电话号码的呼叫队列的资源帐户，不需要许可证。 有关参考，请参阅下图： 

![虚拟用户许可证](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>虚拟用户许可证分配

为组织分配 Microsoft 365 Phone System - 虚拟用户许可证，具体取决于其整体大小。 具有至少一个许可证（包括电话系统）或已添加电话系统的任何组织都提供 25 个虚拟用户许可证，无需付费。 在组织中添加 10 个电话系统用户许可证后，再添加一个 Microsoft 365 电话系统 - 虚拟用户许可证将变为可用。

> [!NOTE]
> 电话系统是 Microsoft 365 和 Office 365 E1 和 E3 提供的附加许可证。 电话系统也作为 Microsoft 365 E5、Office 365 E5 和 Microsoft 365 商业语音许可证的一部分包括在内。

如果你的组织在创建自动助理或呼叫队列节点时使用了可用的免费 Microsoft 365 电话系统 - 虚拟用户许可证，则仍可将付费电话系统许可证与资源帐户一同使用。 大多数组织将基于缩放计划拥有足够的虚拟用户许可证。 

### <a name="license-allocation-example"></a>许可证分配示例

Contoso， Inc. 购买了 600 个许可证，其中包括电话系统 (每个员工一) 。 Contoso 分配了初始 25 + 60 Microsoft 365 Phone System – 虚拟用户许可证，总共 85 个。 其组织有 90 个呼叫队列和具有电话号码的自动助理。 他们需要分配所有 Microsoft 365 手机系统 - 虚拟用户许可证，并获取五个常规价格的手机系统许可证。

Contoso 应考虑重新设计自动助理和呼叫队列系统。 如果他们使用的电话号码较少，嵌套的节点也更多，并且不需要电话号码，则简化实现并降低成本。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>如何购买 Microsoft 365 手机系统 - 虚拟用户许可证

1. 登录到 Microsoft 365 管理中心。
2. 转到 **计费**  >  **购买服务**  >  **附加内容**
3. 滚动到末尾，找到 **"Microsoft 365 手机系统 - 虚拟用户"** 许可证。 选择"**立即购买"。**

> [!NOTE]
> 请记住，即使许可证的成本  **为零** ，仍必须购买许可证。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>更改现有资源帐户以使用 Microsoft 365 电话系统 - 虚拟用户许可证

如果决定将资源帐户上的许可证从电话系统许可证切换到 Microsoft 365 电话系统 - 虚拟用户许可证：

1. 获取新的 Microsoft 365 手机系统 - 虚拟用户许可证。
2. 按照 Microsoft 365 管理中心中的链接步骤将[用户移到其他订阅。](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> 始终删除完整的手机系统许可证，并在同一许可证活动中分配 Microsoft 365 手机系统 - 虚拟用户许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再正常运行。 如果发生这种情况，建议为 Microsoft 365 手机系统 - 虚拟用户许可证创建新的资源帐户，并删除损坏的资源帐户。 

## <a name="related-information"></a>相关信息

[自动助理和呼叫队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)