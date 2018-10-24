---
title: New-CsLocationPolicy
TOCTitle: New-CsLocationPolicy
ms:assetid: 167dead6-e4d4-402c-9ea4-91968eae5610
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398231(v=OCS.15)
ms:contentKeyID: 49312113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsLocationPolicy

 

_**上一次修改主题：** 2015-03-09_

Creates a new location policy for use with location identification for the Enhanced 9-1-1 (E9-1-1) service and general client location. The E9-1-1 service enables those who answer 911 calls to determine the caller’s geographic location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsLocationPolicy -Identity <XdsIdentity> [-ConferenceMode <oneway | twoway>] [-ConferenceUri <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-EmergencyDialMask <String>] [-EmergencyDialString <String>] [-EnhancedEmergencyServiceDisclaimer <String>] [-EnhancedEmergencyServicesEnabled <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LocationRefreshInterval <Int64>] [-LocationRequired <yes | no | disclaimer>] [-NotificationUri <String>] [-PstnUsage <String>] [-UseLocationForE911Only <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 uses the **New-CsLocationPolicy** cmdlet to create a new location policy for the Redmond site that enables all users on that site for E9-1-1. To create this policy, the **New-CsLocationPolicy** cmdlet is called along with two parameters: one to set the Identity, which in this case is the string site: followed by the name of the site to which this policy will apply; the other to set the value of the EnhancedEmergencyServicesEnabled property to True.

    New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True

## EXAMPLE 2

This example creates a per-user location policy. (Per-user policies must be specifically granted to individual users or groups.) This policy has an Identity of Reno. We’ve added a more detailed description of the policy by using the Description parameter. The next parameter we supply is EnhancedEmergencyServicesEnabled, which is set to True to turn on E9-1-1 functionality for all users to which this policy is granted. The next parameter is PstnUsage, in this case with a value of Emergency. This value must match a value in the list of PSTN usages. (This list can be retrieved by calling the **Get-CsPstnUsage** cmdlet.) The usage should be associated with a voice route that will be used for emergency calls. (You can retrieve voice routes by calling the **Get-CsVoiceRoute** cmdlet.) The final parameter used in this example is EmergencyDialString, which specifies the number that is dialed to make an emergency call.

    New-CsLocationPolicy -Identity Reno -Description "All users located at the Reno site" -EnhancedEmergencyServicesEnabled $True -PstnUsage Emergency -EmergencyDialString 911

## Detailed Description

The location policy is used to apply settings that relate to E9-1-1 functionality and location settings to users or contacts. The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call. For example, you can use the location policy to define what number constitutes an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed. This cmdlet creates a new location policy at the site or per-user scope. (A policy at the global scope already exists.)

IMPORTANT: The location policy behaves differently from other policies in Lync Server in terms of order of scope. For all other policies, if a policy is defined at the per-user scope, the policy is applied to any user granted that policy. If the user has not been granted a per-user policy, the site policy is applied. If there is no site policy, the global policy is applied. Location policies are applied in the same way, with one exception: a per-user location policy can also be assigned to a network site. (A network site consists of a group of subnets.) If the user is making the emergency call from a location that is mapped to a network site within the organization, the user-level policy assigned to that network site is used. This functionality will override a per-user policy that has been granted to that user. If the user calls from a location that is unknown or unmapped in the organization, the standard policy scoping will be applied.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsLocationPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsLocationPolicy"}

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
<td><p>A unique identifier for the location policy. This cmdlet can be used to create policies at the site or per-user scope. (A global policy exists by default and cannot be removed.) For a policy created at the site scope, this value must be in the form site:&lt;site name&gt;, where site name is the name of a site defined in the Lync Server deployment. For example, site:Redmond. A policy created at the per-user scope can be assigned any string value, such as Reno.</p></td>
</tr>
<tr class="even">
<td><p><em>ConferenceMode</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Location.ConferenceModeEnum</p></td>
<td><p>If a value is specified for the ConferenceUri parameter, the ConferenceMode parameter determines whether a third party can participate in the call or can only listen in. Available values are:</p>
<p>- oneway: Third party can only listen to the conversation between the caller and the Public Safety Answering Point (PSAP) operator.</p>
<p>- twoway: Third party can listen in and participate in the call between the caller and the PSAP operator.</p></td>
</tr>
<tr class="odd">
<td><p><em>ConferenceUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The SIP Uniform Resource Identifier (URI), in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made. For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value of the ConferenceMode property).</p>
<p>The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</p></td>
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
<td><p>A detailed description of this location. For example, “Reno corporate users”.</p></td>
</tr>
<tr class="even">
<td><p><em>EmergencyDialMask</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A number that is dialed that will be translated into the value of the EmergencyDialString property. For example, if EmergencyDialMask has a value of &quot;212&quot; and EmergencyDialString has a value of &quot;911&quot;, if a user dials 212 the call will be made to 911. This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country/region with a different emergency number attempts to dial that country/region’s number rather than the number for the country/region they’re currently in). You can define multiple emergency dial masks by separating the values with semicolons. For example, -EmergencyDialMask “212;414”.</p>
<p>IMPORTANT. Ensure that the specified dial mask value is not the same as a number in a call park orbit range. Call park routing will take precedence over emergency dial string conversion. To see the existing call park orbit ranges, call the <strong>Get-CsCallParkOrbit</strong> cmdlet.</p>
<p>Maximum length of the string is 100 characters. Each character must be a digit 0 through 9.</p></td>
</tr>
<tr class="odd">
<td><p><em>EmergencyDialString</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The number that is dialed to reach emergency services. In the United States this value is 911.</p>
<p>The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</p></td>
</tr>
<tr class="even">
<td><p><em>EnhancedEmergencyServiceDisclaimer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Text value containing information that will be displayed to users who are connected from locations that cannot be resolved by the location mapping (wiremap) who choose not to enter their location manually. To remove a service disclaimer from a location policy set this property to a null value:</p>
<p>-EnhancedEmergencyServiceDisclaimer $Null</p>
<p>Location policies, and the EnhancedEmergencyServiceDisclaimer property, should be used in Lync Server 2013 to set disclaimers for the E9-1-1 service. This differs from Lync Server 2010, where the Set-CsEnhancedEmergencyServiceDisclaimer cmdlet was used to set a global disclaimer for the entire organization. By using location policies to set these disclaimers, you can create different disclaimers for different locales or different sets of users.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnhancedEmergencyServicesEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether the users associated with this policy are enabled for E9-1-1. Set the value to True to enable E9-1-1 so Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</p>
<p>Default Value: False</p></td>
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
<td><p><em>LocationRefreshInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Specifies the amount of time (in hours) between client requests for Location Information service location update. The LocationRefreshInterval can be set to any value between 1 and 12; the default value is 4.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocationRequired</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationRequiredEnum</p></td>
<td><p>If the client was unable to retrieve a location from the location configuration database, the user can be prompted to manually enter a location. This parameter accepts the following values:</p>
<p>- no: The user will not be prompted for a location. When a call is made with no location information, the Emergency Service Provider will answer the call and ask for a location.</p>
<p>- yes: The user will be prompted to input location information when the client registers at a new location. The user can dismiss the prompt without entering any information. If information is entered, a call made to 911 will first be answered by the Emergency Service Provider to verify the location before being routed to the PSAP operator (the 911 operator).</p>
<p>- disclaimer: This option is the same as yes except that if the user dismisses the prompt disclaimer text will be displayed that can alert the user to the consequences of declining to enter location information. (The disclaimer text must be set by calling the <strong>Set-CsEnhancedEmergencyServiceDisclaimer</strong> cmdlet.)</p>
<p>This value is ignored if EnhancedEmergencyServicesEnabled is set to False (the default). Users will not be prompted for location information.</p></td>
</tr>
<tr class="even">
<td><p><em>NotificationUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>One or more SIP URIs to be notified when an emergency call is made. For example, the company security office could be notified through an instant message whenever an emergency call is made. If the caller’s location is available that location will be included in the notification.</p>
<p>Multiple SIP URIs can be included as a comma-separated list. For example, -NotificationUri sip:security@litwareinc.com,sip:kmyer@litwareinc.com. Note that, with the release of Lync Server 2013, distribution lists can now be configured as a notification URI.</p>
<p>The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnUsage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile. The route associated with this usage should point to a SIP trunk dedicated to emergency calls.</p>
<p>The usage must already exist in the global list of PSTN usages. Call the <strong>Get-CsPstnUsage</strong> cmdlet to retrieve a list of usages. To create a new usage, call the <strong>Set-CsPstnUsage</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>UseLocationForE911Only</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Location information can be used by the Lync client for various reasons (such as notifying teammates of current location). Set this value to True to ensure location information is available only for use with an emergency call.</p></td>
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

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationPolicy.

## 另请参阅

#### 其他资源

[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Set-CsLocationPolicy](set-cslocationpolicy.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Grant-CsLocationPolicy](grant-cslocationpolicy.md)  
[Test-CsLocationPolicy](test-cslocationpolicy.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

