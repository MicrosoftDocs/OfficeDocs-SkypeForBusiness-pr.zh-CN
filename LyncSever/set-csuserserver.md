---
title: Set-CsUserServer
TOCTitle: Set-CsUserServer
ms:assetid: f4dd845a-5c78-4455-93eb-722b603ff154
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413026(v=OCS.15)
ms:contentKeyID: 49314751
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUserServer

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify an existing User Services pool. Among other things, the User Services pool provides presence information and helps to manage conferences. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUserServer [-Identity <XdsGlobalRelativeIdentity>] [-ConfDirManagementWcfTcpPort <UInt16>] [-ConferenceServer <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-McuFactorySipPort <UInt16>] [-UserDatabase <String>] [-UserPinManagementWcfHttpPort <UInt16>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 changes the McuFactorySipPort for a single User Services pool: the pool with the Identity UserServer:atl-cs-001.litwareinc.com. In this example, the port is changed to 445.

    Set-CsUserServer -Identity "UserServer:atl-cs-001.litwareinc.com" -McuFactorySipPort 445

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1. In this case, however, the McuFactorySipPort is modified for all the User Services pools in the organization. To do this, the command starts off by using the **Get-CsService** cmdlet and the UserServer parameter to return a collection of all the User Services pool currently in use. This collection is then piped to the **ForEach-Object** cmdlet, which takes each pool in the collection and sets the McuFactorySipPort to 445. The data must be piped to the **ForEach-Object** cmdlet because the **Set-CsUserServer** cmdlet cannot accept pipelined data itself.

    Get-CsService -UserServer | ForEach-Object {Set-CsUserServer -Identity $_.Identity -McuFactorySipPort 445}

## Detailed Description

User Services is a catch-all component that performs a number of key Lync Server roles; for example, User Services provides presence information; helps to manage conferences (through the Focus and Focus Factory); handles user authorization and user-level routing; and serves as the primary interface to the back-end database. User Services also assists with provisioning user accounts.

Because of this, it is important for administrators to know exactly how their User Services pools have been configured and, if necessary, to modify those configurations. You can retrieve information about your User Services pools by using this command:

Get-CsService -UserServer

Likewise, you can use the **Set-CsUserServer** cmdlet to make changes to any of these pools. The **Set-CsUserServer** cmdlet enables administrators to change the user database and/or the conferencing server associated with a pool. The cmdlet also lets you modify the port used for connections to the Focus Factory.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUserServer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUserServer"}

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
<td><p><em>ConfDirManagementWcfTcpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Windows Communication Foundation (WCF) port used for managing conference directories. The default value is 9001.</p></td>
</tr>
<tr class="even">
<td><p><em>ConferenceServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service ID for the conferencing server associated with the User Services pool. For example: -ConferenceServer &quot;ConferenceServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the User Services pool to be modified. For example: -Identity &quot;UserServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that you can leave off the prefix &quot;UserServer:&quot; when specifying a User server. For example: -Identity &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>McuFactorySipPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used for connecting to the Focus Factory (McuFactory). The Focus Factory allocates media control units (MCUs) in order to add specific media types such as audio to conferences.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service ID for the user database associated with the User Services pool. For example: -UserDatabase &quot;UserDatabase:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>UserPinManagementWcfHttpPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Port used by Windows Communication Foundation (WCF) when managed user PINs. The default value is 443.</p></td>
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

None. The **Set-CsUserServer** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsUserServer** cmdlet does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.Xds.DisplayUserServer object.

## 另请参阅

#### 其他资源

[Get-CsService](get-csservice.md)

