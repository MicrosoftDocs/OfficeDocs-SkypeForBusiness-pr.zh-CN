---
title: Set-CsTrunkConfiguration
TOCTitle: Set-CsTrunkConfiguration
ms:assetid: 18152388-68de-4a6b-b5a1-248534ecde72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398238(v=OCS.15)
ms:contentKeyID: 49312123
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTrunkConfiguration

 

_**上一次修改主题：** 2015-02-27_

修改描述中继对等实体（例如服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC)）设置的现有中继配置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsTrunkConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsTrunkConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-ConcentratedTopology <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Enable3pccRefer <$true | $false>] [-EnableBypass <$true | $false>] [-EnableFastFailoverTimer <$true | $false>] [-EnableLocationRestriction <$true | $false>] [-EnableMobileTrunkSupport <$true | $false>] [-EnableOnlineVoice <$true | $false>] [-EnablePIDFLOSupport <$true | $false>] [-EnableReferSupport <$true | $false>] [-EnableRTPLatching <$true | $false>] [-EnableSessionTimer <$true | $false>] [-EnableSignalBoost <$true | $false>] [-Force <SwitchParameter>] [-ForwardCallHistory <$true | $false>] [-ForwardPAI <$true | $false>] [-MaxEarlyDialogs <UInt32>] [-NetworkSiteID <String>] [-OutboundCallingNumberTranslationRulesList <PSListModifier>] [-OutboundTranslationRulesList <PSListModifier>] [-PstnUsages <PSListModifier>] [-RemovePlusFromUri <$true | $false>] [-RTCPActiveCalls <$true | $false>] [-RTCPCallsOnHold <$true | $false>] [-SipResponseCodeTranslationRulesList <PSListModifier>] [-SRTPMode <Required | Optional | NotSupported>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例修改 Identity 为 site:Redmond 的中继配置以启用媒体旁路功能。媒体旁路功能是通过将值 $True 分配给 EnableBypass 参数来启用的。此配置的其余属性将保留其现有值。

    Set-CsTrunkConfiguration -Identity site:Redmond -EnableBypass $True

## 示例 2

此示例修改为中继配置（Identity 为 site:Redmond）定义的出站转换规则。请注意，我们并没有实际调用 **Set-CsTrunkConfiguration** cmdlet 来进行此更改。使用 **Set-CsOutboundTranslationRule** cmdlet 进行的更改会自动反映在 Identity 与出站转换规则 Identity 的范围部分匹配的中继配置中。

    Set-CsOutboundTranslationRule -Identity site:Redmond/OTR1 -Translation '$1'

## 示例 3

示例 3 将在站点范围定义的所有中继配置的 SRTPMode 设置为 Optional。该命令的第一部分调用使用 Filter 参数的 **Get-CsTrunkConfiguration** cmdlet，以检索 Identity 以 site: 开头的所有中继配置，即在站点级别定义的所有中继配置。然后，将该配置集合通过管道传递到 **Set-CsTrunkConfiguration** cmdlet，后者会将每个配置的 SRTPMode 属性设置为 Optional。

    Get-CsTrunkConfiguration -Filter site:* | Set-CsTrunkConfiguration -SRTPMode "Optional"

## 示例 4

示例 4 将修改 Trunk 配置（Identity 为 site:Redmond），以启用 PIDF-LO 支持。默认情况下，EnablePIDFLOSupport 参数为 False。在该示例中我们将该值设置为 True，以启用紧急呼叫的位置支持。必须将 EnablePIDFLOSupport 设置为 True，出站路由应用程序才能将位置信息发送到 Trunk。

    Set-CsTrunkConfiguration -Identity site:Redmond -EnablePIDFLOSupport $True

## 详细说明

使用此 cmdlet 可修改适用于 PSTN 网关实体的中继配置。每种配置包含中继对等实体（如服务提供商的 PSTN 网关、IP-PBX 或 SBC）的特定设置。这些设置配置如下内容：是否在此中继上启用媒体旁路，是否在特定条件下发送实时传输控制协议 (RTCP) 数据包，以及是否需要安全实时协议 (SRTP) 加密。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsTrunkConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsTrunkConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>ConcentratedTopology</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值可确定是否存在一个已知的媒体端点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）如果中继没有已知的媒体端点，则将该值设置为 False。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于描述中继配置用途的字符串。</p></td>
</tr>
<tr class="even">
<td><p><em>Enable3pccRefer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否可使用 3pcc 协议允许转接的呼叫绕过托管站点。3pcc 又称为“第三方控制”，在通过第三方连接呼叫双方时会采用此方式（例如，接线员创建一个从人员 A 到人员 B 的呼叫）。REFER 方法是标准的 SIP 方法，它指示接收人应使用发送人提供的信息来联系第三方。默认值为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableBypass</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值确定是否对该中继启用媒体旁路功能。将此值设置为 True 可启用旁路。请注意，为使媒体旁路功能成功发挥作用，PSTN 网关、SBC 和 PBX 必须支持某些功能，其中包括：</p>
<p>- 能够接收针对邀请的分叉响应。</p>
<p>- Lync Server 客户端与媒体端点必须能够直接通信，而不经由中介服务器。</p>
<p>- 网关子网必须定义为与客户端的子网位于同一站点；如果位于不同站点，则不得使用具有限定带宽的 WAN 链路分隔这些站点。</p>
<p>仅在以下情况时才可以启用媒体旁路功能：</p>
<p>- ConcentratedTopology 参数设置为 True</p>
<p>- EnableReferSupport 参数设置为 False 且 RTCPActiveCalls 和 RTCPCallsOnHold 设置为 False，或 EnableReferSupport 设置为 True</p>
<p>请注意，如果 EnableBypass 为 True 而 EnableReferSupport 为 False，则随后传输的旁路呼叫将变为非旁路呼叫。</p>
<p>要使媒体旁路功能对特定中继起作用，需要在全局范围内启用该功能，并且需要对该中继启用该功能。使用 <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet 可在全局范围内启用媒体旁路功能。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableFastFailoverTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，会将网关在 10 秒内未应答的出站呼叫路由到下一个可用的中继；如果没有其他中继，则会自动丢弃该呼叫。在网络和网关响应缓慢的组织中，这可能导致不必要地丢弃呼叫。</p>
<p>默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLocationRestriction</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，将为通过由指定 SIP 中继配置设置集合管理的 SIP 中继传递的呼叫启用基于位置的语音路由。使用基于位置的语音路由，会在路由呼叫时考虑发起呼叫的用户和接收呼叫的用户的位置。如果此属性设置为 True（默认值为 False），则您还应设置 NetworkSiteId 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableMobileTrunkSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义服务提供商是否为移动运营商。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableOnlineVoice</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示 SIP 中继是否支持联机语音。使用联机语音，用户可创建本地 Lync Server 帐户，但其语音邮件由 Skype for Business Online 托管。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePIDFLOSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义是否通过所定义的网关来路由具有状态信息数据格式位置对象 (PIDF-LO) 的紧急呼叫。如果要将紧急呼叫路由到已认证的紧急服务提供商，需将此参数设置为 True。（位置信息将随呼叫一起传输。）</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableReferSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义此中继是否支持接收来自中介服务器的 Refer 请求。</p>
<p>仅在以下情况时才可以启用媒体旁路功能：</p>
<p>- ConcentratedTopology 参数设置为 True</p>
<p>- EnableReferSupport 参数设置为 False 且 RTCPActiveCalls 和 RTCPCallsOnHold 设置为 False，或 EnableReferSupport 设置为 True</p>
<p>请注意，如果 EnableBypass 为 True 而 EnableReferSupport 为 False，则随后传输的旁路呼叫将变为非旁路呼叫。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>EnableRTPLatching</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一项通过 NAT（网络地址转换器）设备或防火墙建立 RTP/RTCP 连接的技术。默认值为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableSessionTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指定是否启用会话计时器。会话计时器用于确定特定会话是否仍处于活动状态。</p>
<p>请注意，即使此参数设置为 False，但如果远程连接启用了会话计时器，也会应用会话计时器。在这种情况下，中介服务器将响应来自远程实体的会话计时器探查。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableSignalBoost</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果将此参数设置为 True，服务提供商的 PSTN 网关、IP-PBX 或 SBC 将提高发送给中介服务器或 Lync Server 客户端的语音流中的音频音量。如果将此值设置为 False，将在中介服务器（对于非旁路呼叫）或 Lync Server 客户端（对于旁路呼叫）增大音频音量。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>ForwardCallHistory</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否将通过中继转发呼叫历史记录信息。默认值为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>ForwardPAI</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否将随呼叫一起转发 P-Asserted-Identity (PAI) 标头。PAI 标头提供验证呼叫者身份的方法。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>包括中继配置范围的唯一标识符。对于 PSTN 网关服务，中继配置可以位于全局范围、站点范围或服务范围中。例如 site:Redmond（对于站点范围）或 PstnGateway:Redmond.litwareinc.com（对于服务范围）。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>TrunkConfiguration</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p>
<p>此参数要求使用 Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration 类型的对象，可通过调用 <strong>Get-CsTrunkConfiguration</strong> cmdlet 来检索该对象。</p></td>
</tr>
<tr class="even">
<td><p><em>MaxEarlyDialogs</em></p></td>
<td><p>可选</p></td>
<td><p>UInt32</p></td>
<td><p>服务提供商的 PSTN 网关、IP-PBX 或 SBC 可以接收的分叉响应的最大数目，这些响应是针对发送到中介服务器的邀请的。</p>
<p>默认值：20</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与中继配置设置集合关联的网络站点的站点 ID。如果 EnableLocationRestriction 属性设置为 True，则通过此中继路由的基于位置的语音将使用为指定站点配置的设置进行管理。网络站点 ID 可以通过使用以下命令进行检索：</p>
<p>Get-CsNetworkSite | Select NetworkSiteID</p></td>
</tr>
<tr class="even">
<td><p><em>OutboundCallingNumberTranslationRulesList</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>分配给中继的出站呼叫号码转换规则的集合。可以通过运行以下命令来检索有关可用规则的信息：</p>
<p>Get-CsOutboundCallingNumberTranslationRule</p></td>
</tr>
<tr class="odd">
<td><p><em>OutboundTranslationRulesList</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>应用于由 Outbound Routing 处理的呼叫（路由到 PBX 或 PSTN 目标的呼叫）的电话号码转换规则的集合。</p>
<p>虽然使用此 cmdlet 可以直接修改该列表和这些规则，但我们建议您使用 <strong>Set-CsOutboundTranslationRule</strong> cmdlet 修改出站转换规则。<strong>Set-CsOutboundTranslationRule</strong> cmdlet 将修改该规则，并且所做的修改会自动反映在中继配置中。要通过添加新的出站转换规则来修改中继配置，请调用 <strong>New-CsOutboundTranslationRule</strong> cmdlet；新规则将添加到具有匹配范围的中继配置中。</p></td>
</tr>
<tr class="even">
<td><p><em>PstnUsages</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>分配给中继的 PSTN 用法的集合。可以通过运行以下命令来检索有关可用用法的信息：</p>
<p>Get-CsPstnUsage</p></td>
</tr>
<tr class="odd">
<td><p><em>RemovePlusFromUri</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果将此参数设置为 True，会导致中介服务器在将统一资源标识符 (Uniform Resources Identifier, URI) 发送给服务提供商之前，删除该标识符的前导加号 (+)。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>RTCPActiveCalls</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数确定是否从服务提供商的 PSTN 网关、IP-PBX 或 SBC 对活动呼叫发送 RTCP 数据包。此情况下的活动呼叫是指允许媒体沿至少一个方向流动的呼叫。当 RTCPActiveCalls 设置为 True 时，如果中介服务器或 Lync Server 客户端在 30 秒后还没有收到 RTCP 数据包，将会终止呼叫。</p>
<p>请注意，如果对 Lync Server 元素中活动呼叫收到的 RTCP 媒体禁用检查，则将失去一种用于检测故障对等端的重要安全防护措施，因此应仅在必要时才禁用检查。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>RTCPCallsOnHold</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数确定是否通过中继，继续对置于等待状态且预计在任何方向都没有媒体数据包流动的呼叫发送 RTCP 数据包。如果在 Lync Server 客户端或中继上启用了呼叫等待音乐功能，此呼叫将被认为是活动呼叫，而该属性将被忽略。这种情况下可使用 RTCPActiveCalls 参数。</p>
<p>请注意，如果对 Lync Server 元素中活动呼叫收到的 RTCP 媒体禁用检查，则将失去一种用于检测故障对等端的重要安全防护措施，因此应仅在必要时才禁用检查。</p>
<p>默认值：True</p></td>
</tr>
<tr class="even">
<td><p><em>SipResponseCodeTranslationRulesList</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>SIP 响应代码转换规则列表，这些规则适用于从服务提供商的 PSTN 网关、IP-PBX 或 SBC 收到的响应代码。使用这些规则，管理员可以将通过中继收到的值在 400 与 699 之间的 SIP 响应代码映射到更符合 Lync Server 标准的新值。</p>
<p>您可直接使用此 cmdlet 创建该列表和相应规则。但是，我们建议您通过调用 <strong>New-CsSipResponseCodeTranslationRule</strong> cmdlet 来创建 SIP 响应代码转换规则。该 cmdlet 会创建此规则并将其分配给具有匹配范围的中继配置。</p></td>
</tr>
<tr class="odd">
<td><p><em>SRTPMode</em></p></td>
<td><p>可选</p></td>
<td><p>SRTPMode</p></td>
<td><p>此参数的值可确定对 SRTP 的支持级别，以保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量。对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。可使用 <strong>New-CsMediaConfiguration</strong> cmdlet 和 <strong>Set-CsMediaConfiguration</strong> cmdlet 设置媒体配置。</p>
<p>有效值：</p>
<p>- Required：必须使用 SRTP 加密。</p>
<p>- Optional：如果服务提供商支持 SRTP，则使用 SRTP。</p>
<p>- NotSupported:SRTP 加密不受支持，因此不使用该功能。</p>
<p>注意：仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为 NotSupported。</p>
<p>默认值：Required</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>开关参数</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration 对象。接受通过管道传递的中继配置对象的输入。

## 返回类型

此 cmdlet 不会返回值；它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration 的对象。

## 另请参阅

#### 其他资源

[New-CsTrunkConfiguration](new-cstrunkconfiguration.md)  
[Remove-CsTrunkConfiguration](remove-cstrunkconfiguration.md)  
[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)  
[Test-CsTrunkConfiguration](test-cstrunkconfiguration.md)  
[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)  
[Set-CsOutboundTranslationRule](set-csoutboundtranslationrule.md)

