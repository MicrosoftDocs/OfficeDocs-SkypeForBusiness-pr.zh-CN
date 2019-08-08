---
title: Skype for Business Online 中使用全局范围和标记范围的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233097"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Skype for Business Online 中使用全局范围和标记范围的 cmdlet

 


在 Skype for Business Online 中, 可以在*全局范围内*或在*标记作用*域 (或*每用户范围*) 内配置策略。 使用**Cs** cmdlet 时, 无需指定范围或标识。 如果您调用其中一个 cmdlet 且不带任何参数, 则将返回所有相关项。 例如, 此命令将返回有关所有外部访问策略的信息:

    Get-CsExternalAccessPolicy

如果要限制返回的数据, 只需包含 Identity 参数或 Filter 参数。 例如, 若要仅返回全局策略, 请使用以下命令:

    Get-CsExternalAccessPolicy -Identity "global"

若要返回具有 "RedmondAccessPolicy" 标识的每用户策略, 请使用以下命令:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 引用每用户策略时, 标记<STRONG>前缀</STRONG>是可选的。 此语法 (包括前缀) 也有效:<BR>CsExternalAccessPolicy-Identity "tag: RedmondAccessPolicy"



若要返回除全局策略 (即所有每用户策略) 之外的所有策略, 请使用以下命令:

    Get-CsExternalAccessPolicy -Filter "tag:*"

以下 cmdlet 对全局范围和每用户 (标记) 作用域进行操作:

  - [Set-csclientpolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 尽管名称、拨号计划和功能, 请说出策略。 使用 "<EM>拨号计划</EM>" 而不是 "拨号策略", 以保留早期版本的 Lync Server 所使用的术语。



## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的身份、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

