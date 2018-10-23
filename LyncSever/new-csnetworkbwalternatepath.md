---
title: New-CsNetworkBWAlternatePath
TOCTitle: New-CsNetworkBWAlternatePath
ms:assetid: 9017378e-4583-42bc-9572-aa8e9571cfe3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398732(v=OCS.15)
ms:contentKeyID: 49313580
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkBWAlternatePath

 

_**上一次修改主题：** 2015-03-09_

创建新设置，用于定义是否可以通过 Internet 将媒体路由至备用路径以进行带宽受限连接。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkBWAlternatePath -AlternatePath <$true | $false> -BWPolicyModality <Audio | Video>

## 示例

## 示例 1

此示例创建一个新的网络带宽备用路径，并将这些设置分配给新创建的区域。示例中的第一行调用 **New-CsNetworkBWAlternatePath** cmdlet 创建新的备用路径。备用路径仅具有两个属性：BWPolicyModality，必须设置为 audio 或 video（在此示例中使用 audio）；以及 AlternatePath，必须设置为 True 或 False（在此示例中使用 True）。我们将此 cmdlet 的输出（即，对刚刚创建的备用路径对象的引用）分配给变量 $a。

示例的第 2 行在创建新的网络区域时使用上述新创建的备用路径。为执行此操作，我们调用 **New-CsNetworkRegion** cmdlet，并传递标识 NorthAmerica。我们分配所需参数 CentralSite 的值（在此示例中，此区域的中央站点的名称为 Redmond-NA-MLS），然后指定 BWAlternatePaths 参数，并向其传递包含刚刚创建的备用路径对象的变量 ($a)。

    $a = New-CsNetworkBWAlternatePath -BWPolicyModality "audio" -AlternatePath $true
    New-CsNetworkRegion -Identity NorthAmerica -CentralSite Redmond-NA-MLS -BWAlternatePaths $a

## 详细说明

Lync Server 中的呼叫允许控制 (CAC) 配置可能包含两种内容形式：音频和视频。可针对上述每种内容形式设置带宽限制。如果带宽限制将阻止完成呼叫，该呼叫可通过 Internet 采用允许建立该呼叫的备用路径。此 cmdlet 用于创建相应设置，这些设置定义是否可以根据内容形式通过 Internet 将呼叫路由至备用路径。这些设置基于 CAC 配置中的每个区域进行应用。

此 cmdlet 不会立即保存新创建的设置，而仅在内存中创建设置。要将这些设置应用到网络中的某区域，需要将此 cmdlet 的输出分配给一个变量，然后将该变量用作 **New-CsNetworkRegion** cmdlet 或 **Set-CsNetworkRegion** cmdlet 的 BWAlternatePaths 参数的值。请注意，您可以使用 **New-CsNetworkRegion** cmdlet 和 **Set-CsNetworkRegion** cmdlet 的 AudioAlternatePath 和 VideoAlternatePath 参数来直接应用这些设置，而不必调用 **New-CsNetworkBWAlternatePath** cmdlet 来创建新对象。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsNetworkBWAlternatePath** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkBWAlternatePath"}

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
<td><p><em>AlternatePath</em></p></td>
<td><p>必需</p></td>
<td><p>Boolean</p></td>
<td><p>当主要路径中没有充足的带宽时，将此参数设置为 True 可允许通过备用路径路由在 BWPolicyModality 参数的指定内容形式（音频或视频）的媒体中执行的呼叫。</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicyModality</em></p></td>
<td><p>必需</p></td>
<td><p>BWPolicyModality</p></td>
<td><p>应用备用路径设置的内容形式。</p>
<p>有效值：audio、video</p>
<p>完整数据类型：Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyModality</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWAlternatePathType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)

