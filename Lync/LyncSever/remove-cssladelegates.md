---
title: Remove-CsSlaDelegates
TOCTitle: Remove-CsSlaDelegates
ms:assetid: 030ca24c-b7b7-4a82-b66a-b6741bbe6f68
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Mt703203(v=OCS.15)
ms:contentKeyID: 72851552
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsSlaDelegates

 

_**上一次修改主题：** 2016-04-12_

Use the **Remove-CsSlaDelegates** cmdlet to remove a delegate from a shared number in Shared Line Appearance (SLA). A shared number in SLA is an Enterprise Voice user that is capable of receiving multiple calls at a time and forwarding them to its delegates, who answer the call.

## 语法

    Remove-CsSlaDelegates -Identity <UserIdParameter> -Delegate <Uri> [-Confirm [<SwitchParameter>]] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The example removes the “delegate\_3@contosohealth.com” delegate from a SLA configuration identified by “emergency”.

    Remove-CsSlaDelegates -Identity emergency -Delegate sip:delegate_3@contosohealth.com

## Detailed Description

SLA is a feature in Skype for Business (SfB) for handling multiple calls on a specific number called a shared number. SLA can configure any enterprise voice enabled SfB user as a shared number with multiple lines to respond to multiple calls. The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number. Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result. Both the number of lines and the delegates are configurable for a shared number in SLA. In addition, advanced options such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call) etc. can also be configured for a shared number.

The **Remove-CsSlaDelegates** cmdlet provides a way remove a delegate from a shared number in Shared Line Appearance (SLA).

> [!NOTE]  
> Logging in with the account created for the SLA number is not supported. Using the SLA number account with any device or Desktop Client can result in unpredictable behavior. It is not necessary to use that account for the Shared Line Appearance feature to function.


By default, members of the RTCUniversalServerAdmins group are authorized to run the **Remove-CsSlaDelegates** cmdlet. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsSlaDelegates"}

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
<td><p><em>Delegate</em></p></td>
<td><p>Required</p></td>
<td><p>System.Uri</p></td>
<td><p>Specifies the delegate to remove from the shared number specified by the <em>Identity</em> parameter. This parameter requires a valid sip address.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the identity of the shared number from which to remove the delegate.</p>
<p>UNRESOLVED_TOKENBLOCK_VAL(PS_PD_User_Updated_Specification)</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>UNRESOLVED_TOKEN_VAL(PS_PD_Passthru_Generic_CurrentObjects)</p></td>
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

The **Remove -CsSlaDelegates** cmdlet accepts a pipelined object representing a user account that has been enabled for Skype for Business Server 2015.

## Return Types

The **Remove -CsSlaDelegates** returns instance of Microsoft.Rtc.Management.SlaConfiguration object.

