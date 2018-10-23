---
title: Get-CsNetworkInterSitePolicy
TOCTitle: Get-CsNetworkInterSitePolicy
ms:assetid: a4a64048-f8d7-483a-9565-0c6f3b0937b7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412769(v=OCS.15)
ms:contentKeyID: 49313824
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkInterSitePolicy

 

_**上一次修改主题：** 2015-03-09_

检索一个或多个网络站点间策略，这些策略用于定义在呼叫允许控制 (CAC) 配置中直接链接的站点之间的带宽限制。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkInterSitePolicy [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkInterSitePolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

调用不带参数的 **Get-CsNetworkInterSitePolicy** cmdlet 将检索在两个直接链接的网络站点之间定义的所有网络站点策略。

    Get-CsNetworkInterSitePolicy

## 示例 2

此示例检索 Identity 为 Reno\_Portland 的网络站点策略。

    Get-CsNetworkInterSitePolicy -Identity Reno_Portland

## 示例 3

示例 3 检索 Identity 值中包含字符串 Reno 的所有网络站点策略。传递给 Filter 参数的值中的通配符 (\*) 表示“任意字符或字符集”。也就是说，字符串 \*Reno\* 将与以任意字符开头、后跟字符串 Reno 且其后是任意字符的 Identity 值匹配。

    Get-CsNetworkInterSitePolicy -Filter *Reno*

## 示例 4

此示例检索所有未分配带宽策略配置文件的网络站点策略。此命令首先调用 **Get-CsNetworkInterSitePolicy** cmdlet，这将检索所有网络站点策略的集合（如示例 1 中所示）。然后，将此集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 将该集合范围缩减到仅包含未分配带宽策略配置文件的站点策略。这是通过比较以查看每个站点策略的 BWPolicyProfileID 属性是否等于 (-eq) Null ($null) 来实现的。

    Get-CsNetworkInterSitePolicy | Where-Object {$_.BWPolicyProfileID -eq $null}

## 详细说明

当两个网络站点共享一条直接链路时，可定义这两个站点之间的音频和视频连接的带宽限制。此 cmdlet 可检索一个或多个将带宽限制设置与直接连接的站点进行关联的网络站点策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkInterSitePolicy** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkInterSitePolicy"}

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
<td><p>包含通配符的字符串，这些通配符可搜索 Identity 值与通配符字符串相匹配的策略。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要检索的网络站点策略的唯一标识符。网络站点策略只能在全局范围创建，因此该标识符不需要指定范围。此标识符包含一个字符串，作为标识该策略的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络站点间策略信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

检索一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterSitePolicy](new-csnetworkintersitepolicy.md)  
[Remove-CsNetworkInterSitePolicy](remove-csnetworkintersitepolicy.md)  
[Set-CsNetworkInterSitePolicy](set-csnetworkintersitepolicy.md)

