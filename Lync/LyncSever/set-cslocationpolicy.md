---
title: Set-CsLocationPolicy
TOCTitle: Set-CsLocationPolicy
ms:assetid: efa2840c-2e21-408e-b9fe-6f9998c81db2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412987(v=OCS.15)
ms:contentKeyID: 49314685
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsLocationPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing location policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsLocationPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsLocationPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-ConferenceMode <oneway | twoway>] [-ConferenceUri <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-EmergencyDialMask <String>] [-EmergencyDialString <String>] [-EnhancedEmergencyServiceDisclaimer <String>] [-EnhancedEmergencyServicesEnabled <$true | $false>] [-Force <SwitchParameter>] [-LocationRefreshInterval <Int64>] [-LocationRequired <yes | no | disclaimer>] [-NotificationUri <String>] [-PstnUsage <String>] [-UseLocationForE911Only <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command uses the **Set-CsLocationPolicy** cmdlet to modify the location policy with the Identity site:Redmond. (In other words, it modifies the location policy applied to the Redmond site.) In this case, the command sets the value of the EnhancedEmergencyServicesEnabled property to True, which will enable E9-1-1 functionality for all users connected to (in this case) the Redmond site.

    Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True

## EXAMPLE 2

Example 2 modifies all the location policies in use in the organization that have defined a conferencing URI to have a conferencing mode of two-way. To carry out this task, the command first uses the **Get-CsLocationPolicy** cmdlet to return a collection of all the location policies currently defined. This collection is then piped to the **Where-Object** cmdlet to narrow the collection down to only those location policies that have a ConferenceUri property that is not empty (not equal to Null). This results in a collection of location policies that have ConferenceUri values. This collection is then piped to the **Set-CsLocationPolicy** cmdlet, which then modifies the value of the ConferenceMode property for each policy in the collection by setting the value to twoway.

    Get-CsLocationPolicy | Where-Object {$_.ConferenceUri -ne $null} | Set-CsLocationPolicy -ConferenceMode twoway

## Detailed Description

The location policy is used to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and client location. The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call. For example, you can use the location policy to define what number constitutes an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed. This cmdlet modifies an existing location policy.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsLocationPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsLocationPolicy"}

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
<td><p><em>ConferenceMode</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Policy.Location.ConferenceModeEnum</p></td>
<td><p>If a value is specified for the ConferenceUri parameter, the ConferenceMode parameter determines whether a third party can participate in the call or can only listen in. Available values are:</p>
<p>- oneway: Third party can only listen to the conversation between the caller and the Public Safety Answering Point (PSAP) operator.</p>
<p>- twoway: Third party can listen in and participate in the call between the caller and the PSAP operator.</p></td>
</tr>
<tr class="even">
<td><p><em>ConferenceUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The SIP Uniform Resource Identifier (URI), in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made. For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value of the ConferenceMode property).</p>
<p>The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A detailed description of this location. For example, “Building 30, 3rd Floor, Northeast corner”.</p></td>
</tr>
<tr class="odd">
<td><p><em>EmergencyDialMask</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A number that is dialed that will be translated into the value of the EmergencyDialString property. For example, if EmergencyDialMask has a value of &quot;212&quot; and EmergencyDialString has a value of &quot;911&quot;, if a user dials 212 the call will be made to 911. This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country/region with a different emergency number attempts to dial that country/region’s number rather than the number for the country/region they’re currently in). You can define multiple emergency dial masks by separating the values with semicolons. For example, -EmergencyDialMask “212;414”.</p>
<p>IMPORTANT. Ensure that the specified dial mask value is not the same as a number in a call park orbit range. Call park routing will take precedence over emergency dial string conversion. To see the existing call park orbit ranges, call the <strong>Get-CsCallParkOrbit</strong> cmdlet.</p>
<p>Maximum length of the string is 100 characters. Each character must be a digit 0 through 9.</p></td>
</tr>
<tr class="even">
<td><p><em>EmergencyDialString</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The number that is dialed to reach emergency services. In the United States this value is “911”.</p>
<p>The string must be made of the digits 0 through 9 and can be from 1 to 10 characters in length.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnhancedEmergencyServiceDisclaimer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Text value containing information that will be displayed to users who are connected from locations that cannot be resolved by the location mapping (wiremap) who choose not to enter their location manually. To remove a service disclaimer from a location policy set this property to a null value:</p>
<p>-EnhancedEmergencyServiceDisclaimer $Null</p>
<p>Location policies, and the EnhancedEmergencyServiceDisclaimer property, should be used in Lync Server 2013 to set disclaimers for the E9-1-1 service. This differs from Lync Server 2010, where the Set-CsEnhancedEmergencyServiceDisclaimer cmdlet was used to set a global disclaimer for the entire organization. By using location policies to set these disclaimers, you can create different disclaimers for different locales or different sets of users.</p></td>
</tr>
<tr class="even">
<td><p><em>EnhancedEmergencyServicesEnabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether the users associated with this policy are enabled for E9-1-1. Set the value to True to enable E9-1-1, so Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the location policy you want to modify. To modify the global location policy, use a value of Global. For a policy created at the site scope, this value will be in the form site:&lt;site name&gt;, where site name is the name of a site defined in the Lync Server deployment (for example, site:Redmond). For a policy created at the per-user scope, this value will simply be the name of the policy, such as Reno.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>LocationPolicy</p></td>
<td><p>A reference to a location policy object. This object must be of type Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationPolicy, which can be retrieved by calling the <strong>Get-CsLocationPolicy</strong> cmdlet. Retrieve this object, change the properties in memory, and then pass the object reference as a value to this parameter to update that location policy.</p></td>
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
<p>- yes: The user will be prompted to input location information when the client registers at a new location. The user can dismiss the prompt without entering any information. If information is entered, a call made to 911 will first be answered by the Emergency Service Provider to verify the location before being routed to the PSAP (that is, the 911 operator).</p>
<p>- disclaimer: This option is the same as yes except that if the user dismisses the prompt disclaimer text will be displayed that can alert the user to the consequences of declining to enter location information. (The disclaimer text must be set by calling the <strong>Set-CsEnhancedEmergencyServiceDisclaimer</strong> cmdlet.)</p>
<p>This value is ignored if EnhancedEmergencyServicesEnabled is set to False (the default). Users will not be prompted for location information.</p></td>
</tr>
<tr class="even">
<td><p><em>NotificationUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made. For example, the company security office could be notified through an instant message whenever an emergency call is made. If the caller’s location is available that location will be included in the notification.</p>
<p>Multiple SIP URIs can be included as a comma-separated list. For example, -NotificationUri sip:security@litwareinc.com,sip:kmyer@litwareinc.com. Note that, with the release of Lync Server 2013, distribution lists can now be configured as a notification URI.</p>
<p>The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnUsage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route 911 calls from clients using this profile. The route associated with this usage should point to a SIP trunk dedicated to emergency calls.</p>
<p>The usage must already exist in the global list of PSTN usages. Call the <strong>Get-CsPstnUsage</strong> cmdlet to retrieve a list of usages. To create a new usage, call the <strong>Set-CsPstnUsage</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>UseLocationForE911Only</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Location information can be used by the Lync Server client for various reasons (such as notifying teammates of current location). Set this value to True to ensure location information is available only for use with an emergency call.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationPolicy object. Accepts pipelined input of location policy objects.

## Return Types

This cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationPolicy object.

## 另请参阅

#### 其他资源

[New-CsLocationPolicy](new-cslocationpolicy.md)  
[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Grant-CsLocationPolicy](grant-cslocationpolicy.md)  
[Test-CsLocationPolicy](test-cslocationpolicy.md)  
[Get-CsPstnUsage](get-cspstnusage.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

