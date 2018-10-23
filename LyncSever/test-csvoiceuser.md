﻿---
title: Test-CsVoiceUser
TOCTitle: Test-CsVoiceUser
ms:assetid: f29c3b43-d315-4964-ab5c-9fb14612db34
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413013(v=OCS.15)
ms:contentKeyID: 49314714
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsVoiceUser

 

_**上一次修改主题：** 2015-03-09_

Identifies the route that a phone call from a given user would take to be completed based on voice rules, routes, and policies. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsVoiceUser -DialedNumber <PhoneNumber> -SipUri <UserIdParameter> [-Force <SwitchParameter>]

## Examples

## EXAMPLE 1

This example runs a voice user test against the user with the SIP address sip:kmyer@litwareinc.com. The test is performed against the phone number provided by the DialedNumber parameter ("+14255559999"). If no matching rules or routes are identified this cmdlet returns a null value. Notice that we’ve also included the Verbose parameter. Verbose is a common Windows PowerShell parameter that will display additional information as the test is being conducted, such as which dial plan and voice policy are being loaded for the test.

    Test-CsVoiceUser -DialedNumber "+14255559999" -SipUri "sip:kmyer@litwareinc.com" -Verbose

## EXAMPLE 2

This example does a voice routing test for all users enabled for Lync Server or Office Communications Server. The command starts with a call to the **Get-CsUser** cmdlet, which returns a collection of all users enabled for Lync Server or Office Communications Server. This example then pipes the collection of users to the **ForEach-Object** cmdlet. This cmdlet will look at each individual user object and perform the actions we’ve specified within curly braces ({}).

The first action is to output the display name of the current user. (The current user is represented by the $\_ characters; thus the display name is in the DisplayName property of $\_.) We now can see which user account we’re testing. Next we call the **Test-CsVoiceUser** cmdlet, passing it the DialedNumber ("+14255559999") and the SipUri of the current user. In this example we’re using the user’s SIP address ($\_.SipAddress).

Finally, because the output by default is in table format and can get cut off to fit the screen width, we pipe the test results to the **Format-List** cmdlet so we’ll see each user’s display name followed by one line for each output field.

    Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+14255559999" -SipUri $_.SipAddress} | Format-List

## Detailed Description

When a user makes a phone call, the route the call takes to reach its destination depends on the policies and dial plans assigned to that user. Given a user’s SIP address and a phone number, this cmdlet returns the number translated to E.164 format (based on the user’s dial plan), the normalization rule that supplied that translation, the first route (based on route Priority) with a number pattern matching that phone number, and the phone usage that would link the voice policy of that user to the voice route.

This cmdlet can be used to determine whether a specific phone number will route and translate as expect based on user settings, and can help troubleshoot issues experienced by individual users.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsVoiceUser** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsVoiceUser"}

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
<td><p><em>DialedNumber</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
<td><p>The phone number to test.</p>
<p>Full data type: Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
</tr>
<tr class="even">
<td><p><em>SipUri</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>The SIP URI of the user against which the test is taking place. This is the Identity of the user as used in the CsUser cmdlets. You can specify a user's identity using one of four formats: 1) The user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). Note that the SamAccountName cannot be used as an identity.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts or non-fatal error messages that might occur when you run the cmdlet.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns an object of type Microsoft.Rtc.Management.Voice.OcsVoiceUserTestResult.

## 另请参阅

#### 其他资源

[Get-CsUser](get-csuser.md)

