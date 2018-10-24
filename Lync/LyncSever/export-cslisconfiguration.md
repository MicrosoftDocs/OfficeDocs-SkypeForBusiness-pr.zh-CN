---
title: Export-CsLisConfiguration
TOCTitle: Export-CsLisConfiguration
ms:assetid: 714bd67e-4cd6-4066-a065-59f7e079b6ad
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398539(v=OCS.15)
ms:contentKeyID: 49313213
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsLisConfiguration

 

_**上一次修改主题：** 2015-03-09_

Exports an Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration to a file in compressed format for backup purposes. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Export-CsLisConfiguration -FileName <String> <COMMON PARAMETERS>

    Export-CsLisConfiguration [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>

    COMMON PARAMETERS:

## Examples

## EXAMPLE 1

This example exports the entire E9-1-1 configuration from the Location Information Server (LIS) to the backup file named E911Config.bak.

    Export-CsLisConfiguration -FileName C:\E911Config.bak

## EXAMPLE 2

In this example, the LIS configuration is stored as an array of bytes in a variable, $lisconfig.

    $lisconfig = Export-CsLisConfiguration -AsBytes

## EXAMPLE 3

Example 3 is a more complete version of Example 2. The first line is the same, we call the **Export-CsLisConfiguration** cmdlet with the AsBytes parameter to store the LIS configuration as an array of bytes in the variable $lisconfig. The rest of this example shows how to save that configuration to a file and then import it back into the location configuration database.

In line 2 we pipe the contents of $lisconfig, which is the byte array representing the LIS configuration, to the Windows PowerShell **Set-Content** cmdlet. We assign values to two parameters of the **Set-Content** cmdet: Path and Encoding. We assign the full path and file name of the file to which we want to save the configuration to the Path parameter. We use the Encoding parameter with a value of byte to ensure the configuration is stored as an array of bytes.

Finally, in line 3 we import the configuration back into the location configuration database. First we call the **Get-Content** cmdlet to retrieve the contents from the file. We pass a value of 0 to the ReadCount property, which tells the **Get-Content** cmdlet to read all the contents of the file at once rather than one line at a time. We again use the Encoding parameter with a value of byte to specify what type of data we’re reading from the file. Finally we pass the file name to the Path parameter. The contents of the file that we read with the **Get-Content** cmdlet are piped to the **Import-CsLisConfiguration** cmdlet, which imports the saved configuration into the location database.

    $lisconfig = Export-CsLisConfiguration -AsBytes
    $lisconfig | Set-Content -Path C:\E911Config.bak -Encoding byte
    Get-Content -ReadCount 0 -Encoding byte -Path C:\E911Config.bak  | Import-CsLisConfiguration

## Detailed Description

Implementing E9-1-1 in an organization can, depending on the size of the organization, involve mapping thousands of subnets, ports, switches, and wireless access points (WAPs) to locations. An E9-1-1 configuration also includes information about web services provided by the E9-1-1 Network Routing Provider, and about locations and civic addresses and whether or not they’ve been validated. Given the volume of information and settings required to implement E9-1-1, it’s recommended that you regularly back up the entire configuration. You can use this cmdlet to back up the E9-1-1 configuration to a file, which will save the entire configuration in compressed format. To recover the configuration, call the **Import-CsLisConfiguration** cmdlet.

This cmdlet creates a new backup file; it will not overwrite an existing file. That means the file name that is specified in the call to this cmdlet cannot be the name of an existing file.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsLisConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsLisConfiguration"}

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
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The path and file name of the file to which you want to save the configuration. This cannot be the name of an existing file.</p>
<p>If you supply a value to the AsBytes parameter, you cannot supply a value to the FileName parameter. If you’re accessing this cmdlet remotely, you must use AsBytes rather than FileName.</p></td>
</tr>
<tr class="even">
<td><p><em>AsBytes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns the configuration as a byte array. The output of the command should be assigned to a variable for later import. (If you don’t assign the output to a variable, the byte array representing the configuration will scroll down your Lync Server 命令行管理程序 window.) You cannot specify both the AsBytes parameter and the FileName parameter; you can use only one or the other for each call to this cmdlet.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns a byte array (Byte\[\]) when the AsBytes parameter is used.

## 另请参阅

#### 其他资源

[Import-CsLisConfiguration](import-cslisconfiguration.md)  
[Debug-CsLisConfiguration](debug-cslisconfiguration.md)  
[Publish-CsLisConfiguration](publish-cslisconfiguration.md)  
[Unpublish-CsLisConfiguration](unpublish-cslisconfiguration.md)  
[Test-CsLisConfiguration](test-cslisconfiguration.md)

