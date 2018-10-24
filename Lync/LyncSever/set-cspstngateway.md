---
title: Set-CsPstnGateway
TOCTitle: Set-CsPstnGateway
ms:assetid: 5d61e7e5-dacb-4dd3-bdd5-b757d98181d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398408(v=OCS.15)
ms:contentKeyID: 49312983
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPstnGateway

 

_**上一次修改主题：** 2015-03-09_

修改公用电话交换网 (PSTN) 网关的属性。PSTN 网关有助于在外部 PSTN 网络上的设备和内部企业语音网络上的设备之间路由呼叫。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsPstnGateway [-Identity <XdsGlobalRelativeIdentity>] [-AlternateByPassId <String>] [-Confirm [<SwitchParameter>]] [-Default <$true | $false>] [-Force <SwitchParameter>] [-GatewaySipClientTcpPort <UInt16>] [-GatewaySipClientTlsPort <UInt16>] [-MediationServer <String>] [-RepresentativeMediaIP <String>] [-Routable <$true | $false>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令可将网关 PstnGateway:192.168.0.240 配置为默认网关。这意味着 PstnGateway:192.168.0.240 可用于处理来自 Office Communications Server 2007 R2 的呼叫。

    Set-CsPstnGateway -Identity "PstnGateway:192.168.0.240" -Default $True

## 示例 2

示例 2 将配置组织中的所有 PSTN 网关，这确保了其中的每个网关都可以在出站路由中使用。为执行此操作，该命令将首先使用 **Get-CsService** cmdlet 和 PstnGateway 参数返回当前使用的所有 PSTN 网关的集合。然后，将此集合通过管道传递到 **ForEach-Object** cmdlet。**ForEach-Object** cmdlet 针对集合中的每个网关运行 **Set-CsPstnGateway** cmdlet，从而将每个网关的 Routable 属性设置为 True。

    Get-CsService -PstnGateway | ForEach-Object {Set-CsPstnGateway -Identity $_.Identity -Routable $True}

## 详细说明

PSTN 网关使企业语音用户不仅能够对 PSTN 网络上的人员进行电话呼叫，也能够接收来自 PSTN 网络上的人员的电话呼叫。这些网关充当中介服务器和 PSTN 网络之间的网桥。

在使用时分复用公共交换机 (PBX) 电话系统时，通常需要 PSTN 网关；在这种情况下，通常需要利用 PSTN 网关和中介服务器以便将企业语音呼叫路由到 PSTN 网络。相比之下，如果使用 IP-PBX 系统，则可以在 PBX 和中介服务器之间创建直接 SIP 连接，从而无需 PSTN 网关。

在安装和配置完 PSTN 网关后，可以使用 **Set-CsPstnGateway** cmdlet 对其进行管理。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsPstnGateway** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPstnGateway"}

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
<td><p><em>AlternateByPassId</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>代表备用绕过 ID 的全局唯一标识符 (GUID)。此 ID 由 Lync Server 自动生成并用于帮助消除“发夹”呼叫。这允许“发夹”呼叫自动绕过中介服务器，而无需定义单个子网并将其与所有站点和区域关联，具体取决于您配置系统的方式。</p>
<p>为执行此操作，通常需要全局启用绕过功能，以使用网络配置站点和区域，然后对 PSTN 网关的中继配置启用绕过功能。</p>
<p>来自 PSTN 网络的入站呼叫通过呼叫转接或同时响铃方式路由回到该网络时，会发生“发夹”呼叫。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Default</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果设置为 True，此网关将处理从 Office Communications Server 2007 R2 发送的呼叫。由一个中介服务器管理的网关集合中只能有一个默认网关。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此 cmdlet 时可能出现的任何确认提示或非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>GatewaySipClientTcpPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>侦听端口，用于通过传输控制协议 (TCP) 与中介服务器通信。默认值为 5066。</p></td>
</tr>
<tr class="even">
<td><p><em>GatewaySipClientTlsPort</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt16</p></td>
<td><p>侦听端口，用于通过传输层安全性 (TLS) 协议与中介服务器通信。默认值为 5067。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的 PSTN 网关的服务标识。例如：-Identity &quot;PstnGateway:192.168.0.240&quot;。</p>
<p>请注意，在指定 PSTN 网关时，可以不指定前缀“PstnGatewayServer:”。例如：-Identity &quot;atl-cs-001.litwareinc.com&quot;。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>MediationServer</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>要与 PSTN 网关关联的中介服务器的服务标识。例如：-MediationServer &quot;MediationServer:atl-cs-001.litwareinc.com&quot;。</p></td>
</tr>
<tr class="odd">
<td><p><em>RepresentativeMediaIP</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>与网关关联的媒体处理器的 IP 地址（如果处理器位置不同于信号地址）。媒体旁路和呼叫允许控制 (CAC) 是基于网关的媒体处理器的位置；默认情况下，与信号地址相同。如果两个位置不同（例如，媒体处理器位于远程站点，而信号对等实体位于中央站点），则必须使用媒体处理器的 IP 地址配置 RepresentativeMediaIP。</p>
<p>如果已在同一站点中部署多个媒体处理器且每个处理器都具有单独的 IP 地址，则可以在配置 RepresentativeMediaIP 属性时使用其中任何一个 IP 地址。</p></td>
</tr>
<tr class="even">
<td><p><em>Routable</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果设置为 True，则可以在出站路由中使用网关。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsPstnGateway** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Set-CsPstnGateway** cmdlet 不会返回任何对象或值。但 cmdlet 会修改 Microsoft.Rtc.Management.Xds.DisplayPstnGateway 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsService](get-csservice.md)

