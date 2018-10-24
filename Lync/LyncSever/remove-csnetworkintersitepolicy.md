---
title: Remove-CsNetworkInterSitePolicy
TOCTitle: Remove-CsNetworkInterSitePolicy
ms:assetid: daf1afc8-cce4-4192-8ba4-05d26817198e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398963(v=OCS.15)
ms:contentKeyID: 49314450
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkInterSitePolicy

 

_**上一次修改主题：** 2015-03-09_

删除定义呼叫允许控制 (CAC) 配置内直接链接的站点间带宽限制的网络站点间策略。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkInterSitePolicy -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例删除 Identity 为 Reno\_Portland 的网络站点策略。

    Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

## 示例 2

在示例 2 中，删除在 CAC 配置内定义的所有网络站点策略。我们首先调用 **Get-CsNetworkInterSitePolicy** cmdlet 来检索所有网络站点策略的集合。然后，将此集合通过管道传递到 **Remove-CsNetworkInterSitePolicy** cmdlet，后者将删除集合中的每一项。

    Get-CsNetworkInterSitePolicy | Remove-CsNetworkInterSitePolicy

## 详细说明

当两个网络站点共享一条直接链路时，可定义这两个站点之间的音频和视频连接的带宽限制。此 cmdlet 可删除将带宽限制策略与两个直接连接的站点相关联的网络站点策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkInterSitePolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkInterSitePolicy"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要删除的网络站点策略的唯一标识符。网络站点策略只能在全局范围创建，因此该标识符不需要指定范围。它包含一个字符串，此字符串是一个用于标识该站点策略的唯一名称。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType 对象。接受通过管道传递的网络站点间策略对象的输入。

## 返回类型

此 cmdlet 不会返回值。它可删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)

