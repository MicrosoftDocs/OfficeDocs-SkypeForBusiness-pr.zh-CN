---
title: Lync Online：Lync Online cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Lync Online cmdlets
ms:assetid: 1d85a61f-80e5-49c6-be7f-971ff5fe4dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994021(v=OCS.15)
ms:contentKeyID: 51803930
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc8a5c1868620446af3fe574db7af10aa8b34785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-online-cmdlets"></a>Lync Online cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-07_

此页面列出了 Microsoft Lync Online 租户的管理员可用的所有 Windows PowerShell cmdlet。

<div>

## <a name="cmdlets-available-only-to-lync-online-administrators"></a>仅适用于 Lync Online 管理员的 cmdlet

以下 cmdlet 只能与 Lync Online 一起使用：

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ994030(v=OCS.15))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15))

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/JJ994044(v=OCS.15))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/JJ994072(v=OCS.15))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/JJ994034(v=OCS.15))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/Dn362770(v=OCS.15))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/JJ994016(v=OCS.15))

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/JJ994088(v=OCS.15))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/JJ994023(v=OCS.15))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/JJ994040(v=OCS.15))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/JJ994080(v=OCS.15))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/JJ994046(v=OCS.15))

  - [Set-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/JJ994047(v=OCS.15))

  - [Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))

有关如何将计算机配置为使用 Windows PowerShell 管理 Lync Online 的信息，请参阅[使用 Windows Powershell 管理 Lync online](https://technet.microsoft.com/en-us/library/Dn362831(v=OCS.15))中的帮助主题。

</div>

<div>

## <a name="other-cmdlets-available-to-lync-online-administrators"></a>Lync Online 管理员可用的其他 Cmdlet

这些 cmdlet 既可以与 Lync Online 一起使用，也可以与 Lync Server 2013 的本地版本一起使用：

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - [CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))

  - [CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - [Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))

  - [CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))

  - [授权-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - [授权-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - [授权-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))

  - [授权-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))

  - [Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))

  - [Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))

  - [Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

  - [Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))

  - [Set-Move-csuser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

