---
title: Lync Server 2013：定义您的移动要求
TOCTitle: 定义您的移动要求
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690039(v=OCS.15)
ms:contentKeyID: 49314020
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 定义您的 Lync Server 2013 移动要求

 

_**上一次修改主题：** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

在实现 Lync Server 2013 移动功能的规划阶段，当您要使用 Lync 2010 Mobile 和 Lync 2013 Mobile 客户端时，您需要做出一些确定部署步骤的决定。

以下是您必须要考虑的决定：

  - **是否要对 Lync 移动客户端使用自动发现功能？**
    
    如果您希望支持自动发现功能，则需要创建新的内部和外部域名系统 (DNS) 记录，将使用者替代名称添加到 前端服务器、 控制器和反向代理上的证书中，并在反向代理上修改现有发布规则。有关详细信息，请参阅 [Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。利用自动发现功能，用户可从企业网络的内部或外部的任意位置自动定位 Lync Server 2013 Web 服务，而无需在其移动设备设置中输入 URL。
    
    如果您使用手动设置而非自动发现功能，则移动用户需要在其移动设备中手动输入以下 URL：
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root（用于外部访问）
    
      - https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root（用于内部访问）
    
    强烈建议您使用自动发现功能。手动设置主要用于进行故障排除。

  - **如果您决定支持自动发现功能，那么您是否愿意使用每个 SIP 域的使用者替代名称更新反向代理上的证书？**
    
    如果您具有多个 SIP 域，则更新反向代理上的公共证书的成本会非常高。在此情况下，您可以选择实现自动发现功能，这样一来，初始自动发现服务请求将在端口 80 上使用 HTTP，而不是在端口 443 上使用 HTTPS。建议您不要采用此方法。如果您决定选择此备用方法，则无需更新反向代理上的证书，但您需要在端口 80 上为 HTTP 创建 Web 发布规则。有关更多详细信息，请参阅 [Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **是希望同时在企业网络的内部和外部支持 Lync 移动客户端，还是希望仅在企业网络内部支持这些客户端？**
    
    如果您希望同时在网络的内部和外部支持移动客户端，则移动设备可从任意位置访问移动功能。默认配置为，同时在企业网络的内部和外部支持客户端。
    
    尽管默认配置允许移动客户端通信通过外部网站，但您可以将移动客户端通信限制在内部企业网络内。如果您将通信限制在内部网络内，则用户只有在位于网络内部时才能在其移动设备上使用 Lync 移动应用程序。
    
    对于支持使用 Mcx Mobility Service 和 Lync 2010 Mobile 的移动性的部署，您需要运行 **Set-CsMcxConfiguration** cmdlet。要仅为内部使用设置移动性，可使用如下命令：
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    > [!NOTE]  
    > UCWA 不需要其他任何额外配置，并且它不具有仅用于内部的同等配置。
    
    
    > [!IMPORTANT]
    > 如果您使用的是 Lync Server 2013前端服务器或 前端池，并且 <strong>没有</strong>任何 Lync Server 2010前端服务器或 前端池， <strong>则无需基于 Cookie 的持久性</strong>。如果需要保留任何 Lync Server 2010前端服务器或 前端池，则与 Lync Server 2010 中相同的规则仍适用于基于 Cookie 的持久性。


  - **是否希望支持针对 Apple iOS 设备和 Windows Phone 的推送通知？**
    
    如果您支持推送通知，则受支持的 Apple iOS 设备和 Windows Phone 将收到在移动应用程序处于非活动状态时所发生的事件的通知。您需要配置您的 边缘服务器，使其与基于云的 Lync Server 推送通知服务（位于 Lync Online 数据中心内）之间具有联盟关系，并运行 cmdlet 以启用推送通知。
    
    如果您希望在 Wi-Fi 网络中支持推送通知，并希望在移动设备提供商的 3G 或数据网络中支持推送通知，则您必须在企业 Wi-Fi 网络上向外打开端口 5223。通过在 Wi-Fi 网络中支持推送通知，可支持仅使用 Wi-Fi 的移动设备和室内接收能力较差的移动设备。
    
    > [!IMPORTANT]
    > 仅在支持运行 Lync 2010 Mobile 客户端的 Apple 设备时才需要打开端口 TCP 5223。
    
    如果您不支持推送通知，则 Apple 移动设备和 Windows Phone 的用户将找不到在移动应用程序处于非活动状态时所发生的事件（例如，即时消息邀请或错过的消息）。
    
    > [!NOTE]  
    > Apple 设备上的 Lync 2013 Mobile 客户端不需要推送通知，而 Windows Phone 上的 Lync 2013 Mobile 客户端使用推送通知。对于 Windows Phone 上的 Lync Mobile 以及不能运行 Lync 2013 Mobile 客户端的 Apple 设备，有关推送通知和推送通知交换所的规划应保持一致。
    


  - **是否希望所有用户都可以访问移动功能，或是否希望自己能够指定哪些用户可以访问这些功能？**
    
    下表描述可供 Lync Server 2013 用户使用的功能。默认提供“单位电话呼叫”、“IP 语音 (VoIP)”和移动功能。以下是完整的可用选项集：
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>功能/参数名称/范围 （策略参数名称可能不相同）</th>
    <th>说明</th>
    <th>引入程序</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>支持移动性</p>
    <p>参数名称： <code>EnableMobility</code></p>
    <p>范围：全局/站点/用户</p></td>
    <td><p>用于控制指定范围内已安装 Lync Mobile 的用户的管理设置。如果该策略设置为 False，则用户无法登录到客户端。</p>
    <p>默认设置为 True。</p></td>
    <td><p>2011 年 11 月版 Lync Server 2010 累积更新</p></td>
    </tr>
    <tr class="even">
    <td><p>支持外部语音</p>
    <p>参数名称：<code>EnableOutsideVoice</code></p>
    <p>范围：全局/站点/用户</p></td>
    <td><p>对用户能否使用“单位电话呼叫”功能进行控制，该功能允许用户使用其单位号码而不是移动号码来拨打和接听电话。如果设置为 False，用户将无法使用其单位号码从其移动设备拨打或接听电话。</p>
    <p>默认设置为 True。</p></td>
    <td><p>2011 年 11 月版 Lync Server 2010 累积更新</p></td>
    </tr>
    <tr class="odd">
    <td><p>支持 IP 音频和视频</p>
    <p>参数名称：<code>EnableIPAudioVideo</code></p>
    <p>范围：全局/站点/用户</p></td>
    <td><p>对用户能否使用 VoIP 在其移动设备上拨打或接听语音或视频电话进行控制。如果设置为 False，用户将无法在其设备上拨打或接听 VoIP 或视频电话。</p>
    <p>默认设置为 True。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP 音频需要 WiFi</p>
    <p>参数名称：<code>RequireWiFiForIPAudio</code></p>
    <p>范围：全局/站点/用户</p></td>
    <td><p>该设置定义是否将要求客户端通过 WiFi 而不是蜂窝数据网络拨打和接听 VoIP 电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 视频需要 WiFi</p>
    <p>参数名称：<code>RequireWiFiForIPVideo</code></p>
    <p>范围：全局/站点/用户</p></td>
    <td><p>该设置定义是否将要求客户端通过 WiFi 而不是蜂窝数据网络拨打和接听视频电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听视频电话。</p>
    <p>默认设置为 False。</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    有关您可以配置的策略设置以及如何管理这些策略的说明，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)、 [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)、 [Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)、 [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy) 和 [Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)。

  - **是否希望未启用企业语音的用户能够使用“单击以加入”来加入会议？**
    
    对于可以访问移动功能和“单位电话呼叫”功能的用户，必须为他们启用企业语音。不过，对于未启用企业语音的用户，如果为其分配了适当的语音策略，则可通过单击其移动设备上的链接来加入会议。您可以为这些用户分配一个特定的语音策略或确保存在适用的全局或站点级策略。您分配的语音策略必须具有公用电话交换网 (PSTN) 用法记录和可定义用户为加入会议而将拨出到的区域的路由。有关设置语音策略、PSTN 用法记录和路由的详细信息，请参阅[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)。
    
    > [!NOTE]  
    > 需要使用“单击以加入”的移动用户需要语音策略、相关的 PSTN 用法记录以及语音路由，因为单击移动设备上的链接会导致来自 Lync Server 2013 的出站呼叫。
    


## 另请参阅

#### 概念

[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)  

#### 其他资源

[在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

