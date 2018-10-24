---
title: 使用会议提供商标识的 Cmdlet
TOCTitle: 使用会议提供商标识的 Cmdlet
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56271199
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用会议提供商标识的 Cmdlet

 

_**上一次修改主题：** 2015-06-22_

要返回有关您的组织已与其签订合同的所有音频会议提供商的信息，您可以简单地不带任何参数调用 [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider) cmdlet：

    Get-CsAudioConferencingProvider

如果想要将返回的数据限制为单个提供商（在此示例中为 Contoso Audio Services），请使用 Identity 参数：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

仅存在一个接受音频会议商 ID 的 Skype for Business Online cmdlet：

  - [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider)

## 另请参阅

#### 概念

[标识、作用域和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

