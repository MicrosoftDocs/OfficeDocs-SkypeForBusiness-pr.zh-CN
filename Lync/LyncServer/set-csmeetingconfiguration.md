---
title: Set-CsMeetingConfiguration
TOCTitle: Set-CsMeetingConfiguration
ms:assetid: 80c3529e-d009-48c5-835a-3740f02b6dd4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398648(v=OCS.15)
ms:contentKeyID: 49313418
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsMeetingConfiguration

 

_**上一次修改主题：** 2015-03-09_

**Set-CsMeetingConfiguration** enables you to modify the meeting configuration settings currently in use in your organization. Meeting configuration settings help dictate the type of meetings (also called conferences) that users can create, and also control how (or even if) anonymous users and dial-in conferencing users can join these meetings. Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Lync. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsMeetingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsMeetingConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AdmitAnonymousUsersByDefault <$true | $false>] [-AssignedConferenceTypeByDefault <$true | $false>] [-Confirm [<SwitchParameter>]] [-CustomFooterText <String>] [-DesignateAsPresenter <None | Company | Everyone>] [-EnableAssignedConferenceType <$true | $false>] [-Force <SwitchParameter>] [-HelpURL <String>] [-LegalURL <String>] [-LogoURL <String>] [-PstnCallersBypassLobby <$true | $false>] [-RequireRoomSystemsAuthorization <$true | $false>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone.

    Set-CsMeetingConfiguration -Identity site:Redmond -DesignateAsPresenter Everyone

## EXAMPLE 2

The command shown in Example 2 is a variation of the command shown in Example 1. In this case, however, the value of the DesignateAsPresenter property is modified for all the meeting configuration settings in use in the organization. To do this, the **Get-CsMeetingConfiguration** cmdlet is called without any parameters in order to return a collection of all the meeting configuration settings currently in use. This collection is then piped to the **Set-CsMeetingConfiguration** cmdlet, which modifies the DesignateAsPresenter property for each item in the collection.

    Get-CsMeetingConfiguration | Set-CsMeetingConfiguration -DesignateAsPresenter Everyone

## EXAMPLE 3

In Example 3, all the meeting configuration settings that do not allow the default admission of anonymous users are modified. To perform this task, the command first calls the **Get-CsMeetingConfiguration** cmdlet to return a collection of all the meeting configuration settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the AdmitAnonymousUsersByDefault property is equal to False. In turn, this filtered collection is piped to the **Set-CsMeetingConfiguration** cmdlet, which takes each item in the collection and sets the PstnCallersBypassLobby property to True.

    Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $False} | Set-CsMeetingConfiguration -PstnCallersBypassLobby $True

## Detailed Description

Meetings (also called conferences) are an integral part of Lync Server. The CsMeetingConfiguration cmdlets enable administrators to control the type of meetings that users can create and to determine how meetings deal with anonymous users and dial-in conferencing users. For example, you can configure meetings so that anyone dialing in over the public switched telephone network (PSTN) is automatically admitted to the meeting. Alternatively, you can configure meetings so that dial-in users are not automatically admitted the meeting, but are instead routed to the meeting lobby. These dial-in users remain on hold in the lobby until a presenter admits them to the meeting.

As noted previously, these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking Meet Now in Microsoft Lync. When you create a meeting by clicking Meet Now, participant access is automatically open to all everyone, and anonymous users can join the meeting without having to wait in the lobby. This will occur regardless of how you have configured your meeting settings using the CsMeetingConfiguration cmdlets.

The **Set-CsMeetingConfiguration** cmdlet enables you to modify any of the meeting configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsMeetingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsMeetingConfiguration"}

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
<td><p><em>AdmitAnonymousUsersByDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether meetings will, by default, allow attendance by anonymous users (that is, by unauthenticated users). Set this value to True if you would like new meetings to allow for attendance by anonymous users by default. Set this value to False if you would prefer that, by default, new meetings do not allow for attendance by anonymous users. The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>AssignedConferenceTypeByDefault</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether new meetings will be configured, by default, as public meetings. Set this value to True to use public meetings by default; set this value to False to use private meetings by default. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>CustomFooterText</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Text to be used on custom meeting invitations.</p></td>
</tr>
<tr class="odd">
<td><p><em>DesignateAsPresenter</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.DesignateAsPresenter</p></td>
<td><p>Indicates which users (besides the meeting organizer) are automatically designated as presenters when they join a meeting. Valid choices are: None; Company; and Everyone. By default, DesignateAsPresenter is set to Company, meaning everyone in your organization will have presenter rights the moment they join a meeting.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableAssignedConferenceType</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether users are allowed to schedule public meetings. With a public meeting, the conference ID and the meeting link remain consistent each time the meeting is held. With a private meeting, the conference ID and meeting link change from meeting to meeting. The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HelpURL</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL to a website where users can obtain assistance on joining the meeting.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of meeting configuration settings you want to modify. To refer to the global settings, use this syntax: -Identity global. To refer to a collection configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. Settings configured at the service scope can be referenced using syntax like this: -Identity &quot;service:UserServer:atl-cs-001.litwareinc.com&quot;.</p>
<p>If this parameter is not specified, then the <strong>Set-CsMeetingConfiguration</strong> cmdlet will modify the global settings.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>MeetingConfiguration object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
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
<td><p>Indicates whether users dialing in over a public switched telephone network (PSTN) phone line should automatically be admitted to a meeting. If set to True ($True), PSTN callers will automatically be admitted to the meeting. If set to False ($False), then PSTN callers will initially be routed to the conference lobby. At that point, they will have to wait, on hold, until a conference presenter grants them access to the meeting. The default value is True.</p></td>
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
<td><p>Globally unique identifier (GUID) of the Office 365 tenant account whose meeting configuration settings are being modified.</p>
<p>For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.MeetingConfiguration object. The Set-CsMeetingConfiguration cmdlet accepts pipelined instances of the meeting configuration object.

## Return Types

The **Set-CsMeetingConfiguration** cmdlet does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.MeetingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsMeetingConfiguration](get-csmeetingconfiguration.md)  
[New-CsMeetingConfiguration](new-csmeetingconfiguration.md)  
[Remove-CsMeetingConfiguration](remove-csmeetingconfiguration.md)

