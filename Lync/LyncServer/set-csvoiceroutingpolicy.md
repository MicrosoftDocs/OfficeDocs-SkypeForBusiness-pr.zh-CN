---
title: Set-CsVoiceRoutingPolicy
TOCTitle: Set-CsVoiceRoutingPolicy
ms:assetid: cff51726-88c6-4cdf-aaad-a7246c4408c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205313(v=OCS.15)
ms:contentKeyID: 49314306
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceRoutingPolicy

 

_**上一次修改主题：** 2015-05-28_

This cmdlet is for Microsoft internal use only.

Modifies an existing voice routing policy. Voice routing policies manage PSTN usages for users of hybrid voice. Hybrid voice enables users homed on Skype for Business Online to take advantage of the Enterprise Voice capabilities available in an on-premises installation of Lync Server 2013. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsVoiceRoutingPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceRoutingPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-Name <String>] [-PstnUsages <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 adds the PSTN usage "Long Distance" to the per-user voice routing policy RedmondVoiceRoutingPolicy.

    Set-CsVoiceRoutingPolicy -Identity "RedmondVoiceRoutingPolicy" -PstnUsages @{Add="Long Distance"}

## Example 2

In Example 2, the PSTN usage "Local" is removed from the per-user voice routing policy RedmondVoiceRoutingPolicy.

    Set-CsVoiceRoutingPolicy -Identity "RedmondVoiceRoutingPolicy" -PstnUsages @{Remove="Local"}

## Example 3

Example 3 removes the PSTN usage "Local" is removed from all the voice routing policies that include that usage. In order to do this, the command first calls the **Get-CsVoiceRoutingPolicy** cmdlet without any parameters in order to return a collection of all the available voice routing policies. That collection is then piped to the Where-Object cmdlet, which picks out only those policies where the PstnUsages property includes (-contains) the "Local" usage. Those policies are then piped to the **Set-CsVoiceRoutingPolicy** cmdlet, which deletes the Local usage from each policy.

    Get-CsVoiceRoutingPolicy | Where-Object {$_.PstnUsages -contains "Local"} | Set-CsVoiceRoutingPolicy -PstnUsages @{Remove="Local"}

## Detailed Description

Voice routing policies are used in "hybrid" scenarios: when some of your users are homed on the on-premises version of Lync Server and other users are homed on Skype for Business Online. Assigning your Skype for Business Online users a voice routing policy enables those users to receive and to place phones calls to the public switched telephone network by using your on-premises SIP trunks.

Note that simply assigning a user a voice routing policy will not enable them to make PSTN calls via Skype for Business Online. Among other things, you will also need to enable those users for Enterprise Voice and will need to assign them an appropriate voice policy and dial plan.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceRoutingPolicy"}

**Lync Server 控制面板:** The functions carried out by the Set-CsVoiceRoutingPolicy cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide explanatory text to accompany a voice routing policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier assigned to the policy when it was created. Voice routing policies can be assigned at the global scope or the per-user scope. To refer to the global instance, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to a per-user policy, use syntax similar to this:</p>
<p>-Identity &quot;RedmondVoiceRoutingPolicy&quot;</p>
<p>If you do not specify an Identity, then the <strong>Set-CsVoiceRoutingPolicy</strong> cmdlet will modify the global policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A friendly name describing this policy.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnUsages</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of PSTN usages (such as Local or Long Distance) that can be applied to this voice routing policy. The PSTN usage must be an existing usage. (PSTN usages can be retrieved by calling the <strong>Get-CsPstnUsage</strong> cmdlet.)</p></td>
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

The **Set-CsVoiceRoutingPolicy** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceRoutingPolicy object.

## Return Types

None. Instead, the **Set-CsVoiceRoutingPolicy** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.VoiceRoutingPolicy object.

## 另请参阅

#### 其他资源

[Get-CsVoiceRoutingPolicy](get-csvoiceroutingpolicy.md)  
[Grant-CsVoiceRoutingPolicy](grant-csvoiceroutingpolicy.md)  
[New-CsVoiceRoutingPolicy](new-csvoiceroutingpolicy.md)  
[Remove-CsVoiceRoutingPolicy](remove-csvoiceroutingpolicy.md)

