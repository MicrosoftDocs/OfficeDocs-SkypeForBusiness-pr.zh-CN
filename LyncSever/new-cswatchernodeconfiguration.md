---
title: New-CsWatcherNodeConfiguration
TOCTitle: New-CsWatcherNodeConfiguration
ms:assetid: c7f78c92-7965-4879-9efa-1b5adcd1881b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205254(v=OCS.15)
ms:contentKeyID: 49314215
ms.date: 04/05/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWatcherNodeConfiguration

 

_**上一次修改主题：** 2017-04-05_

Assigns a new collection of watcher node configuration settings to a pool. Watcher nodes are computers that periodically use Microsoft System Center Operations Manager and Lync Server 2013 synthetic transactions to verify that Lync Server components are working as expected. 此 cmdlet 是在 Lync Server 2013 中引入的。

> [!NOTE]  
> The <strong>New-CsWatcherNodeConfiguration</strong> command should only be executed on the Trusted Application Server you are designating as a Watcher Node.


## 语法

    New-CsWatcherNodeConfiguration -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    New-CsWatcherNodeConfiguration -TargetFqdn <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -PortNumber <UInt16> [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-ExtendedTests <PSListModifier>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Tests <PSListModifier>] [-TestUsers <PSListModifier>] [-UseInternalWebUrls <$true | $false>] [-WhatIf [<SwitchParameter>]] [-XmppTestReceiverMailAddress <String>]

## Examples

## Example 1

The commands shown in Example 1 create a new collection of watcher node configuration settings for the pool atl-cs-001.litwareinc.com. To do this, the first two commands in the example create a pair watcher node test users (sip:kenmyer@litwareinc.com and sip:pilar@litwareinc.com). After the test users have been created, the third command in the example creates a new extended PSTN test using the two newly-created users. This new test (which, at this point in time, exists only in memory) is stored in a variable named $x.

Finally, the fourth command in the example creates the watcher node configuration settings for atl-cs-001.litwareinc.com. These new settings use port 5061; the two new test users; and the extended test stored in the variable $x.

    Set-CsTestUserCredential -SipAddress "sip:kenmyer@litwareinc.com" -UserName "litwareinc\kenmyer" -Password "07Apples"
    
    Set-CsTestUserCredential -SipAddress "sip:pilar@litwareinc.com" -UserName "litwareinc\pilar" -Password "07Apples"
    
    $x = New-CsExtendedTest -TestUsers "sip:kenmyer@litwareinc.com", "sip:pilar@litwareinc.com" -Name "PSTN Test" -TestType "PSTN"
    
    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers "sip:kenmyer@litwareinc.com","sip:pilar@litwareinc.com"} -ExtendedTests @{Add=$x}

## Detailed Description

If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions in order to verify that Lync Server is working as expected. Watcher nodes are assigned to pools, and are managed using the **CsWatcherNodeConfiguration** cmdlets. Note that you do not need to install watcher nodes if you are using System Center Operations Manager. You can still monitor your system without using watcher nodes; the only difference is that any synthetic transactions you want to run will need to be invoked manually rather than automatically invoked by Operations Manager.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsWatcherNodeConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **New-CsWatcherNodeConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name of the pool being associated with the watcher node configuration settings. You can use either the Identity parameter or the TargetFqdn parameter to specify the pool; however, you cannot use both these parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>PortNumber</em></p></td>
<td><p>Required</p></td>
<td><p>System.UInt16</p></td>
<td><p>SIP port used by the Registrar service.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the pool being associated with the watcher node configuration settings. You can use either the TargetFqdn parameter or the Identity parameter to specify the pool; however, you cannot use both these parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Enables or disables the watcher node. The default value is True ($True).</p></td>
</tr>
<tr class="even">
<td><p><em>ExtendedTests</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>PSTN or Audio Conferencing Provider tests that can be assigned to a watcher node configuration. These tests must be created using the <strong>New-CsExtendedTest</strong> cmdlet and stored in a variable (for example, $x). The test can then be assigned to a watcher node by using syntax similar to this:</p>
<p>–ExtendedTests @{Add=$x}</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tests</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Synthetic transactions to be run by the watcher node. Allowed values are:</p>
<p>* Registration</p>
<p>* IM</p>
<p>* GroupIM</p>
<p>* P2PAV</p>
<p>* AvConference</p>
<p>* Presence</p>
<p>* ABS</p>
<p>* ABWQ</p>
<p>* MCXP2PIM</p>
<p>* ExumConnectivity</p>
<p>* JoinLauncher</p>
<p>* PersistentChatMessage</p>
<p>* DataConference</p>
<p>* XmppIM</p>
<p>* UnifiedContactStore</p>
<p>* AVEdgeConnectivity</p>
<p>To configure tests at the time you create a new watcher node, use the following syntax, separating the individual tests by using commas:</p>
<p>-Tests &quot;ABS&quot;,&quot;ABWQ&quot;,&quot;IM&quot;,&quot;GroupIM&quot;,&quot;XmppIM&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>TestUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>SIP addresses of the test users to be assigned to the watcher node; these user accounts must have previously been configured by using the <strong>Set-CsTestUserCredential</strong> cmdlet. To add test users, use syntax similar to this, separating user addresses by using commas:</p>
<p>–TestUsers &quot;sip:kenmyer@litwareinc.com&quot;,&quot;sip:pilar@litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>UseInternalWebUrls</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), instructs the watcher node to use the internal Web URLs rather than the external Web URLs. This provides a way to way to verify URL validity for users located behind the organization's firewall.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>XmppTestReceiverMailAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>XMPP email address to be used when testing the XMPP gateway.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsWatcherNodeConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsWatcherNodeConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

