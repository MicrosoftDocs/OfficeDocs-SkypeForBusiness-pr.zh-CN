---
title: New-CsTrunkConfiguration
TOCTitle: New-CsTrunkConfiguration
ms:assetid: f3958f86-3313-4929-9f9d-f796a2669aea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413021(v=OCS.15)
ms:contentKeyID: 49314722
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTrunkConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建描述中继对等实体（例如服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC)）设置的新中继配置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTrunkConfiguration -Identity <XdsIdentity> [-ConcentratedTopology <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Enable3pccRefer <$true | $false>] [-EnableBypass <$true | $false>] [-EnableFastFailoverTimer <$true | $false>] [-EnableLocationRestriction <$true | $false>] [-EnableMobileTrunkSupport <$true | $false>] [-EnableOnlineVoice <$true | $false>] [-EnablePIDFLOSupport <$true | $false>] [-EnableReferSupport <$true | $false>] [-EnableRTPLatching <$true | $false>] [-EnableSessionTimer <$true | $false>] [-EnableSignalBoost <$true | $false>] [-Force <SwitchParameter>] [-ForwardCallHistory <$true | $false>] [-ForwardPAI <$true | $false>] [-InMemory <SwitchParameter>] [-MaxEarlyDialogs <UInt32>] [-NetworkSiteID <String>] [-OutboundCallingNumberTranslationRulesList <PSListModifier>] [-OutboundTranslationRulesList <PSListModifier>] [-PstnUsages <PSListModifier>] [-RemovePlusFromUri <$true | $false>] [-RTCPActiveCalls <$true | $false>] [-RTCPCallsOnHold <$true | $false>] [-SipResponseCodeTranslationRulesList <PSListModifier>] [-SRTPMode <Required | Optional | NotSupported>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例创建 Identity 为 site:Redmond 的新中继配置。该新配置的其余属性将使用默认值进行填充。

    New-CsTrunkConfiguration -Identity site:Redmond

## 示例 2

此示例创建 Identity 为 site:Redmond 的新中继配置并启用媒体旁路。媒体旁路功能是通过将值 $True 分配给 EnableBypass 参数来启用的。该新配置的其余属性将使用默认值进行填充。

    New-CsTrunkConfiguration -Identity site:Redmond -EnableBypass $True

## 示例 3

此示例创建 Identity 为 site:Redmond 的新中继配置，然后为该中继分配新的出站转换。此示例的第一行调用 **New-CsTrunkConfiguration** cmdlet 创建使用默认设置的新中继配置。第二行调用 **New-CsOutboundTranslationRule** cmdlet。请注意分配给 Identity 的值：site:Redmond/OTR1。Identity 的第一部分 (site:Redmond) 定义应用规则的范围。该范围匹配新中继配置的 Identity，这意味着此规则将自动应用于该配置。该范围后跟斜线 (/)，然后是一个字符串，该字符串是此规则的唯一名称（每个范围可以包含多个规则）。之后，我们将值传递到 Pattern 和 Translation 参数以定义此规则。

    New-CsTrunkConfiguration -Identity site:Redmond
    New-CsOutboundTranslationRule -Identity site:Redmond/OTR1 -Pattern '^\+(\d{8})$' -Translation '9$1'

## 详细说明

使用此 cmdlet 可创建适用于 PSTN 网关实体的新中继配置。每种配置包含中继对等实体（如服务提供商的 PSTN 网关、IP-PBX 或 SBC）的特定设置。这些设置配置如下内容：是否在此中继上启用媒体旁路，是否在特定条件下发送实时传输控制协议 (RTCP) 数据包，以及是否需要安全实时协议 (SRTP) 加密。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsTrunkConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTrunkConfiguration"}

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>XdsIdentity</p></td>
<td><p>包括中继配置范围的唯一标识符。可以在站点范围创建中继配置，对于 PSTN 网关服务，也可以在服务范围创建中继配置。（默认情况下，全局配置已存在，不能删除或重新创建。）例如 site:Redmond（对于站点范围）或 PstnGateway:Redmond.litwareinc.com（对于服务范围）。</p></td>
</tr>
<tr class="even">
<td><p><em>ConcentratedTopology</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值可确定是否存在一个已知的媒体端点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）如果中继没有已知的媒体端点，则将该值设置为 False。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于描述中继配置用途的字符串。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enable3pccRefer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否可使用 3pcc 协议允许转接的呼叫绕过托管站点。3pcc 又称为“第三方控制”，在通过第三方连接呼叫双方时会采用此方式（例如，接线员创建一个从人员 A 到人员 B 的呼叫）。REFER 方法是标准的 SIP 方法，它指示接收人应使用发送人提供的信息来联系第三方。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableBypass</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>此参数的值可确定是否对该中继启用媒体旁路功能。将此值设置为 True 可启用旁路。请注意，为使媒体旁路功能成功发挥作用，PSTN 网关、SBC 和 PBX 必须支持某些功能，其中包括：</p>
<p>- 能够接收针对邀请的分叉响应。</p>
<p>- Lync Server 客户端与媒体端点必须能够直接通信，而不经由中介服务器。</p>
<p>- 网关子网必须定义为与客户端的子网位于同一站点；如果位于不同站点，则不得使用具有限定带宽的 WAN 链路分隔这些站点。</p>
<p>仅在以下情况时才可以启用媒体旁路功能：</p>
<p>- ConcentratedTopology 参数设置为 True</p>
<p>- EnableReferSupport 参数设置为 False 且 RTCPActiveCalls 和 RTCPCallsOnHold 设置为 False，或 EnableReferSupport 设置为 True</p>
<p>请注意，如果 EnableBypass 为 True 且 EnableReferSupport 为 False，则随后传输的旁路呼叫将变为非旁路呼叫。</p>
<p>要使媒体旁路功能对特定中继起作用，需要在全局范围内启用该功能，并且需要对该中继启用该功能。使用 <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet 可在全局范围内启用媒体旁路功能。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableFastFailoverTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，会将网关在 10 秒内未应答的出站呼叫路由到下一个可用的中继；如果没有其他中继，则会自动丢弃该呼叫。在网络和网关响应缓慢的组织中，这可能导致不必要地丢弃呼叫。</p>
<p>默认值为 True。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableLocationRestriction</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，将为通过由 SIP 中继配置设置的指定集合管理的 SIP 中继传送的呼叫启用基于位置的语音路由。使用基于位置的语音路由，在路由呼叫时将同时考虑发出呼叫的用户的位置和接收呼叫的用户的位置。如果此属性设置为 True（默认值为 False），则您还应设置 NetworkSiteId 属性。</p>
<p>此参数是在 Lync Server 2013 2013 年 2 月版本中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMobileTrunkSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义服务提供商是否为移动运营商。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableOnlineVoice</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示 SIP 中继是否支持联机语音。使用联机语音，用户可创建本地 Lync Server 帐户，但其语音邮件由 Office 365 托管。默认值为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePIDFLOSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义是否通过所定义的网关来路由具有状态信息数据格式位置对象 (PIDF-LO) 的紧急呼叫。如果要将紧急呼叫路由到已认证的紧急服务提供商，需将此参数设置为 True。（位置信息将随呼叫一起传输。）</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableReferSupport</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>定义此中继是否支持接收来自中介服务器的 Refer 请求。</p>
<p>仅在以下情况时才可以启用媒体旁路功能：</p>
<p>- ConcentratedTopology 参数设置为 True</p>
<p>- EnableReferSupport 参数设置为 False 且 RTCPActiveCalls 和 RTCPCallsOnHold 设置为 False，或 EnableReferSupport 设置为 True</p>
<p>请注意，如果 EnableBypass 为 True 且 EnableReferSupport 为 False，则随后传输的旁路呼叫将变为非旁路呼叫。</p>
<p>默认值：True</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableRTPLatching</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一项通过 NAT（网络地址转换器）设备或防火墙建立 RTP/RTCP 连接的技术。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>EnableSessionTimer</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指定是否启用会话计时器。会话计时器用于确定特定会话是否仍处于活动状态。</p>
<p>请注意，即使此参数设置为 False，但如果远程连接启用了会话计时器，也会应用会话计时器。在这种情况下，中介服务器将响应来自远程实体的会话计时器探查。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableSignalBoost</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果将此参数设置为 True，服务提供商的 PSTN 网关、IP-PBX 或 SBC 将提高发送给中介服务器或 Lync Server 客户端的语音流中的音量。如果将此值设置为 False，将在中介服务器（对于非旁路呼叫）或 Lync Server 客户端（对于旁路呼叫）增大音量。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>ForwardCallHistory</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否将通过中继转发呼叫历史记录信息。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>ForwardPAI</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否将随呼叫一起转发 P-Asserted-Identity (PAI) 标头。PAI 标头提供验证呼叫者身份的方法。默认值为 False ($False)。</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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
<td><p>与中继配置设置的新集合关联的网络站点的网站 ID。如果 EnableLocationRestriction 属性设置为 True，则将使用为指定网站配置的设置管理通过此中继的基于位置的语音路由。可使用此命令检索网络站点 ID：</p>
<p>Get-CsNetworkSite | Select NetworkSiteID</p>
<p>此参数是在 Lync Server 2013 2013 年 2 月版本中引入的。</p></td>
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
<p>虽然可以通过此 cmdlet 直接创建该列表以及这些规则，但是建议您使用 <strong>New-CsOutboundTranslationRule</strong> cmdlet 创建出站转换规则，该 cmdlet 会创建规则并将其分配给范围匹配的中继配置。</p></td>
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
<td><p>如果将此参数设置为 True，会导致中介服务器在将统一资源标识符 (URI) 发送到服务提供商之前删除 URI 的前导加号 (+)。</p>
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
<p>您可直接使用此 cmdlet 创建该列表和相应规则。但是，建议您通过调用 <strong>New-CsSipResponseCodeTranslationRule</strong> cmdlet 来创建 SIP 响应代码转换规则。该 cmdlet 会创建规则并将其分配给范围匹配的中继配置。</p></td>
</tr>
<tr class="odd">
<td><p><em>SRTPMode</em></p></td>
<td><p>可选</p></td>
<td><p>SRTPMode</p></td>
<td><p>此参数的值可确定对 SRTP 的支持级别，以保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量。对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。可使用 <strong>New-CsMediaConfiguration</strong> cmdlet 和 <strong>Set-CsMediaConfiguration</strong> cmdlet 设置媒体配置。</p>
<p>有效值：</p>
<p>- Required：必须使用 SRTP 加密。</p>
<p>- Optional：如果网关支持 SRTP，将使用 SRTP。</p>
<p>- NotSupported:SRTP 加密不受支持，因此不使用该功能。</p>
<p>说明：仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为 NotSupported。</p>
<p>默认值：Required</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration 的对象。

## 另请参阅

#### 其他资源

[Remove-CsTrunkConfiguration](remove-cstrunkconfiguration.md)  
[Set-CsTrunkConfiguration](Set-CsTrunkConfiguration.md)  
[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)  
[Test-CsTrunkConfiguration](test-cstrunkconfiguration.md)  
[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)

