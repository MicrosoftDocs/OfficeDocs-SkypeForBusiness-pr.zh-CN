---
title: Lync Server 2013：定义您的移动要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>定义您的 Lync Server 2013 移动要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在 Lync Server 2013 移动功能的规划阶段中, 当你使用 Lync 2010 移动版和 Lync 2013 移动客户端时, 应做出决定以确定你的部署步骤。

下面是您必须考虑的决策:

  - **是否要使用 Lync 移动客户端的自动发现？**
    
    如果你想要支持自动发现, 你需要创建新的内部和外部域名系统 (DNS) 记录, 在前端服务器、控制器和反向代理上向证书添加使用者备用名称, 以及修改现有发布规则反向代理。 有关详细信息, 请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。 通过自动发现, 用户可以从公司网络内部或外部的任何位置自动查找 Lync Server 2013 Web 服务, 而无需在移动设备设置中输入 Url。
    
    如果您使用手动设置而不是自动搜索, 则移动用户需要在其移动设备上手动输入以下 Url:
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
      - https://\<IntPoolFQDN\>/AutoDiscover/autodiscoverservice/Root for 内部访问
    
    强烈建议使用自动发现。 手动设置的主要用途是进行故障排除。

  - **如果你决定支持自动发现, 你是否愿意使用每个 SIP 域的使用者备用名称更新反向代理的证书？**
    
    如果您有多个 SIP 域, 则在反向代理服务器上更新公共证书可能会非常昂贵。 如果是这种情况, 你可以选择实现自动发现, 以便初始自动发现服务请求在端口80上使用 HTTP, 而不是在端口443上使用 HTTPS。 但是, 这不是推荐的方法。 如果你决定选择这种替代方法, 则无需更新反向代理的证书, 但你需要在端口80上为 HTTP 创建 web 发布规则。 有关更多详细信息, 请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **是否希望同时支持企业网络内部和外部的 Lync 移动客户端, 或者仅支持企业网络内的客户端？**
    
    如果您希望支持您的网络内部和外部的移动客户端, 则移动设备可从任何位置访问移动功能。 默认配置是支持企业网络内部和外部的客户端。
    
    尽管默认配置允许移动客户端通信转到外部网站, 但你可以将移动客户端流量限制到内部公司网络。 将流量限制到内部网络时, 用户只能在其移动设备上使用 Lync mobile 应用程序, 而不是在网络内部。
    
    对于支持使用 Mcx 移动服务和 Lync 2010 Mobile 进行移动的部署, 请运行**CsMcxConfiguration** cmdlet。 若要设置仅供内部使用的移动, 请使用类似于以下内容的命令:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > UCWA 不需要额外的配置。 UCWA 没有等效的仅内部配置。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您使用的是 Lync Server 2013&nbsp;前端服务器或前端池, 并且没有<STRONG></STRONG>任何 Lync server 2010&nbsp;前端服务器或前端池, 则不<STRONG>需要基于 cookie 的持久性</STRONG>。 如果需要保留任何 Lync Server 2010&nbsp;前端服务器或前端池, 同样的规则在 Lync Server 2010 中仍适用于基于 cookie 的持久性。

    
    </div>

  - **是否要支持 Apple iOS 设备和 Windows phone 的推送通知？**
    
    如果你支持推送通知, 受支持的 Apple iOS 设备和 Windows phone 将收到当移动应用程序处于非活动状态时发生的事件通知。 你必须将 Edge 服务器配置为与基于云的 Lync Server 推送通知服务具有联合身份验证关系, 该服务位于 Lync Online 数据中心, 并运行 cmdlet 以启用推送通知。
    
    如果你希望通过 Wi-fi 网络支持推送通知, 除了支持移动设备提供商的3G 或数据网络上的推送通知之外, 你必须在企业 Wi-fi 网络上打开出站端口5223。 通过 Wi-fi 网络支持推送通知支持仅使用 Wlan 和移动设备的移动设备, 使用室内接收不太好。
    
    <div>
    

    > [!IMPORTANT]  
    > 仅当支持运行 Lync 2010 移动客户端的 Apple 设备时, 才需要打开端口 TCP 5223。

    
    </div>
    
    如果不支持推送通知, Apple mobile 设备和 Windows phone 的用户将无法找到有关在移动应用程序处于非活动状态时出现的事件 (如即时消息邀请或错过的消息)。
    
    <div>
    

    > [!NOTE]  
    > Apple 设备上的 Lync 2013 移动客户端不需要推送通知。 Windows Phone 上的 Lync 2013 移动客户端使用推送通知。 对推送通知和推送通知 clearinghouse 的规划对于 Windows Phone 上的 Lync Mobile 和不能运行 Lync 2013 移动客户端的 Apple 设备保持相同。

    
    </div>

  - **是否希望所有用户都可以访问移动功能, 或者是否希望能够指定哪些用户有权访问这些功能？**
    
    此表介绍了 Lync Server 2013 中的用户可用的功能。 默认情况下, 允许通过工作呼叫呼叫、允许 IP 语音 (VoIP) 和启用移动性。 下面是可用选项的完整集:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>功能/参数名称/范围 (策略参数名称可能不同)</th>
    <th>说明</th>
    <th>新增</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>支持移动性</p>
    <p>参数名称:<code>EnableMobility</code></p>
    <p>范围: 全局/网站/用户</p></td>
    <td><p>管理设置若要控制已安装 Lync Mobile 的给定范围内的用户, 如果该策略设置为 False, 用户将无法登录到客户端。</p>
    <p>默认设置为 True。</p></td>
    <td><p>Lync Server 2010 的累积更新:11 月2011</p></td>
    </tr>
    <tr class="even">
    <td><p>启用外部语音</p>
    <p>参数名称:<code>EnableOutsideVoice</code></p>
    <p>范围: 全局/网站/用户</p></td>
    <td><p>控制用户通过工作进行呼叫的能力, 该功能使用户能够使用其工作电话号码而不是移动电话号码拨打和接听电话。 如果设置为 False, 用户将无法通过其移动设备使用其工作电话来拨打或接听电话。</p>
    <p>默认设置为 True</p></td>
    <td><p>Lync Server 2010 的累积更新:11 月2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>支持 IP 音频和视频</p>
    <p>参数名称:<code>EnableIPAudioVideo</code></p>
    <p>范围: 全局/网站/用户</p></td>
    <td><p>控制用户是否可以使用 VoIP 在其移动设备上进行语音或视频通话。 如果设置为 False, 用户将无法在其设备上进行或接收 VoIP 或视频通话。</p>
    <p>默认设置为 True。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP 音频需要 WiFi</p>
    <p>参数名称:<code>RequireWiFiForIPAudio</code></p>
    <p>范围: 全局/网站/用户</p></td>
    <td><p>此设置定义客户是否需要在 WiFi 上通过 VoIP 而不是手机网络数据网络进行呼叫。 如果设置为 True, 则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 呼叫。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 视频需要 WiFi</p>
    <p>参数名称:<code>RequireWiFiForIPVideo</code></p>
    <p>范围: 全局/网站/用户</p></td>
    <td><p>此设置定义客户端是否需要在 Wi-fi 上进行视频呼叫, 而不是在手机网络数据网络上进行接收。 如果设置为 True, 则用户仅在连接到 Wi-fi 网络时才能进行和接收视频呼叫。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    有关你可以配置的策略设置以及如何管理策略的说明, 请参阅[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)、 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)、 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)和[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)。

  - **您是否希望未启用企业语音的用户能够使用单击加入加入会议？**
    
    若要让用户能够访问移动功能并通过工作进行呼叫, 必须为企业语音启用这些功能。 但是, 未启用企业语音的用户可以通过单击其移动设备上的链接来加入会议, 前提是这些用户已分配适当的语音策略。 你可以为这些用户分配特定的语音策略, 或者确保存在适用于它们的全局策略或网站级别策略。 您分配的语音政策必须具有公共交换电话网络 (PSTN) 使用记录和路由, 用于定义用户可拨出以加入会议的区域。 有关设置语音策略、PSTN 使用记录和路由的详细信息, 请参阅[在 Lync Server 2013 中配置语音策略、pstn 使用记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。
    
    <div>
    

    > [!NOTE]  
    > 希望使用 "单击以加入" 的移动用户以及相关的 PSTN 使用记录和语音路由, 因为单击移动设备上的链接将导致来自 Lync Server 2013 的出站呼叫。

    
    </div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)  


[在 Lync Server 2013 中配置语音策略、PSTN 使用记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

