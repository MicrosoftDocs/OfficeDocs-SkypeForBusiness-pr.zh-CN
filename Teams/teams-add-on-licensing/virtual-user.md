---
title: Microsoft 365 电话系统-虚拟用户许可证
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
description: 了解如何为组织中的资源帐户分配免费的电话系统-虚拟用户许可证或付费电话系统用户许可证。
ms.openlocfilehash: 5a60e757f4ed9dbca67219217257894a8f95a295
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904784"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 电话系统-虚拟用户许可证 

具有电话系统许可用户的组织可为资源帐户分配一个免费的 Microsoft 365 Phone 系统–虚拟用户许可证或付费电话系统用户许可证。 不需要呼叫计划。 所有自动助理或呼叫队列都需要关联的资源帐户。 需要电话号码的资源帐户需要一个免费的 Microsoft 365 Phone 系统-虚拟用户许可证或付费电话系统用户许可证，然后才能将电话号码应用于资源帐户。

> [!TIP]
> 对于将与未分配电话号码的嵌套自动助理或通话队列一起使用的资源帐户，不需要许可证。 有关参考，请参阅下图： 

![虚拟用户许可证](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>虚拟用户许可证分配

您的组织已分配 Microsoft 365 手机系统-虚拟用户许可证，具体取决于其总体大小。 至少有一个许可证（包括电话系统或已添加手机系统）的任何组织均可免费使用25个虚拟用户许可证。 在你的组织中添加10个电话系统用户许可证后，另一个 Microsoft 365 Phone 系统-虚拟用户许可证将变为可用。

> [!NOTE]
> 电话系统是 Office 365 E1 和 E3 可用的附加许可证。 电话系统还包含在 Office 365 E5 和 Microsoft 365 商业语音许可证中。

如果您的组织使用可用的免费 Microsoft 365 Phone 系统-创建自动助理或呼叫队列节点的虚拟用户许可证，您仍然可以将付费电话系统许可证用于资源帐户。 大多数组织都有足够的虚拟用户许可证，具体取决于缩放计划。 

### <a name="license-allocation-example"></a>许可证分配示例

Contoso，Inc. 购买了包括电话系统的600许可证（每个员工一个）。 Contoso 已被分配了一个初始25加 60 Microsoft 365 电话系统-总共是虚拟用户许可证-85。 其组织拥有具有电话号码的90通话队列和自动助理。 他们需要分配所有 Microsoft 365 Phone 系统-虚拟用户许可证，并获得五个常规价格的电话系统许可证。 

Contoso 应考虑重新设计自动助理和呼叫队列系统。 如果他们使用较少的电话号码和更多不需要电话号码的嵌套节点，它们将简化实施并降低成本。 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>如何购买 Microsoft 365 Phone 系统-虚拟用户许可证 

1. 登录到 Microsoft 365 管理中心。
2. 转到**帐单** > **购买服务** > **加载项**
3. 滚动到 "结束" 以查找**Microsoft 365 Phone System-虚拟用户**许可证。 选择 "**立即购买**"。

> [!NOTE]
> 请记住，您仍然必须**购买**许可证，即使其成本为零。 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>将现有资源帐户更改为使用 Microsoft 365 Phone 系统–虚拟用户许可证

如果你决定将资源帐户中的许可证从电话系统许可证切换到 Microsoft 365 Phone 系统-虚拟用户许可证： 

1. 获取新的 Microsoft 365 Phone 系统-虚拟用户许可证。 
2. 按照 Microsoft 365 管理中心中的链接步骤[将用户移动到其他订阅](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)。 

> [!WARNING]
> 始终删除完整的电话系统许可证，并分配 Microsoft 365 Phone 系统-虚拟用户许可证在同一许可证活动中。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。 如果发生这种情况，我们建议你为 Microsoft 365 Phone 系统创建新的资源帐户-虚拟用户许可证并删除断开的资源帐户。 

## <a name="related-information"></a>相关信息

[自动助理和通话队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)
