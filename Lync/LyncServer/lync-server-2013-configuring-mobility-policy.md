---
title: Lync Server 2013：配置移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中配置移动策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 提供了移动性策略, 这些策略确定谁可以使用移动功能、通过工作、IP 语音 (VoIP) 或视频通话以及是否需要 WiFi 或视频。 通过 "通过工作电话呼叫" 功能, 移动用户可以通过使用工作电话号码 (而不是移动电话号码) 在移动电话上拨打和接听电话。 此功能可防止被呼叫方看到呼叫方的移动电话号码, 并使用户可以避免出站通话费用。 配置 VoIP 和视频使用户可以接收和进行 VoIP 呼叫和视频。 WiFi 使用的设置定义用户的设备是否需要在移动数据网络上使用 WiFi 网络。

默认情况下, 移动、通过工作进行呼叫, 并启用 VoIP 和视频功能。 已禁用 VoIp 和视频需要 WiFi 的设置。 管理员可以通过运行 cmdlet 来确定哪些用户有权访问这些功能。 你可以将选项设置为 "全局"、"按网站" 或 "由用户"。

若要能够通过工作使用移动功能和通话, 用户必须满足以下先决条件:

  - 必须为 Lync Server 2013 启用用户。

  - 必须为用户启用企业语音。

  - 必须为用户分配一个将**EnableMobility**选项设置为 True 的移动策略。

为使用户能够通过工作使用呼叫, 他们必须满足以下两个额外的先决条件:

  - 必须为用户分配已选中 "**启用同时拨打的电话**" 选项的语音策略。

  - 必须为用户分配一个将**EnableOutsideVoice**选项设置为 True 的移动策略。

<div>


> [!NOTE]  
> 未启用企业语音的用户可以使用其移动设备使 Lync 通过 IP (VoIP) 呼叫进行 Lync 语音通话, 或者, 如果为这些用户分配了相应的语音策略选项, 则可以通过使用 "单击以加入" 链接在其移动设备上加入会议。 有关详细信息, 请参阅<A href="lync-server-2013-defining-your-mobility-requirements.md">定义 Lync Server 2013 的移动性要求</A>。



</div>

有关为 Lync Server 2013 启用用户的详细信息, 请参阅[禁用或重新启用 Lync server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。 有关为企业语音启用用户的详细信息, 请参阅[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)。 有关设置语音策略选项的详细信息, 请参阅[在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。

<div>

## <a name="to-modify-global-mobility-policy"></a>修改全局移动策略

1.  登录到安装了 Lync Server 命令行管理器和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  通过全球工作, 关闭对移动和通话的访问。 在命令行中键入：
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 您可以通过工作来关闭呼叫, 而无需关闭移动访问。 但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>按网站修改移动策略

1.  登录到安装了 Lync Server 命令行管理器和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  创建网站级策略, 关闭 VoIP 和视频, 并启用 IP 音频的 WiFi 和视频, 并按站点启用 IP 视频的 WiFi。 在命令行中键入：
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>按用户修改移动策略

1.  登录到安装了 Lync Server 命令行管理器和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  创建用户级移动策略, 并通过用户的工作方式关闭移动性和呼叫。 在命令行中键入：
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    您可以通过工作来关闭呼叫, 而无需关闭移动访问。 但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。
    
    例如：
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>另请参阅


[禁用或重新启用 Lync Server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[定义您的 Lync Server 2013 移动要求](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

