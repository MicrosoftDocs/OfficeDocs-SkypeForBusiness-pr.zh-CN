﻿---
title: Move-CsAnalogDevice
TOCTitle: Move-CsAnalogDevice
ms:assetid: c629c5f8-93e7-4fe4-ad51-52bc0ae99a46
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398816(v=OCS.15)
ms:contentKeyID: 49314207
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsAnalogDevice

 

_**上一次修改主题：** 2015-03-09_

Moves one or more analog devices to a new Registrar pool. An analog device is a telephone or other device that is connected to the public switched telephone network (PSTN). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsAnalogDevice -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-IgnoreBackendStoreException <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 moves the analog device with the Identity CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com to the Registrar pool atl-cs-001.litwareinc.com.

    Move-CsAnalogDevice -Identity "CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com" -Target atl-cs-001.litwareinc.com

## EXAMPLE 2

In Example 2, the analog device that has the Active Directory display name, "Building 14, Room 142", is moved to the Registrar pool atl-cs-001.litwareinc.com. To do this, the **Get-CsAnalogDevice** cmdlet is first called without any parameters in order to return a collection of all the analog devices currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out all the devices that have the display name "Building 14, Room 142". That filtered collection is then piped to the **Move-CsAnalogDevice** cmdlet, which moves all of the devices in the collection to the Registrar pool atl-cs-001.litwareinc.com.

    Get-CsAnalogDevice | Where-Object {$_.DisplayName -eq "Building 14, Room 142"} | Move-CsAnalogDevice -Target atl-cs-001.litwareinc.com

## EXAMPLE 3

The command shown in Example 3 moves all of the analog devices that have a display name that begins with the string value "Building 14". To carry out this task, the command first calls the **Get-CsAnalogDevice** cmdlet to return a collection of all the analog devices currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects all the devices that have a display name that begins with the string value "Building 14". The filtered collection is then piped to the **Move-CsAnalogDevice** cmdlet, which moves each device in the collection to the Registrar pool atl-cs-001.litwareinc.com.

    Get-CsAnalogDevice | Where-Object {$_.DisplayName -like "Building 14*"} | Move-CsAnalogDevice -Target atl-cs-001.litwareinc.com

## Detailed Description

Analog devices include telephones, fax machines, modems, and teletype/telecommunication device for the deaf (TTY/TDD) devices that are connected to the public switched telephone network (PSTN). Unlike devices that take advantage of Enterprise Voice (the Voice over Internet Protocol (VoIP) solution offered by Microsoft), analog devices do not transmit information by using digital packets. Instead, information is transmitted by using a continuous signal. This signal is commonly referred to as an analog signal; hence the term "analog devices."

In order to enable administrators to manage analog devices, Lync Server lets you associate analog devices with Active Directory contact objects. After a device has been associated with a contact object, you can then manage the analog device by assigning policies and dial plans to the contact.

The **Move-CsAnalogDevice** cmdlet provides a way for you to move an existing analog device to a new Registrar pool.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Move-CsAnalogDevice** cmdlet locally: RTCUniversalUserAdmins. Permissions to run this cmdlet for specific sites or specific Active Directory organizational units (OUs) can be assigned by using the **Grant-CsOUPermission** cmdlet. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsAnalogDevice"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Unique identifier for the analog device. Analog devices are identified by using the Active Directory distinguished name of the associated contact object. By default, analog devices use a GUID (globally unique identifier) as their common name, which means devices will typically have an Identity similar to this: CN={ce84964a-c4da-4622-ad34-c54ff3ed361f},OU=Redmond,DC=Litwareinc,DC=com.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The fully qualified domain name (FQDN) (for example, atl-cs-001.litwareinc.com) of the Registrar pool where the analog device should be moved. In addition to a Registrar pool, the Target can also be the FQDN of a hosting provider.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to move the analog device. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its FQDN (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, moves the analog device but deletes any associated data (such as policies that were assigned to the device). If not present, the device is moved along with any associated data.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, instructs the computer to ignore any errors that might occur with the backend database and attempt to move the common area phone despite those errors.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being moved. By default, the <strong>Move-CsAnalogDevice</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is used only for Microsoft Lync Online 2010. It should not be used with an on-premises implementation of Lync Server.</p></td>
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

String. The **Move-CsAnalogDevice** cmdlet accepts a pipelined string value that represents the Identity of the analog device.

## Return Types

By default, the **Move-CsAnalogDevice** cmdlet does not return any objects or values. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact object.

## 另请参阅

#### 其他资源

[Get-CsAnalogDevice](get-csanalogdevice.md)  
[New-CsAnalogDevice](new-csanalogdevice.md)  
[Remove-CsAnalogDevice](remove-csanalogdevice.md)  
[Set-CsAnalogDevice](set-csanalogdevice.md)

