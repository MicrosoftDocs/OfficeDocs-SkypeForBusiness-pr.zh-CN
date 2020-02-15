---
title: Lync Server 2013：创建新的中继配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04392b4157f0c1a12b0bcfa9e7125183a76864cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建一个新的中继配置设置集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：

  - 是否应对中继启用媒体旁路。

  - 发送实时传输控制协议 (RTCP) 数据包的条件。

  - 每个中继上是否需要安全实时协议 (SRTP) 加密。

安装 Microsoft Lync Server 2013 时，将为您创建一个全局 SIP 中继配置设置集合。 此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。

使用 Lync Server 控制面板创建 SIP 中继配置设置时，可以使用以下选项：


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
<td><p>Name</p></td>
<td><p>标识</p></td>
<td><p>集合的唯一标识符。此属性为只读；您无法更改中继配置设置集合的标识。</p></td>
</tr>
<tr class="even">
<td><p>说明</p></td>
<td><p>说明</p></td>
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
<td><p>指示用于保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量的支持级别。 对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。 媒体配置通过使用<a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">set-csmediaconfiguration</a>和<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-csmediaconfiguration</a> cmdlet 进行设置。</p>
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
<p>如果设置为“允许使用第三方呼叫控制的引用”<strong></strong>，则指示 3pcc 协议可用于允许转接的呼叫绕过宿主网站。 3pcc 也称为&quot;第三方控件，&quot;在使用第三方连接一对呼叫者时（例如，操作员将来自某人 a 的呼叫放入个人 B 时）发生此事件。</p></td>
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
<td><p>分配给中继的出站主叫号码转换规则的集合。</p></td>
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
> Lync Server Remove-cstrunkconfiguration cmdlet 支持未在 Lync Server 控制面板中显示的其他属性。 有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">remove-cstrunkconfiguration</A> cmdlet 的帮助主题。



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建新的中继配置设置

1.  在 "Lync Server 控制面板" 中，单击 "**语音路由**"，然后单击 "**中继配置**"。

2.  在“Trunk 配置”**** 选项卡上，单击“新建”****，然后单击“站点 Trunk”**** 以创建站点作用域的新设置，或“池 Trunk”**** 创建服务作用域的新设置。

3.  在“选择站点”**** 或“选择服务”**** 对话框（根据您是创建站点作用域还是服务作用域设置显示的对话框），选择新配置设置的位置，然后单击“确定”****。如果对话框为空，则意味着没有位置可创建新设置；例如，如果“选择站点”**** 对话框为空，则意味着您的所有站点已分配有中继配置站点的集合，并且每个站点（以及每个服务）只能承载一个此类集合。在此情况下，您可删除现有集合并创建新的集合，或只修改现有集合。

4.  在“新建 Trunk 配置”**** 对话框中，进行适当的选择，然后单击“确定”****。

5.  集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。

6.  在“未提交的语音配置设置”**** 对话框中，单击“确定”****。

7.  在“Microsoft Lync Server 2013 控制面板”**** 对话框中，单击“确定”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

