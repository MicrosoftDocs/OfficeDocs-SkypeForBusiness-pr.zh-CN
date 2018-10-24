---
title: New-CsNetworkMediaBypassConfiguration
TOCTitle: New-CsNetworkMediaBypassConfiguration
ms:assetid: 24055ae5-7fc8-4ca5-9e65-ac3a1f17b405
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425718(v=OCS.15)
ms:contentKeyID: 49312258
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkMediaBypassConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建新的全局设置以便实现媒体旁路功能。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkMediaBypassConfiguration [-AlwaysBypass <$true | $false>] [-BypassID <String>] [-Enabled <$true | $false>] [-EnableDefaultBypassID <$true | $false>] [-EnabledForAudioVideoConferences <$true | $false>] [-ExternalBypassMode <Off | ICE | Any>] [-InternalBypassMode <Off | ICE | Any>]

## 示例

## 示例 1

此示例中的命令启用媒体旁路功能，并将其配置为始终尝试旁路。此示例中的第一行调用 **New-CsNetworkMediaBypassConfiguration** cmdlet。我们向此 cmdlet 传递以下两个参数：AlwaysBypass 和 Enabled，并将这两个参数同时设置为 True ($true)。将 Enabled 设置为 True 可启用媒体旁路功能，而将 AlwaysBypass 设置为 True 可确保在所有调用中尝试媒体旁路。（请注意，设置这两个参数将自动为 BypassID 属性生成值。）**New-CsNetworkMediaBypassConfiguration** cmdlet 仅在内存中创建对象，因此我们将该对象分配给变量 $a。

媒体旁路配置随网络配置设置一起存储。因此，在此示例的第二行中，我们调用 **Set-CsNetworkConfiguration** cmdlet，并向 MediaBypassSettings 参数传递在第一行中创建的媒体旁路配置对象 ($a)，从而将媒体旁路配置更改保存到网络配置中。

    $a = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
    Set-CsNetworkConfiguration -MediaBypassSettings $a

## 示例 2

Lync Server 未提供 **Set-CsNetworkMediaBypassConfiguration** cmdlet，因此为了修改现有设置，必须创建新配置（如示例 1 所示）以替换现有配置，或者必须通过以下方式修改现有设置：检索并修改现有设置，然后使用 **Set-CsNetworkConfiguration** cmdlet 保存更改。此示例演示如何使用后一种方法来关闭 AlwaysBypass 选项。

此示例中的第一行检索现有媒体旁路设置。它通过调用 **Get-CsNetworkConfiguration** cmdlet 进行检索。对此 cmdlet 的调用位于括号中，以确保在运行该命令的任何其他部分之前完成此 cmdlet。**Get-CsNetworkConfiguration** cmdlet 会检索整个网络配置的所有设置。由于我们仅关注媒体旁路设置，因此指定 MediaBypassSettings 属性将仅检索这些设置。我们将这些设置分配给变量 $a。

在第二行中，通过为 AlwaysBypass 属性分配值 False ($false) 来修改变量 $a 中存储的设置。最后，在第三行中，我们调用 **Set-CsNetworkConfiguration** cmdlet，以向 MediaBypassSettings 参数传递 $a 变量，从而将所做更改保存到 AlwaysBypass 属性中。

    $a = (Get-CsNetworkConfiguration).MediaBypassSettings
    $a.AlwaysBypass = $false
    Set-CsNetworkConfiguration -MediaBypassSettings $a

## 详细说明

此 cmdlet 可创建用于实现音频连接的媒体旁路功能的全局设置。

与 Lync Server 中的大多数 New- cmdlet 不同，此 cmdlet 不会立即保存新配置，而仅在内存中创建设置。必须将此 cmdlet 创建的对象保存到变量中，然后分配给网络配置的 MediaBypassSettings 属性。（有关详细信息，请参阅本主题中的“示例”部分。）

