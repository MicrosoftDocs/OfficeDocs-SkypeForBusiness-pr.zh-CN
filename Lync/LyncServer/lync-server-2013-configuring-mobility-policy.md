---
title: Lync Server 2013：配置移动策略
description: Lync Server 2013：配置移动策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569998"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中配置移动策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供移动策略，用于确定谁可以使用移动功能、通过工作呼叫、IP 语音 (VoIP) 或视频，以及 VoIP 或视频是否需要 WiFi。 通过 "通过工作进行呼叫" 功能，移动用户可以通过使用工作电话号码而不是移动电话号码，在移动电话上拨打和接听呼叫。 此功能可防止被叫方查看呼叫者的移动电话号码，并允许用户避免出站通话费用。 配置 VoIP 和视频使用户可以接收和发出 VoIP 呼叫和视频。 WiFi 用法的设置定义用户的设备是否需要通过蜂窝数据网络使用 WiFi 网络。

默认情况下，移动性、通过工作进行呼叫以及启用 VoIP 和视频功能。 禁用 VoIp 和视频需要 WiFi 的设置。 管理员可确定哪些用户可通过运行 cmdlet 访问这些功能。 您可以按网站或用户全局关闭这些选项。

为了能够使用移动功能和单位电话呼叫功能，用户必须满足以下先决条件：

  - 必须为用户启用 Lync Server 2013。

  - 用户必须启用企业语音。

  - 必须为用户分配已将“EnableMobility”**** 选项设置为 True 的移动策略。

对于希望能使用单位电话呼叫功能的用户，他们必须满足以下两个额外的先决条件：

  - 必须为用户分配已选择“允许多部电话同时响铃”**** 选项的语音策略。

  - 必须为用户分配已将“EnableOutsideVoice”**** 选项设置为 True 的移动策略。

<div>


> [!NOTE]  
> 未启用企业语音的用户可以使用其移动设备使 Lync 通过 IP 的 Lync 语音 (VoIP) 呼叫，也可以通过在其移动设备上使用 "加入" 链接来加入会议，前提是为这些用户分配语音策略的相应选项。 有关详细信息，请参阅为 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 定义移动性要求</A>。



</div>

有关为用户启用 Lync Server 2013 的详细信息，请参阅 [Disable or 重新启用 Lync server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 有关为用户启用企业语音的详细信息，请参阅 [Enable users For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。 有关设置语音策略选项的详细信息，请参阅 [在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>

## <a name="to-modify-global-mobility-policy"></a>修改全局移动策略

1.  登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  全局禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>按网站修改移动策略

1.  登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  创建网站级策略，并关闭 VoIP 和视频，并启用站点的 IP 音频和 IP 视频需要 WiFi。 在命令行中键入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>通过用户修改移动策略

1.  登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  创建用户级别移动策略，然后按用户禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。
    
    例如：
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>请参阅


[为 Lync Server 2013 禁用或重新启用用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[定义 Lync Server 2013 的移动性要求](lync-server-2013-defining-your-mobility-requirements.md)  


[新 Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

