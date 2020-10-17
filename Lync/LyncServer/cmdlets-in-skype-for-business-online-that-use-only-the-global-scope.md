---
title: 仅使用全局范围的 Skype for business Online 中的 cmdlet
description: 仅使用全局范围的 Skype for Business Online 中的 cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f59806128ceea825a4cdd966e85852b98079b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545598"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>仅使用全局范围的 Skype for business Online 中的 cmdlet

 


许多 Skype for Business Online 设置仅在 *全局范围内*可用。 这意味着，有一个设置集合，这些设置适用于分配给该租户的所有用户。  (每个租户都有自己的唯一全局设置集合。 ) 当使用限制为全局作用域的 cmdlet 时，Identity 参数是可选的。 例如，若要检索会议配置设置，可以使用以下命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，您可以省略 Identity 参数，而改为使用以下更简单的命令：

    Get-CsMeetingConfiguration

由于只有一个全局会议配置设置集合，这两个命令将返回完全相同的信息。 在使用其中一个 **Cs** cmdlet 时，也可以省略 Identity 参数。 这两个命令相同：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

这两个命令完全相同，因为默认情况下，如果不包含 Identity 参数，Windows PowerShell 将修改全局集合。

以下 cmdlet 仅在全局范围内运行：

  - [CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Set-cstenantpublicprovider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

请注意， **set-csvoicepolicy** cmdlet 是异常的一些情况。 首先，此 cmdlet 需要包含 Identity 参数：

    Remove-CsVoicePolicy -Identity "global"

其次， **set-csvoicepolicy** cmdlet 不会实际删除全局语音策略;Skype for Business Online 不允许删除全局策略或配置设置。 Cmdlet 的功能是使您能够将全局语音策略中的所有属性重置为其默认值。 例如，默认情况下，AllowCallForwarding 属性设置为 False。 但是，AllowCallForwarding 可能已修改，值现在设置为 True。 当您运行 **set-csvoicepolicy** cmdlet 时，AllowCallForwarding 属性将还原为其默认值： False。 下表总结了此方案：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 值</th>
<th>方案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>默认值</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>修改全局策略后</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>在运行 <strong>set-csvoicepolicy</strong> cmdlet 之后</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

