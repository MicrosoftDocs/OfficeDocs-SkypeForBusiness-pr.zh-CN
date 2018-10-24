---
title: New-CsAnalogDevice
TOCTitle: New-CsAnalogDevice
ms:assetid: c02755d6-b651-4385-91a0-5b594dc67751
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412937(v=OCS.15)
ms:contentKeyID: 49314122
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAnalogDevice

 

_**上一次修改主题：** 2015-03-09_

Creates a new analog device that can be managed by using Lync Server. An analog device is a telephone or other device that is connected to the public switched telephone network (PSTN). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAnalogDevice -DN <ADObjectId> <COMMON PARAMETERS>

    New-CsAnalogDevice -OU <OUIdParameter> <COMMON PARAMETERS>

    COMMON PARAMETERS: -AnalogFax <$true | $false> -Gateway <Fqdn> -LineUri <String> -RegistrarPool <Fqdn> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-DisplayNumber <String>] [-PassThru <SwitchParameter>] [-SipAddress <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new analog device with the phone number (LineUri) 1-425-555-6001. (Note that the phone number must be specified using the E.164 format.) In addition to the LineUri parameter, the other parameters used in this command are DisplayName (to set the Active Directory display name of the device); RegistrarPool (to specify the Registrar pool); AnalogFax (set to $False, to indicate that this is a phone and not a fax machine); Gateway (set to the IP address of the gateway); and OU (the distinguished name of the Active Directory OU where the device’s contact object should be created).

    New-CsAnalogDevice -LineUri tel:+14255556001 -DisplayName "Building 14 Receptionist" -RegistrarPool redmond-Cs-001.litwareinc.com -AnalogFax $False -Gateway 192.168.0.240 -OU "ou=Telecommunications,dc=litwareinc,dc=com"

## Detailed Description

Analog devices include telephones, fax machines, modems, and teletype/telecommunication device for the deaf (TTY/TDD) devices that are connected to the public switched telephone network (PSTN). Unlike devices that take advantage of Enterprise Voice (the Voice over Internet Protocol (VoIP) solution offered by Microsoft), analog devices do not transmit information by using digital packets. Instead, information is transmitted by using a continuous signal. This signal is commonly referred to as an analog signal; hence the term "analog devices."

In order to enable administrators to manage analog devices, Lync Server lets you associate analog devices with Active Directory contact objects. After a device has been associated with a contact object, you can then manage the analog device by assigning policies and dial plans to the contact.

New analog devices are created by using the **New-CsAnalogDevice** cmdlet. This cmdlet can either create new contact objects for use with analog devices or it can associate existing contact objects with a new device. For details, see the OU and the DN parameter descriptions in this topic.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAnalogDevice** cmdlet locally: RTCUniversalUserAdmins. Permissions to run this cmdlet for specific sites or specific Active Directory organizational units (OUs) can be assigned by using the **Grant-CsOUPermission** cmdlet. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAnalogDevice"}

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
<td><p><em>AnalogFax</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set to True ($True) if the analog device is a fax machine. Set to False ($False) if the device is not a fax machine.</p></td>
</tr>
<tr class="even">
<td><p><em>DN</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.ADObjectId</p></td>
<td><p>Enables you to associate an existing Active Directory contact object with the analog device. If you have a contact object you want to associate with an analog device, use the DN parameter followed by the distinguished name of that contact. For example: -DN &quot;cn=Building 14 Lobby,dc=litwareinc,dc=com&quot;. Note that the command will fail if the specified contact does not exist.</p>
<p>You cannot use the OU and the DN parameters in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Gateway</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>IP address of the PSTN gateway to be used by the analog device.</p></td>
</tr>
<tr class="even">
<td><p><em>LineUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Phone number for the analog device. The line Uniform Resource Identifier (URI) should be specified by using the E.164 format, and be prefixed by the &quot;TEL:&quot; prefix. For example: TEL:+14255551297. Any extension number should be added to the end of the line URI, for example: &quot;TEL:+14255551297;ext=51297&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>OU</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Distinguished name of the Active Directory organizational unit (OU) where the contact object should be located. For example: -OU &quot;ou=Redmond,dc=litwareinc,dc=com”.</p>
<p>If you include the OU parameter, a new contact will be created in the specified OU, and the contact will automatically be assigned a GUID (globally unique identifier) as its common name. As a result, the contact object will have a name similar to this: {ce84964a-c4da-4622-ad34-c54ff3ed361f}.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPool</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the Registrar pool where the contact object should be homed. For example: -RegistrarPool &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Configures the Active Directory display name of the analog device.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Phone number as displayed in Lync. The DisplayNumber property can be formatted any way you prefer; for example 1-800-555-1234; 1-(800)-555-1234; 1.800.555.1234; etc.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns an object representing the common area phone.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique identifier (similar to an e-mail address) that allows the analog device to communicate with SIP devices such as Lync. The SIP address must be prefaced by the prefix &quot;sip:&quot;. For example: sip:bldg14lobby@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsAnalogDevice** cmdlet does not accept pipelined input.

## Return Types

The **New-CsAnalogDevice** cmdlet creates new instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADAnalogDeviceContact object.

## 另请参阅

#### 其他资源

[Get-CsAnalogDevice](get-csanalogdevice.md)  
[Move-CsAnalogDevice](move-csanalogdevice.md)  
[Remove-CsAnalogDevice](remove-csanalogdevice.md)  
[Set-CsAnalogDevice](set-csanalogdevice.md)

