---
title: Set-CsNetworkInterSitePolicy
TOCTitle: Set-CsNetworkInterSitePolicy
ms:assetid: 973979bc-db2c-47a6-909e-5949a927f51c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398772(v=OCS.15)
ms:contentKeyID: 49313669
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkInterSitePolicy

 

_**上一次修改主题：** 2015-03-09_

修改现有的网络站点间策略，该策略用于定义呼叫允许控制 (CAC) 配置中直接链接的站点之间的带宽限制。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkInterSitePolicy [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkInterSitePolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkSiteID1 <String>] [-NetworkSiteID2 <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例修改 Identity 为 Reno\_Portland 的网络站点策略。我们使用 BWPolicyProfileID 参数将与此网络站点策略关联的带宽策略配置文件更改为 HighBWLimits。

    Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

## 详细说明

当两个网络站点共享一条直接链路时，可定义这两个站点之间的音频和视频连接的带宽限制。此 cmdlet 修改将带宽限制策略与两个直接连接的站点关联的网络站点间策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkInterSitePolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkInterSitePolicy"}

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
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>将定义此站点策略的限制的带宽策略配置文件的标识。您可以通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 来检索可用配置文件的列表。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的网络站点策略的唯一标识符。网络站点策略只能在全局范围创建，因此该标识符不需要指定范围。它包含一个字符串，此字符串是一个用于标识该站点策略的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>InterNetworkSitePolicyType</p></td>
<td><p>已在内存中修改的站点策略的对象引用。此对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType，并且可以通过调用 <strong>Get-CsNetworkInterSitePolicy</strong> cmdlet 来检索。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkSiteID1</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与此策略关联的两个站点之一的标识 (NetworkSiteID)。NetworkSiteID1 和 NetworkSiteID2 的组合必须是唯一的（例如，不能定义用于连接 Reno 和 Portland 的两个站点策略）。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID2</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与此策略关联的两个站点之一的标识 (NetworkSiteID)。NetworkSiteID1 和 NetworkSiteID2 的组合必须是唯一的（例如，不能定义用于连接 Reno 和 Portland 的两个站点策略）。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType 对象。接受通过管道传递的网络站点间策略对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)

