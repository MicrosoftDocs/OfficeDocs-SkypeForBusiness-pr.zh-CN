---
title: Get-CsNetworkBandwidthPolicyProfile
TOCTitle: Get-CsNetworkBandwidthPolicyProfile
ms:assetid: 31784852-0cf4-4114-bf92-5eef6f346c47
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425815(v=OCS.15)
ms:contentKeyID: 49312419
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkBandwidthPolicyProfile

 

_**上一次修改主题：** 2015-03-09_

检索一个或多个网络带宽策略配置文件。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkBandwidthPolicyProfile [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkBandwidthPolicyProfile [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

调用不带任何参数的 **Get-CsNetworkBandwidthPolicyProfile** cmdlet 将检索在 Lync Server 部署中定义的所有带宽策略配置文件。

    Get-CsNetworkBandwidthPolicyProfile

## 示例 2

此示例检索 Identity 为 LowBWProfile 的带宽策略配置文件。由于标识必须是唯一的，因此将最多返回一个配置文件。

    Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## 示例 3

在此示例中，使用 Filter 参数来指定要根据通配符字符串检索的一个或多个配置文件。我们使用了字符串 \*50MB\*，这表示要检索 Identity 值的任意位置包含字符串 50MB 的所有带宽策略配置文件。例如，这将检索标识为“BW profile for 50MB links”、“50MB audio limit”和“video limits of 50MB”之类的配置文件。

    Get-CsNetworkBandwidthPolicyProfile -Filter *50MB*

## 详细说明

带宽策略是呼叫允许控制 (CAC) 的一部分，用于定义某些形式的带宽限制。（在 Lync Server 中，只能为音频和视频形式指定带宽限制。）此 cmdlet 可检索一个或多个容器配置文件以查找这些策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkBandwidthPolicyProfile** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkBandwidthPolicyProfile"}

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
<td><p>一个包含通配符的字符串，用于检索 Identity 值与通配符模式匹配的带宽策略配置文件。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一标识要检索的带宽策略配置文件的字符串值。指定 Identity 将最多检索一个配置文件。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络带宽策略配置文件。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

返回一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Remove-CsNetworkBandwidthPolicyProfile](remove-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)

