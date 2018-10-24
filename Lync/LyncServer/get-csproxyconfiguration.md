---
title: Get-CsProxyConfiguration
TOCTitle: Get-CsProxyConfiguration
ms:assetid: e4836619-026f-4df0-adbd-aa5216e36368
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399011(v=OCS.15)
ms:contentKeyID: 49314547
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsProxyConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回有关组织中当前使用的代理服务器配置设置的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsProxyConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsProxyConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令返回组织中当前使用的所有代理配置设置的集合。这是通过调用不带任何参数的 **Get-CsProxyConfiguration** cmdlet 实现的。

    Get-CsProxyConfiguration

## 示例 2

在示例 2 中，返回有关 Identity 为 service:EdgeServer:atl-cs-001.litwareinc.com 的代理配置设置的信息。由于标识必须是唯一的，因此该命令返回的设置集合始终不会超过一个。

    Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"

## 示例 3

示例 3 返回有关已在服务范围配置的所有代理设置的信息。为此，该命令调用带有 Filter 参数的 **Get-CsProxyConfiguration** cmdlet；筛选器值“service:\*”可确保仅返回 Identity 以字符串值“service:”开头的设置。

    Get-CsProxyConfiguration -Filter "service:*"

## 示例 4

示例 4 返回有关不允许使用客户端证书作为身份验证机制的代理配置设置的信息。为了执行此任务，该命令首先使用 **Get-CsProxyConfiguration** cmdlet 返回当前使用的所有代理配置设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅选择 UseCertificateForClientToProxyAuth 属性等于 False 的设置。

    Get-CsProxyConfiguration | Where-Object {$_.UseCertificateForClientToProxyAuth -eq $False}

## 示例 5

示例 5 返回客户端消息的最大正文大小小于 5000 KB 的所有代理配置设置。为此，该命令首先调用不带任何参数的 **Get-CsProxyConfiguration** cmdlet；这将返回当前使用的所有代理配置设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会挑选出 MaxClientMessageBodySizeKb 属性小于 5000 KB 的设置。

    Get-CsProxyConfiguration | Where-Object {$_.MaxClientMessageBodySizeKb -lt 5000}

## 详细说明

Lync Server 用于通过代理服务器配置设置来管理代理服务器。这些设置可在全局范围和服务范围（但仅限边缘服务器和注册器服务）应用，用于控制可供客户端终结点使用的身份验证协议以及是否将在传入和传出代理服务器连接上使用压缩等设置。当安装 Lync Server 时，系统将自动为您创建代理服务器配置设置的全局集合。如前所述，您也可以在服务范围创建其他集合。

**Get-CsProxyConfiguration** cmdlet 用于返回组织中当前使用的任何代理服务器配置设置的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsProxyConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsProxyConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以在指定要返回的代理配置设置时使用通配符。例如，以下语法返回在服务范围配置的所有设置：-Filter &quot;service:*&quot;。</p>
<p>不能在同一个命令中同时使用 Filter 和 Identity 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要返回的代理服务器配置设置的唯一标识符。要返回全局设置，请使用以下语法：-Identity global。要返回在服务范围配置的设置，请使用以下类似语法：-Identity &quot;service:EdgeServer:atl-cs-001.litwareinc.com&quot;。请注意，在指定 Identity 时不能使用通配符。如果要（或需要）使用通配符，请改用 Filter 参数。</p>
<p>如果未包括此参数，<strong>Get-CsProxyConfiguration</strong> cmdlet 将返回组织中当前使用的所有代理服务器设置。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而非中央管理存储本身检索代理配置数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsProxyConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsProxyConfiguration** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.ProxySettings 对象的实例。

## 另请参阅

#### 其他资源

[New-CsProxyConfiguration](new-csproxyconfiguration.md)  
[Remove-CsProxyConfiguration](remove-csproxyconfiguration.md)  
[Set-CsProxyConfiguration](set-csproxyconfiguration.md)

