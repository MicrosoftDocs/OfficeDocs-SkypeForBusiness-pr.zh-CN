---
title: New-CsMeetingConfiguration
TOCTitle: New-CsMeetingConfiguration
ms:assetid: 0043c9e7-83c6-4f07-88d2-7018c65c1654
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398065(v=OCS.15)
ms:contentKeyID: 49311796
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsMeetingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of meeting configuration settings at the site or service scope. Meeting configuration settings help dictate the type of meetings (also called “conferences”) that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings. Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Lync. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsMeetingConfiguration -Identity <XdsIdentity> [-AdmitAnonymousUsersByDefault <$true | $false>] [-AssignedConferenceTypeByDefault <$true | $false>] [-Confirm [<SwitchParameter>]] [-CustomFooterText <String>] [-DesignateAsPresenter <None | Company | Everyone>] [-EnableAssignedConferenceType <$true | $false>] [-Force <SwitchParameter>] [-HelpURL <String>] [-InMemory <SwitchParameter>] [-LegalURL <String>] [-LogoURL <String>] [-PstnCallersBypassLobby <$true | $false>] [-RequireRoomSystemsAuthorization <$true | $false>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new collection of meeting configuration settings for the Redmond site (-Identity site:Redmond). In addition to specifying the Identity, three optional parameters are included in this command: EnableAssignedConferenceType, AssignedConferenceTypeByDefault, and AdmitAnonymousUsersByDefault. In all three cases, these parameters are set to False. That means that public meeting types will be disabled; the default meeting type will not be set to public meeting; and anonymous users will not be admitted to meetings by default.

Note that this command will fail if a collection of meeting configuration settings with the Identity site:Redmond already exists. That’s because only one collection of meeting configuration settings can be applied to a given site.

    New-CsMeetingConfiguration -Identity site:Redmond -EnableAssignedConferenceType $False -AssignedConferenceTypeByDefault $False -AdmitAnonymousUsersByDefault $False

## EXAMPLE 2

Example 2 shows an alternate way to create a new collection of meeting configuration settings for the Redmond site; in this case, the settings are initially created in memory only, and are only later applied to the site. To do this, the first command in the example uses the **New-CsMeetingConfiguration** cmdlet to create new meeting settings for the Redmond site. The InMemory parameter is added to the end of the command to ensure that these new settings are created in memory only, and are not immediately applied to the Redmond site. (Because these settings exist only in memory, they must be stored in a variable. In this example, they are stored in a variable named $x.)

After these virtual meeting settings have been created, commands 2, 3, and 4 are used to modify properties of those settings (EnableAssignedConferenceType, AssignedConferenceTypeByDefault, and AdmitAnonymousUsersByDefault). In the final command, the **Set-CsMeetingConfiguration** cmdlet and the Instance parameter are used to actually apply the virtual settings to the Redmond site. Note that this final step is crucial: if you do not call the **Set-CsMeetingConfiguration** cmdlet, the new meeting configuration settings will never be applied to the Redmond site. Instead, your virtual settings will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsMeetingConfiguration -Identity site:Redmond -InMemory
    $x.EnableAssignedConferenceType = $False 
    $x.AssignedConferenceTypeByDefault = $False 
    $x.AdmitAnonymousUsersByDefault = $False
    Set-CsMeetingConfiguration -Instance $x

## Detailed Description

Meetings (also called “conferences”) are an integral part of Lync Server. The **CsMeetingConfiguration** cmdlets enable administrators to control the type of meetings that users can create and to determine how meetings deal with anonymous users and dial-in conferencing users. For example, you can configure meetings so that anyone dialing in over the public switched telephone network (PSTN) is automatically admitted to the meeting. Alternatively, you can configure meetings so that dial-in users are not automatically admitted the meeting, but are instead routed to the meeting lobby. These dial-in users remain on hold in the lobby until a presenter admits them to the meeting.

As noted previously, these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking Meet Now in Microsoft Lync. When you create a meeting by clicking Meet Now, participant access is automatically open to all everyone, and anonymous users can join the meeting without having to wait in the lobby. This will occur regardless of how you have configured your meeting settings using the CsMeetingConfiguration cmdlets.

The **New-CsMeetingConfiguration** cmdlet enables you to create new meeting configuration collections at either the site or the service scope (albeit only for the User Services). Meeting settings cannot be created at the global scope because there is already a global collection of meeting settings.

Note that each site or service can only have, at most, one collection of meeting configuration settings. If you try to create new settings for the Redmond site, and the Redmond site already has a collection of meeting configuration settings, then your command will fail.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsMeetingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsMeetingConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the new collection of meeting configuration settings. Meeting configuration settings can only be created at the site or service scope. To create new settings at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To create new settings at the service scope, use syntax like this: -Identity &quot;service:UserServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that the call to the <strong>New-CsMeetingConfiguration</strong> cmdlet will fail if the specified site or service already has a collection of meeting configuration settings.</p></td>
</tr>
<tr class="even">
<td><p><em>AdmitAnonymousUsersByDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether meetings will, by default, allow attendance by anonymous users (that is, unauthenticated users). Set this value to True if you would like new meetings to allow for attendance by anonymous users by default. Set this value to False if you would prefer that, by default, new meetings do not allow for attendance by anonymous users. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>AssignedConferenceTypeByDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether new meetings will be configured, by default, as public meetings. Set this value to True to use public meetings by default; set this value to False to use private meetings by default. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>CustomFooterText</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Text to be used on custom meeting invitations.</p></td>
</tr>
<tr class="even">
<td><p><em>DesignateAsPresenter</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.DesignateAsPresenter</p></td>
<td><p>Indicates which users (besides the meeting organizer) are automatically designated as presenters when they join a meeting. Valid choices are: None; Company; and Everyone. By default, DesignateAsPresenter is set to Company, meaning everyone in your organization has presenter rights the moment they join a meeting.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableAssignedConferenceType</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users are allowed to schedule public meetings. With a public meeting, the conference ID and the meeting link remain consistent each time the meeting is held. With a private meeting, the conference ID and meeting link change from meeting to meeting.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>HelpURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL to a website where users can obtain assistance on joining the meeting.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>LegalURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL to a website containing legal information and meeting disclaimers.</p></td>
</tr>
<tr class="even">
<td><p><em>LogoURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the image to be used on custom meeting invitations.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnCallersBypassLobby</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users dialing in over a public switched telephone network (PSTN) phone line should automatically be admitted to a meeting. If set to True PSTN callers will automatically be admitted to the meeting. If set to False PSTN callers will initially be routed to the conference lobby. At that point, they will be put on hold until a conference presenter grants them access to the meeting. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>RequireRoomSystemsAuthorization</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True) all users must be authenticated before they can join a meeting using the Lync Room System. The default value is False ($False).</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new meeting configuration settings are being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

None. The **New-CsMeetingConfiguration** cmdlet does not accept pipelined data.

## Return Types

The **New-CsMeetingConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.MeetingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsMeetingConfiguration](get-csmeetingconfiguration.md)  
[Remove-CsMeetingConfiguration](remove-csmeetingconfiguration.md)  
[Set-CsMeetingConfiguration](set-csmeetingconfiguration.md)

