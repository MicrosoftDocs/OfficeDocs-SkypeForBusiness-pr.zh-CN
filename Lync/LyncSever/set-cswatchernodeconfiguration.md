---
title: Set-CsWatcherNodeConfiguration
TOCTitle: Set-CsWatcherNodeConfiguration
ms:assetid: 001b49ab-de17-4161-9d0c-9d5d9626558f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204620(v=OCS.15)
ms:contentKeyID: 49311794
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsWatcherNodeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of watcher node configuration settings. Watcher nodes are computers that periodically use Microsoft System Center Operations Manager and Lync Server 2013 synthetic transactions to verify that Lync Server components are working as expected. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsWatcherNodeConfiguration [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsWatcherNodeConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-ExtendedTests <PSListModifier>] [-Force <SwitchParameter>] [-PortNumber <UInt16>] [-Tests <PSListModifier>] [-TestUsers <PSListModifier>] [-UseInternalWebUrls <$true | $false>] [-WhatIf [<SwitchParameter>]] [-XmppTestReceiverMailAddress <String>]

## Examples

## Example 1

The commands shown in Example 1 add a new audio conferencing provider test to the watcher node configuration settings applied to the pool atl-cs-001.litwareinc.com. To do this, the first command in the example uses the **New-CsExtendedTest** cmdlet to create the new test; this in-memory-only test is stored in a variable $x. In the second command, the **Set-CsWatcherNodeConfiguration** cmdlet adds the new test to the watcher node configuration settings; this is done by using the ExtendedTests parameter and the syntax @{Add=$x}.

    $x = New-CsExtendedTest -TestUsers "sip:kenmyer@litwareinc.com", "sip:pilar@litwareinc.com" -Name "Audio Conferencing Test" -TestType "AudioConferencingProvider"
    
    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -ExtendedTests @{Add=$x}

## Example 2

The commands in Example 2 show how you can remove an extended test from a collection of watcher node configuration settings. To carry out this task, the first command in the example uses the **Get-CsWatcherNodeConfiguration** cmdlet to return an object reference to the watcher node settings for the pool atl-cs-001.litwareinc.com; this object reference is stored in a variable named $x.

In the second command, the RemoveAt() method is used to remove the first extended test in the object reference $x. Extended tests are stored as items in an array, with the first item being given the index number 0, the second item being given the index number 1, and so on. The syntax RemoveAt(0) removes the item with the index number 0: the first item in the set of extended tests. To remove the second extended test, use the syntax RemoveAt(1).

After the object reference has been updated, the final command uses the **Set-CsWatcherNodeConfiguration** cmdlet and the Instance parameter to write the changes made to the object reference back to the actual watcher node settings for the pool atl-cs-001.litwareinc.com.

    $x = Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com"
    
    $x.ExtendedTests.RemoveAt(0)
    
    Set-CsWatcherNodeConfiguration -Instance $x

## Example 3

In Example 3, all the extended tests configured for the atl-cs-001.litwareinc.com watcher node are removed. This task is performed by including the ExtendedTests parameter and the parameter value $Null.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -ExtendedTests $Null

## Detailed Description

If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions in order to verify that Lync Server is working as expected. Watcher nodes are assigned to pools, and are managed using the **CsWatcherNodeConfiguration** cmdlets. Note that you do not need to install watcher nodes if you are using System Center Operations Manager. You can still monitor your system without using watcher nodes; the only difference is that any synthetic transactions you want to run will need to be invoked manually rather than automatically invoked by Operations Manager.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsWatcherNodeConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsWatcherNodeConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Enables or disables the watcher node. The default value is True ($True).</p></td>
</tr>
<tr class="odd">
<td><p><em>ExtendedTests</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Object reference to one or more instances of the ExtendedTest object. These objects must be created using the <strong>New-CsExtendedTest</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name of the pool associated with the watcher node configuration settings.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>PortNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>SIP port used by the Registrar service.</p></td>
</tr>
<tr class="even">
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
<p>To enable additional tests for a watcher node use syntax similar to this:</p>
<p>-Tests @{Add=&quot;ExumConnectivity&quot;,&quot;JoinLauncher&quot;,&quot;UnifiedContactStore&quot;}</p>
<p>To disable one or more tests from a watcher node use syntax like this:</p>
<p>-Tests @{Remove=&quot;ABS&quot;,&quot;ABWQ&quot;}</p>
<p>To disable all the tests for a watcher node, set the value of the Tests parameter to $Null:</p>
<p>-Tests $Null</p></td>
</tr>
<tr class="odd">
<td><p><em>TestUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>SIP addresses of the test users employed by the watcher node. To add additional test users to the node use syntax similar to this:</p>
<p>-TestUsers @{Add=&quot;sip:aidan@litwareinc.com&quot;}</p>
<p>To remove a test user from the watcher node user syntax like this:</p>
<p>-TestUsers @{Remove=&quot;sip:aidan@litwareinc.com&quot;</p>
<p>To replace an existing user with a new user, use the Replace method. For example, this syntax replaces the user sip:pilar@litwareinc.com with the new user sip:aidan@litwareinc.com:</p>
<p>-TestUsers @{Replace=&quot;sip:pilar@litwareinc.com&quot;,&quot;sip:aidan@litwareinc.com&quot;}</p>
<p>You must always have at least two test users per watcher node. If you have two users and try to remove one of those users (ostensibly leaving the node with just one test user) your command will fail.</p></td>
</tr>
<tr class="even">
<td><p><em>UseInternalWebUrls</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), instructs the watcher node to use the internal Web URLs rather than the external Web URLs. This provides a way to way to verify URL validity for users located behind the organization's firewall.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>XmppTestReceiverMailAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>XMPP email address to be used when testing the XMPP gateway.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsWatcherNodeConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

## Return Types

None. Instead, the **Set-CsWatcherNodeConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsWatcherNodeConfiguration](get-cswatchernodeconfiguration.md)  
[New-CsWatcherNodeConfiguration](new-cswatchernodeconfiguration.md)  
[Remove-CsWatcherNodeConfiguration](remove-cswatchernodeconfiguration.md)  
[Test-CsWatcherNodeConfiguration](test-cswatchernodeconfiguration.md)

