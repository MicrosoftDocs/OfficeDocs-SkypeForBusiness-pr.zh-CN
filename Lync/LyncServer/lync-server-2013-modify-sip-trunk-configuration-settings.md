---
title: Lync Server 2013：修改 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改 SIP 中继配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络（PSTN）网关、IP 公共分支 exchange （PBX）或会话边界控制器（SBC）之间的关系和能力。 这些设置可执行如下所指定内容的操作：

  - 是否在中继上启用媒体旁路功能。

  - 发送实时传输控制协议（RTCP）数据包的条件。

  - 每个主干上是否需要安全的实时协议（SRTP）加密。

安装 Microsoft Lync Server 2013 时，将为你创建一个全局 SIP 中继配置设置集合。 此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。 以后可以使用 Lync Server 控制面板或 Windows PowerShell 修改这些集合中的任何一个。

使用 Lync Server 控制面板修改 SIP 中继配置设置时，可以使用以下选项：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 设置</th>
<th>PowerShell 参数</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>Identity</p></td>
<td><p>集合的唯一标识符。此属性为只读；您无法更改中继配置设置集合的标识。</p></td>
</tr>
<tr class="even">
<td><p>描述</p></td>
<td><p>描述</p></td>
<td><p>为管理员提供了存储有关设置的附加信息（例如，中继配置的用途）的方法。</p></td>
</tr>
<tr class="odd">
<td><p>支持的最大早期对话数</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>服务提供商的 PSTN 网关、IP-PBX 或 SBC 可以接收的分叉响应的最大数目，这些响应是针对发送到中介服务器的邀请的。</p></td>
</tr>
<tr class="even">
<td><p>加密支持级别</p></td>
<td><p>SRTPMode</p></td>
<td><p>指示用于保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量的支持级别。 对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。 通过使用<a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">CsMediaConfiguration</a>和<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> cmdlet 设置媒体配置。</p>
<p>允许的值包括：</p>
<ul>
<li><p>Required：必须使用 SRTP 加密。</p></li>
<li><p>Optional：如果网关支持 SRTP，将使用 SRTP。</p></li>
<li><p>Not Supported：SRTP 加密不受支持，因此不使用该功能。</p></li>
</ul>
<p>仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为“Not Supported”。</p></td>
</tr>
<tr class="odd">
<td><p>引用支持</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>如果设置为“允许将引用发送到网关”<strong></strong>，则指示中继支持接收来自中介服务器的引用请求。</p>
<p>如果设置为“允许使用第三方呼叫控制的引用”<strong></strong>，则指示 3pcc 协议可用于允许转接的呼叫绕过宿主网站。 3pcc 也称为&quot;第三方控件，&quot;并在第三方用于连接一对呼叫者时（例如，操作员将来自人员 a 的呼叫拨入到 B）时发生。</p></td>
</tr>
<tr class="even">
<td><p>启用媒体旁路</p></td>
<td><p>EnableBypass</p></td>
<td><p>指示是否为此中继启用媒体旁路。仅当启用了“集中式媒体处理”<strong></strong>时才能启用媒体旁路。</p></td>
</tr>
<tr class="odd">
<td><p>集中式媒体处理</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>指示是否有已知的媒体终结点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）</p></td>
</tr>
<tr class="even">
<td><p>启用 RTP 闭锁</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一种通过 NAT（网络地址转换器）设备或防火墙实现 RTP/RTCP 连接的技术。</p></td>
</tr>
<tr class="odd">
<td><p>启用呼叫转移历史记录</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>指示是否通过中继转移呼叫历史记录信息。</p></td>
</tr>
<tr class="even">
<td><p>启用转移 P-Asserted-Identity 数据</p></td>
<td><p>ForwardPAI</p></td>
<td><p>指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。PAI 标头提供了一种验证呼叫者身份的方法。</p></td>
</tr>
<tr class="odd">
<td><p>启用出站路由故障转移计时器</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>指示是否将网关在 10 秒内未应答的出站呼叫路由到下一个可用中继；如果没有任何其他中继，则将自动放弃呼叫。在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</p></td>
</tr>
<tr class="even">
<td><p>关联的 PSTN 用法</p></td>
<td><p>PSTNUsages</p></td>
<td><p>分配给中继的 PSTN 用法的集合。</p></td>
</tr>
<tr class="odd">
<td><p>要测试的已转换号码</p></td>
<td><p>不适用</p></td>
<td><p>可用于对中继配置设置执行临时测试的电话号码。</p></td>
</tr>
<tr class="even">
<td><p>关联的转换规则</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>应用于出站路由处理的呼叫（路由到 PBX 或 PSTN 目标的呼叫）的电话号码转换规则的集合。</p></td>
</tr>
<tr class="odd">
<td><p>被叫号码转换规则</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>分配给中继的出站呼叫号码转换规则的集合。</p></td>
</tr>
<tr class="even">
<td><p>要测试的电话号码</p></td>
<td><p>不适用</p></td>
<td><p>可用于对转换规则执行临时测试的电话号码。</p></td>
</tr>
<tr class="odd">
<td><p>主叫号码</p></td>
<td><p>不适用</p></td>
<td><p>指示要测试的电话号码是呼叫者的电话号码。</p></td>
</tr>
<tr class="even">
<td><p>被叫号码</p></td>
<td><p>不适用</p></td>
<td><p>指示要测试的电话号码是被呼叫的人员的电话号码。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lync Server New-cstrunkconfiguration cmdlet 支持 "Lync Server 控制面板" 中未显示的其他属性。 有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">new-cstrunkconfiguration</A> cmdlet 的帮助主题。



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 修改 SIP 中继配置设置

1.  在 Lync Server "控制面板" 中，单击 "**语音路由**"，然后单击 "**中继配置**"。

2.  在“Trunk 配置”**** 选项卡上，双击要修改的中继配置设置。请注意，您一次只能编辑一个设置集合。如果要对多个集合进行同一更改，请改用 Windows PowerShell。

3.  在“编辑 Trunk 配置”**** 对话框中，进行适当的选择，然后单击“确定”****。

4.  集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。

5.  在“未提交的语音配置设置”**** 对话框中，单击“确定”****。

6.  在 " **Microsoft Lync Server 2013 控制面板**" 对话框中，单击 **"确定"**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

