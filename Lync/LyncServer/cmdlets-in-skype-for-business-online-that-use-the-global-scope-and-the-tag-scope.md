---
title: Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755072"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet

 


在 Skype for Business Online 中，可以在*全局范围*或在*标记范围*（或*每用户范围*）内配置策略。 使用**Cs** cmdlet 时，不必指定范围或标识。 如果调用其中一个不带任何参数的 cmdlet，则将返回所有相关项目。 例如，以下命令将返回有关所有外部访问策略的信息：

    Get-CsExternalAccessPolicy

如果要限制返回的数据，则需要仅包含 Identity 参数或 Filter 参数。 例如，若要仅返回全局策略，请使用以下命令：

    Get-CsExternalAccessPolicy -Identity "global"

若要返回具有标识 "RedmondAccessPolicy" 的每用户策略，请使用以下命令：

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 在引用每用户策略时，标记<STRONG>前缀</STRONG>是可选的。 此语法（包括前缀）也有效：<BR>Set-csexternalaccesspolicy – Identity "标记： RedmondAccessPolicy"



若要返回除全局策略之外的所有策略（即每个用户的所有策略），请使用以下命令：

    Get-CsExternalAccessPolicy -Filter "tag:*"

以下 cmdlet 对全局作用域和每用户（标记）作用域运行：

  - [Set-csclientpolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Set-csconferencingpolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Grant-csdialplan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Set-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 尽管名称，但在功能上讲，拨号计划是策略。 使用 "<EM>拨号计划</EM>" 来代替（例如，拨号策略），以保留旧版 Lync Server 使用的术语。



## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