使用此 cmdlet 创建的设置只能通过访问全局网络配置的 MediaBypassSettings 属性进行检索。要检索这些设置，请运行以下命令：(Get-CsNetworkConfiguration).MediaBypassSettings。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsNetworkMediaBypassConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkMediaBypassConfiguration"}

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
<td><p><em>AlwaysBypass</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果将此参数设置为 True，则会在所有调用中尝试媒体旁路。</p>
<p>仅当禁用了呼叫允许控制 (CAC) 时，才应将此参数值设置为 True。仅对于符合以下条件的部署，才应将此参数设置为 True：</p>
<p>- 不需要带宽控制。</p>
<p>- 不需要精确的配置以确定何时发生旁路。</p>
<p>- 网关与客户端之间有完全连接。</p>
<p>如果 Enabled 参数设置为 True 且 AlwaysBypass 设置为 False，旁路逻辑将使用网络配置站点和区域来确定何时可能发生旁路。</p>
<p>如果将 AlwaysBypass 设置为 True，但同时未将 Enabled 参数的值设置为 True，您将收到一条警告消息：如果将 Enabled 设置为 False，将忽略 AlwaysBypass 设置。</p>
<p>如果将 AlwaysBypass 和 Enabled 都设置为 True，则会自动生成一个旁路 ID，该 ID 将存储在 BypassID 属性中。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>BypassID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>媒体旁路 ID。如果 AlwaysBypass 参数设置为 True，且为该参数提供了值，则此 BypassID 参数将与所有子网关联。如果 AlwaysBypass 为 False，则 BypassID 值将与不在网络配置站点和区域中的所有子网关联。</p>
<p>此 ID 必须采用 GUID 格式（如 96f14dea-5170-429a-b92b-f1cb909c4bb6）。但是，您通常不需要设置或更改此参数。当 Enabled 设置为 True 或满足以下任意条件时，将自动生成该值：1) AlwaysBypass 设置为 True，或者 2) EnableDefaultBypassID 参数设置为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>将此参数设置为 True 可启用媒体旁路。启用媒体旁路功能后，将根据 AlwaysBypass 设置的值做出是否旁路的决定，如下所述：</p>
<p>- 如果 AlwaysBypass 为 True，则将对所有呼叫尝试旁路。</p>
<p>- 如果 AlwaysBypass 为 False，则使用网络配置站点和区域来确定旁路的可能性。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDefaultBypassID</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>仅当 AlwaysBypass 设为 False 时，此值才适用。</p>
<p>如果将该值设置为 True，会自动生成一个默认旁路 ID。此自动生成的值将存储在 BypassID 属性中。</p>
<p>如果存在远程站点具有限定带宽链路的完美连接核心，此参数将非常有用。管理员只需要定义通过网络配置站点和区域与远程站点关联的子网。无需定义任何与此核心关联的子网，并且在这些子网之间将自动尝试旁路。</p>
<p>默认值：False</p></td>
</tr>
<tr class="odd">
<td><p><em>EnabledForAudioVideoConferences</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>指示是否应该对音频/视频会议使用媒体旁路。默认值为 False ($False)。</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalBypassMode</em></p></td>
<td><p>可选</p></td>
<td><p>BypassModeEnumType</p></td>
<td><p>保留以供将来使用。Lync Server 中不支持外部媒体旁路功能。</p>
<p>默认值：Off</p></td>
</tr>
<tr class="odd">
<td><p><em>InternalBypassMode</em></p></td>
<td><p>可选</p></td>
<td><p>BypassModeEnumType</p></td>
<td><p>此参数的值控制组织从网络内部连接的客户端何时可以尝试执行媒体旁路。如果 Enabled 设置为 True，该值将自动更改为 Any。此参数的其他值保留供将来使用。</p>
<p>默认值：Off</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.MediaBypassSettingsType 的对象引用。

## 另请参阅

#### 其他资源

[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)  
[Set-CsNetworkConfiguration](set-csnetworkconfiguration.md)

