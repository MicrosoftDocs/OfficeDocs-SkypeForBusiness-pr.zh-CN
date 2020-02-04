---
title: Skype for Business Online 中仅使用全局范围的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728102"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Skype for Business Online 中仅使用全局范围的 cmdlet

 


许多 Skype for Business Online 设置仅在*全局范围内*可用。 这意味着有一个设置集合，这些设置适用于分配给该租户的所有用户。 （每个租户都有自己唯一的全局设置集合。）使用限制为全局范围的 cmdlet 时，Identity 参数是可选的。 例如，若要检索会议配置设置，您可以使用此命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，你可以省略 Identity 参数，而改为使用以下更简单的命令：

    Get-CsMeetingConfiguration

由于只有一个全局会议配置设置集合，因此这两个命令将返回完全相同的信息。 使用其中一个**Set-Cs** cmdlet 时，也可以省略 Identity 参数。 这两个命令相同：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

这两个命令是相同的，因为默认情况下，如果不包含 Identity 参数，Windows PowerShell 将修改全局集合。

以下 cmdlet 仅在全局范围内运行：

  - [CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

请注意， **CsVoicePolicy** cmdlet 是异常的一些内容。 首先，此 cmdlet 需要包含 Identity 参数：

    Remove-CsVoicePolicy -Identity "global"

第二， **CsVoicePolicy** cmdlet 不会真正删除全局语音策略;Skype for business Online 不允许删除全局策略或配置设置。 Cmdlet 的用途是使你能够将全局语音策略中的所有属性重置为其默认值。 例如，默认情况下，AllowCallForwarding 属性设置为 False。 但是，AllowCallForwarding 可能已修改，值现在设置为 True。 当你运行**CsVoicePolicy** cmdlet 时，AllowCallForwarding 属性将还原为其默认值： False。 下表总结了此方案：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 值</th>
<th>应用场景</th>
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
<td><p><strong>CsVoicePolicy</strong> cmdlet 已运行后</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的身份、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

