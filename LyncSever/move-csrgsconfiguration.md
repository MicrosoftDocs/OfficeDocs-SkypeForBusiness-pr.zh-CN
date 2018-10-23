---
title: Move-CsRgsConfiguration
TOCTitle: Move-CsRgsConfiguration
ms:assetid: 983eadb8-baee-41ba-bba4-2f2b01471250
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398782(v=OCS.15)
ms:contentKeyID: 49313681
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsRgsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Enables you to migrate Response Group configuration settings from Microsoft Office Communications Server 2007 R2 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsRgsConfiguration -Destination <String> -Source <String> [-Force <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 migrates the 响应组应用程序 from atl-ocsrgs-001.litwareinc.com to redmond-lyncrgs-001.litwareinc.com.

    Move-CsRgsConfiguration -Source atl-ocsrgs-001.litwareinc.com -Destination redmond-lyncrgs-001.litwareinc.com 

## Detailed Description

The 响应组应用程序 provides a way for you to automatically route phone calls to entities such as a help desk or customer support line. When someone calls a designated phone number, that call can be automatically routed to the appropriate set of Response Group agents. Alternatively, the call might be routed to an interactive voice response (IVR) queue. In that queue, the caller would be asked a series of questions (for example, "Are you calling about an existing order?") and then, based on the answers to those questions, be given the asked-for information or be routed to a Response Group agent.

If you are currently running the 响应组应用程序 on Office Communications Server 2007 R2 or on Lync Server 2010, the **Move-CsRgsConfiguration** cmdlet provides a way for you to migrate this service to Lync Server 2013. To migrate the service, you need to call the **Move-CsRgsConfiguration** cmdlet and specify: 1) the fully qualified domain name (FQDN) for the existing version of the 响应组应用程序 (the Source); and, 2) the FQDN for the new Lync Server 2013 version of the service (the Destination). **Move-CsRgsConfiguration** will then move all the configuration settings, audio files, and contact objects from the existing version (either Office Communications Server 2007 R2 or Lync Server 2010) to Lync Server 2013. After the service has been migrated, all calls to a Response Group phone number will be handled by Lync Server 2013. Calls will no longer be handled by the previous version of the service.

Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package; this application is installed by running OCSWMIBC.msi. The file OCSWMIBC.msi can be found on the installation DVD in the Setup folder.

If Office Communications Server 2007 is running Microsoft SQL Server 2005 then, before you attempt to migrate the Response Group application, you must install the Microsoft SQL Server 2005 Native Client on the computer where you will be running the **Move-CsRgsConfiguration** cmdlet. If the Native Client is not installed you will receive the error message "Cannot access WMI settings" when you call **Move-CsRgsConfiguration**.

The **Move-CsRgsConfiguration** cmdlet is only for migrating from Office Communications Server 2007 R2 or Lync Server 2010 to Lync Server 2013; you cannot use this cmdlet to migrate from one instance of Lync Server 2013 to a new instance of Lync Server 2013. That type of migration can only be done by using the new **Import-CsRgsConfiguration** and **Export-CsRgsConfiguration** cmdlets.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Move-CsRgsConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsRgsConfiguration"}

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
<td><p><em>Destination</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>FQDN of the computer where the Lync Server 2013 响应组应用程序 is to be hosted (the &quot;copy to&quot; location).</p></td>
</tr>
<tr class="even">
<td><p><em>Source</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>FQDN of the pool where the Office Communications Server 2007 R2 or Lync Server 2010 响应组应用程序 is currently hosted (the &quot;copy from&quot; location).</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **Move-CsRgsConfiguration** does not accept pipelined input.

## Return Types

**Move-CsRgsConfiguration** moves instances of the Microsoft.Rtc.Management.WritableSettings.ServiceSettings from one service to another.

## 另请参阅

#### 其他资源

[Get-CsRgsConfiguration](get-csrgsconfiguration.md)  
[Move-CsRgsConfiguration](move-csrgsconfiguration.md)

