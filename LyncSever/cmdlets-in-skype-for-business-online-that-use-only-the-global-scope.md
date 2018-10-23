---
title: 仅使用全局作用域的 Cmdlet
TOCTitle: 仅使用全局作用域的 Cmdlet
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56271118
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 仅使用全局作用域的 Cmdlet

 

_**上一次修改主题：** 2015-06-22_

许多 Skype for Business Online 设置仅在*全局作用域*可用。这意味着有单个设置集合适用于分配给该租户的所有用户。（每个租户都具有自己独特的全局设置集合。）当您使用限制为全局作用域的 cmdlet 时，Identity 参数是可选的。例如，要检索会议配置设置，您可以使用此命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，您可以忽略 Identity 参数并使用这个较为简单的命令：

    Get-CsMeetingConfiguration

由于仅存在一个会议配置设置全局集合，两个命令将返回完全相同的信息。当使用其中一个 **Set-Cs** cmdlet 时，也可以忽略 Identity 参数。这两个命令是相同的：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

两个命令是相同的，因为默认情况下，如果您不包括 Identity 参数，Windows PowerShell 将修改全局集合。

以下 cmdlet 仅在全局作用域操作：

  - [Get-CsImFilterConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsImFilterConfiguration)

  - [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration)

  - [Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

  - [Get-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantPublicProvider)

  - [Remove-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsVoicePolicy)

  - [Set-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingConfiguration)

  - [Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

请注意，**Remove-CsVoicePolicy** cmdlet 是一个异常。首先，此 cmdlet 要求您包括 Identity 参数：

    Remove-CsVoicePolicy -Identity "global"

其次，**Remove-CsVoicePolicy** cmdlet 实际上不删除全局语音策略；Skype for Business Online 不允许您删除全局策略或配置设置。该 cmdlet 执行的操作使您能够将全局语音策略中的所有属性重置为其默认值。例如，默认情况下，AllowCallForwarding 属性设置为 False。但是，AllowCallForwarding 可能已修改，值现在在设置为 True。当您运行 **Remove-CsVoicePolicy** cmdlet 时，AllowCallForwarding 属性将恢复为默认值：False。 下表总结了此情形：


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
<td><p>全局策略修改之后</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p><strong>Remove-CsVoicePolicy</strong> cmdlet 运行之后</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[标识、作用域和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

