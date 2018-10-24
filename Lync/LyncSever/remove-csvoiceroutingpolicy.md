---
title: Remove-CsVoiceRoutingPolicy
TOCTitle: Remove-CsVoiceRoutingPolicy
ms:assetid: 3729e908-5c0d-4970-bdff-5869ba2082c9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204799(v=OCS.15)
ms:contentKeyID: 49312496
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsVoiceRoutingPolicy

 

_**上一次修改主题：** 2015-03-09_

Deletes an existing voice routing policy. Voice routing policies manage PSTN usages for users of hybrid voice. Hybrid voice enables users homed on Skype for Business Online to take advantage of the Enterprise Voice capabilities available in an on-premises installation of Lync Server 2013. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsVoiceRoutingPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 deletes the voice routing policy RedmondVoiceRoutingPolicy

    Remove-CsVoiceRoutingPolicy -Identity "RedmondVoiceRoutingPolicy"

## Example 2

In Example 2, all the voice routing policies configured at the per-user scope are removed. To do this, the command first calls the **Get-CsVoiceRoutingPolicy** cmdlet along with the Filter parameter; the filter value "tag:\*" limits the returned data to voice routing policies configured at the per-user scope. Those per-user policies are then piped to, and removed by, the **Remove-CsVoiceRoutingPolicy** cmdlet.

    Get-CsVoiceRoutingPolicy -Filter "tag:*" | Remove-CsVoiceRoutingPolicy

## Example 3

In Example 3, all the voice routing polices that include the PSTN usage "Long Distance" are removed. To carry out this task, the **Get-CsVoiceRoutingPolicy** cmdlet is first called without any parameters in order to return a collection of all the available voice routing policies. That collection is then piped to the Where-Object cmdlet, which picks out only those policies where the PstnUsages property includes (-contains) the usage "Long Distance." Policies that meet that criterion are then piped to the **Remove-CsVoiceRoutingPolicy**, which removes each voice routing policy that includes the PSTN usage "Long Distance".

    Get-CsVoiceRoutingPolicy | Where-Object {$_.PstnUsages -contains "Long Distance"} | Remove-CsVoiceRoutingPolicy

## Detailed Description

Voice routing policies are used in "hybrid" scenarios: when some of your users are homed on the on-premises version of Microsoft Lync Server 2013 and other users are homed on Skype for Business Online. Assigning your Skype for Business Online users a voice routing policy enables those users to receive and to place phones calls to the public switched telephone network by using your on-premises SIP trunks.

Note that simply assigning a user a voice routing policy will not enable them to make PSTN calls via Skype for Business Online. Among other things, you will also need to enable those users for Enterprise Voice and will need to assign them an appropriate voice policy and dial plan.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsVoiceRoutingPolicy"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsVoiceRoutingPolicy** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the voice routing policy to be removed. To &quot;remove&quot; the global policy, use the following syntax:</p>
<p>-Identity global</p>
<p>Note that the global policy cannot actually be removed. Instead, all the properties in that policy will be reset to their default values.</p>
<p>To remove a per-user policy, use syntax similar to this:</p>
<p>-Identity &quot;RedmondVoiceRoutingPolicy&quot;</p>
<p>You cannot use wildcards when specifying a policy Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If this parameter is present, the policy will automatically be removed even if it is currently assigned to at least one user.</p>
<p>If this parameter is not present, then the <strong>Remove-CsVoiceRoutingPolicy</strong> cmdlet will not automatically remove a per-user policy that is assigned to at least one user. Instead, a confirmation prompt will appear asking if you are sure that you want to remove the policy. You must answer yes (by pressing the Y key) before the command will continue and the policy will be removed.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsVoiceRoutingPolicy** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceRoutingPolicy object.

## Return Types

None. Instead, the **Remove-CsVoiceRoutingPolicy** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceRoutingPolicy object.

## 另请参阅

#### 其他资源

[Get-CsVoiceRoutingPolicy](get-csvoiceroutingpolicy.md)  
[Grant-CsVoiceRoutingPolicy](grant-csvoiceroutingpolicy.md)  
[New-CsVoiceRoutingPolicy](new-csvoiceroutingpolicy.md)  
[Set-CsVoiceRoutingPolicy](set-csvoiceroutingpolicy.md)

