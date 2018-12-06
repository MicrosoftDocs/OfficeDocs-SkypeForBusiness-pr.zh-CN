---
title: New-CsNetworkSubnet
TOCTitle: New-CsNetworkSubnet
ms:assetid: 15af44bd-d798-435c-9c27-df47ab475023
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398226(v=OCS.15)
ms:contentKeyID: 49312104
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkSubnet

 

_**上一次修改主题：** 2015-03-09_

Creates a new network subnet. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkSubnet -SubnetID <String> <COMMON PARAMETERS>

    New-CsNetworkSubnet -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -MaskBits <Int32> [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-NetworkSiteID <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example demonstrates how to create a new subnet object that represents the subnet 172.11.15.0/24. The Identity of the subnet is set to 172.11.15.0. This value will automatically be assigned as the SubnetID. A subnet must have mask bits defined. That is done by supplying a value--in this case 24--to the MaskBits parameter. Finally, the site ID Vancouver is passed to the NetworkSiteID parameter to associate this subnet with that site.

    New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver

## EXAMPLE 2

Example 2 reads from a CSV file to create a series of subnets. The CSV file in this example looks something like this:

Identity, Mask, SiteID

172.11.12.0, 24, Redmond

172.11.13.0, 24, Chicago

172.11.14.0, 25, Vancouver

172.11.15.0, 31, Paris

...

The example starts by calling the **Import-CSV** cmdlet, passing it the path to a CSV file. This cmdlet will read the contents of that file into memory. Those file contents are then piped to the foreach function. The foreach function iterates through the contents one line at a time. As you can see from the example file, the first line is a list of headings that define the rest of the contents; the foreach function will use these headings to access the comma-separated values by name.

Inside the foreach statement, the **New-CsNetworkSubnet** cmdlet is called. As foreach iterates through each line of the file contents, that line is passed as the values for the **New-CsNetworkSubnet** cmdlet parameters. For example, the first time through the foreach statement, the **New-CsNetworkSubnet** cmdlet will create a subnet with the Identity 172.11.12.0: this is the value in the Identity position in the first comma-separated line of values. (The $\_ indicates the current value in the foreach loop.) The Mask value (24) is then passed to the MaskBits parameter, and the SiteID value (Redmond) from the file is passed to the NetworkSiteID parameter.

This process continues until all lines in the file have been read, and their values used to create new subnets.

    Import-CSV C:\subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}

## Detailed Description

Each subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet. Use this cmdlet to create a new subnet, and at the same time (optionally) assign it to a network site.

In most deployments of Lync Server where call admission control (CAC) is implemented, there will typically be a large number of subnets. Because of this, it’s often best to call the **New-CsNetworkSubnet** cmdlet in conjunction with the **Import-CSV** cmdlet. By using these cmdlets together, you can read in subnet settings from a comma-separated values (CSV) file and create multiple subnets at once. For more details, see the Examples section for this cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsNetworkSubnet** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkSubnet"}

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
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>The unique subnet ID of the subnet being created. This must be an IP address (such as 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</p></td>
</tr>
<tr class="even">
<td><p><em>MaskBits</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>The bitmask to be applied to the subnet being created.</p>
<p>Valid values: 1 through 32</p></td>
</tr>
<tr class="odd">
<td><p><em>SubnetID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>This is the same value as the Identity. You must specify either an Identity or a SubnetID, but you cannot specify both. Whatever value you supply to one will automatically be applied to the other.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A description of the subnet being created.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkSiteID</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The site ID of the site to which this subnet belongs. You can retrieve site IDs for your deployment by calling the <strong>Get-CsNetworkSite</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType.

## 另请参阅

#### 其他资源

[Remove-CsNetworkSubnet](remove-csnetworksubnet.md)  
[Set-CsNetworkSubnet](set-csnetworksubnet.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)  
[Get-CsNetworkSite](get-csnetworksite.md)

