---
title: Lync Server 2013：定义移动性要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0eeb3feda41a62472c79214681bc4b9ce0a22ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>定义 Lync Server 2013 的移动性要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在 Lync Server 2013 移动功能的规划阶段，当你使用 Lync 2010 移动版和 Lync 2013 移动客户端时，应做出决定以确定部署步骤。

下面是您必须考虑的决策：

  - **是否要对 Lync 移动客户端使用自动发现功能？**
    
    如果要支持自动发现，则需要创建新的内部和外部域名系统（DNS）记录，向前端服务器、控制器和反向代理上的证书添加使用者备用名称，以及修改现有的发布规则在反向代理上。 有关详细信息，请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。 通过自动发现，用户可以从公司网络内部或外部的任何位置自动找到 Lync Server 2013 Web 服务，而无需在其移动设备设置中输入 Url。
    
    如果使用手动设置而不是自动发现，移动用户需要手动在其移动设备中输入以下 Url：
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 用于外部访问
    
      - https://\<IntPoolFQDN\>/AutoDiscover/autodiscoverservice/Root for internal access
    
    强烈建议您使用自动发现功能。手动设置主要用于进行故障排除。

  - **如果您决定支持自动发现功能，那么您是否愿意使用每个 SIP 域的使用者替代名称更新反向代理上的证书？**
    
    如果您具有多个 SIP 域，则更新反向代理上的公共证书的成本会非常高。 如果是这种情况，则可以选择实施自动发现，以便初始自动发现服务请求在端口80上使用 HTTP，而不是在端口443上使用 HTTPS。 但是，这并不是推荐的方法。 如果决定选择此替代方法，则无需在反向代理上更新证书，但需要在端口80上为 HTTP 创建 web 发布规则。 有关更多详细信息，请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **是希望同时在企业网络的内部和外部支持 Lync 移动客户端，还是希望仅在企业网络内部支持这些客户端？**
    
    如果您希望同时在网络的内部和外部支持移动客户端，则移动设备可从任意位置访问移动功能。默认配置为，同时在企业网络的内部和外部支持客户端。
    
    尽管默认配置允许移动客户端通信通过外部网站，但您可以将移动客户端通信限制在内部企业网络内。 如果您将通信限制在内部网络内，则用户只有在位于网络内部时才能在其移动设备上使用 Lync 移动应用程序。
    
    有关使用 Mcx 移动服务和 Lync 2010 Mobile 支持移动性的部署，请运行**CsMcxConfiguration** cmdlet。 若要将移动功能设置为仅供内部使用，请使用类似于以下的命令：
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA 不需要其他配置。 UCWA 没有等效的仅内部配置。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果使用的是 Lync Server 2013&nbsp;前端服务器或前端池，并且没有任何 Lync server 2010&nbsp;前端服务器或前端池，则不<STRONG>需要基于 cookie 的持久性</STRONG>。 <STRONG></STRONG> 如果需要保留任何 Lync Server 2010&nbsp;前端服务器或前端池，则在 Lync server 2010 中的相同规则仍适用于基于 cookie 的持久性。

    
    </div>

  - **是否希望支持针对 Apple iOS 设备和 Windows Phone 的推送通知？**
    
    如果您支持推送通知，则受支持的 Apple iOS 设备和 Windows Phone 将收到在移动应用程序处于非活动状态时所发生的事件的通知。 您必须将您的边缘服务器配置为与基于云的 Lync Server 推送通知服务（位于 Lync Online 数据中心中）具有联合身份验证关系，并运行 cmdlet 以启用推送通知。
    
    如果要通过 Wlan 网络支持推送通知，除了通过移动设备提供商的3G 或数据网络支持推送通知之外，还必须在企业版 Wi-fi 网络上打开出站端口5223。 通过在 Wi-Fi 网络中支持推送通知，可支持仅使用 Wi-Fi 的移动设备和室内接收能力较差的移动设备。
    
    <div>
    

    > [!IMPORTANT]  
    > 仅当支持运行 Lync 2010 移动客户端的 Apple 设备时，才需要打开端口 TCP 5223。

    
    </div>
    
    如果不支持推送通知，Apple 移动设备和 Windows phone 的用户将找不到有关在移动应用程序处于非活动状态时出现的事件（如即时消息邀请或丢失的邮件）。
    
    <div>
    

    > [!NOTE]  
    > Apple 设备上的 Lync 2013 移动客户端不需要推送通知。 Windows Phone 上的 Lync 2013 移动客户端使用推送通知。 对推送通知和推送通知交换所做的规划对于不能运行 Lync 2013 移动客户端的 Windows Phone 和 Apple 设备上的 Lync Mobile 保持不变。

    
    </div>

  - **您是否希望所有用户都有权访问移动功能，或者是否希望能够指定哪些用户有权访问这些功能？**
    
    此表介绍了 Lync Server 2013 中用户可用的功能。 默认值允许通过工作呼叫，允许 IP 语音（VoIP），并启用移动性。 下面是一组完整的可用选项：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>功能/参数名称/范围（策略参数名称可能不同）</th>
    <th>说明</th>
    <th>引入</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>启用移动性</p>
    <p>参数名称：<code>EnableMobility</code></p>
    <p>作用域：全局/站点/用户</p></td>
    <td><p>用于控制安装了 Lync Mobile 的给定范围内用户的管理设置，如果将策略设置为 False，则用户将无法登录到客户端。</p>
    <p>默认设置为 True。</p></td>
    <td><p>Lync Server 2010 的累积更新：11月2011</p></td>
    </tr>
    <tr class="even">
    <td><p>启用外部语音</p>
    <p>参数名称：<code>EnableOutsideVoice</code></p>
    <p>作用域：全局/站点/用户</p></td>
    <td><p>控制用户在工作中使用呼叫的能力，这是一项功能，允许用户使用其工作电话号码而不是移动电话号码拨打和接听呼叫。 如果设置为 False，则用户将无法使用其移动设备上的工作电话号码拨打或接听呼叫。</p>
    <p>默认设置为 True</p></td>
    <td><p>Lync Server 2010 的累积更新：11月2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>启用 IP 音频和视频</p>
    <p>参数名称：<code>EnableIPAudioVideo</code></p>
    <p>作用域：全局/站点/用户</p></td>
    <td><p>控制用户是否可以在其移动设备上使用 VoIP 发出或接收语音或视频呼叫。 如果设置为 False，则用户将无法在其设备上进行或接收 VoIP 或视频呼叫。</p>
    <p>默认设置为 True。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>需要 IP 音频的 WiFi</p>
    <p>参数名称：<code>RequireWiFiForIPAudio</code></p>
    <p>作用域：全局/站点/用户</p></td>
    <td><p>此设置定义客户端是否需要在 WiFi （而不是手机数据网络）上拨打和接听 VoIP 进行呼叫。 如果设置为 True，则仅当连接到 WiFi 网络时，用户才可以拨打和接听 VoIP 呼叫。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 视频需要 WiFi</p>
    <p>参数名称：<code>RequireWiFiForIPVideo</code></p>
    <p>作用域：全局/站点/用户</p></td>
    <td><p>此设置定义客户端是否需要在 Wlan 上发出和接收视频呼叫，而不是在手机网络数据网络上进行。 如果设置为 True，则用户只能在连接到 Wi-fi 网络时发出和接收视频呼叫。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    有关可以配置的策略设置，以及如何管理策略的说明，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant 和 set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。

  - **是否希望未启用企业语音的用户能够使用“单击以加入”来加入会议？**
    
    对于可以访问移动功能和单位电话呼叫功能的用户，必须为他们启用企业语音。 但是，如果未启用企业语音的用户可以通过单击其移动设备上的链接来加入会议，前提是他们已向其分配适当的语音策略。 您可以为这些用户分配特定的语音策略，也可以确保存在适用于它们的全局策略或网站级别策略。 您分配的语音策略必须具有公共交换电话网络（PSTN）使用记录和路由，这些记录定义用户可以拨出以加入会议的区域。 有关设置语音策略、PSTN 用法记录和路由的详细信息，请参阅[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。
    
    <div>
    

    > [!NOTE]  
    > 要使用单击加入的移动用户需要语音策略以及相关的 PSTN 用法记录和语音路由，因为单击移动设备上的链接将导致来自 Lync Server 2013 的出站呼叫。

    
    </div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)  


[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

