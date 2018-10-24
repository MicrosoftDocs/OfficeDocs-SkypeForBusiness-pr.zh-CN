---
title: New-CsNetworkBWPolicy
TOCTitle: New-CsNetworkBWPolicy
ms:assetid: bbc91bd1-453c-4ae6-bb77-3b6be9429ed0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412916(v=OCS.15)
ms:contentKeyID: 49314053
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBWPolicy

 

_**上一次修改主题：** 2015-03-09_

在内存中创建可以应用于带宽策略配置文件的带宽策略。在 Lync Server 中，该策略适用于音频或视频带宽。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkBWPolicy -BWLimit <UInt32> -BWPolicyModality <Audio | Video> -BWSessionLimit <UInt32>

## 示例

## 示例 1

此示例创建一个新的带宽策略，并将其分配给变量 $bwp。**New-CsNetworkBWPolicy** cmdlet 的所有参数都是必需的。在此示例中，将总带宽限制 (BWLimit) 指定为 2000 kbps，将带宽会话限制 (BWSessionLimit) 指定为 300 kbps，并将这些限制应用于视频会话（-BWPolicyModality 视频）。

    $bwp = New-CsNetworkBWPolicy -BWLimit 200 -BWSessionLimit 3000 -BWPolicyModality video

## 示例 2

示例 2 在示例 1 的基础上有所展开，将新带宽策略分配给策略配置文件。第 1 行中的命令与示例 1 相同：它将创建视频带宽限制。然后第 2 行将调用 **New-CsNetworkBandwidthPolicyProfile** cmdlet，以将该策略添加至新配置文件。新配置文件将接收 Identity LowBWLimit。然后使用 BWPolicy 参数，将其值设为 $bwp，该值是包含第 1 行中创建的新带宽策略的变量。

    $bwp = New-CsNetworkBWPolicy -BWLimit 200 -BWSessionLimit 3000 -BWPolicyModality video
    New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -BWPolicy $bwp

## 详细说明

此 cmdlet 可新建带宽策略。带宽策略用于为某些形式定义带宽限制。（在 Lync Server 中，只能为音频和视频形式指定带宽限制。）由于带宽策略仅在内存中创建，因此必须将输出分配给变量，然后作为参数值传递到 **New-CsNetworkBandwidthPolicyProfile** cmdlet 或 **Set-CsNetworkBandwidthPolicyProfile** cmdlet 的 BWPolicy 参数。带宽策略应用于策略配置文件，后者可以在单个配置文件中存储多个策略，也是通话允许控制 (CAC) 的全局网络配置的一部分。

请注意，建议您通过调用 **New-CsNetworkBandwidthPolicyProfile** 或 **Set-CsNetworkBandwidthPolicyProfile** cmdlet，并指定 AudioBWLimit、AudioBWSessionLimit、VideoBWLimit 和 VideoBWSessionLimit 参数的值，直接为带宽策略配置文件分配音频和视频策略。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsNetworkBWPolicy** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBWPolicy"}

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
<td><p><em>BWLimit</em></p></td>
<td><p>必需</p></td>
<td><p>System.UInt32</p></td>
<td><p>BWPolicyModality 参数指定类型的所有并发会话的最大总带宽（单位：kbps）。</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicyModality</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyModality</p></td>
<td><p>确定受限制的带宽类型。</p>
<p>有效值：Audio、Video</p></td>
</tr>
<tr class="odd">
<td><p><em>BWSessionLimit</em></p></td>
<td><p>必需</p></td>
<td><p>System.UInt32</p></td>
<td><p>允许用于 BWPolicyModality 参数指定类型的单个会话的最大带宽（单位：kbps）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)

