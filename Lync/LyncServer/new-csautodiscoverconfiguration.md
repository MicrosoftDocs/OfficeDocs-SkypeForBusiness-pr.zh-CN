---
title: New-CsAutodiscoverConfiguration
TOCTitle: New-CsAutodiscoverConfiguration
ms:assetid: 6b878b0e-f0c0-46a2-99b8-fd2105250600
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690022(v=OCS.15)
ms:contentKeyID: 49313163
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAutodiscoverConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of Autodiscover configuration settings at the site scope. The Autodiscover service provides a way for client applications such as Lync Web App or Microsoft Lync Mobile to locate key resources such as a user's home pool or the URL for joining a dial-in conference. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    New-CsAutodiscoverConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-ExternalSipClientAccessFqdn <String>] [-ExternalSipClientAccessPort <UInt32>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WebLinks <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of Autodiscover configuration settings for the Redmond site. Because the WebLinks parameter was not included, these settings will not contain any Autodiscover URLs.

    New-CsAutoDiscoverConfiguration -Identity "site:Redmond"

## EXAMPLE 2

The commands shown in Example 2 create a new collection of Autodiscover configuration settings for the Redmond site and assign those new settings a pair of Autodiscover URLs: http://LyncDiscover.fabrikam.com and http://LyncDiscoverInternal.fabrikam.com. In order to carry out this task, the first two commands use the **New-CsWebLink** cmdlet to create the two Autodiscover URLs; the newly-created URLs are then stored in variables named $Link1 and $Link2. After the two URLs are created, the third command uses the **New-CsAutoDiscoverConfiguration** cmdlet to create the new Autodiscover configuration settings. In order to assign the two URLs to these settings, the WebLinks parameter is included along with the parameter value @{Add=$Link1,$Link2}. That syntax causes the values stored in the variables $Link1 and $Link2 to be added to the WebLinks property.

    $Link1 = New-CsWebLink -Token "Fabrikam" -Href "http://LyncDiscover.fabrikam.com"
    $Link2 = New-CsWebLink -Token "Fabrikam" -Href "http://LyncDiscoverInternal.fabrikam.com"
    
    New-CsAutoDiscoverConfiguration -Identity "site:Redmond" -WebLinks @{Add=$Link1,$Link2}

## Detailed Description

For client applications to make the most effective use of Lync Server those applications need to know the location of key Lync Server components. For example, authenticated users must be able to locate their home pool; after all, they can only be authenticated by that home pool. Likewise, unauthenticated users must be able to do such things as locate the URL used for joining a conference.

If all your users logged on from behind the organization's firewall discovering these locations would be a relatively simple task. However, this relatively simple task gets more and more complicated as users access the system from external locations using Microsoft Lync Mobile or Lync Web App.

This is especially true in split-domain scenarios, scenarios in which some of an organization's users have accounts on the on-premises version of Lync Server while other users have accounts on Skype for Business Online. In cases such as this, user accounts might be located in different Active Directory forests. That can pose a problem: for example, if a US-based user logs on from Europe the system must be able to recognize his or her forest and then refer the logon request to the proper pool.

The Autodiscover service was introduced in the cumulative update for Lync Server: November 2011 in order to address these issues. When a client application attempts to access Lync Server, the Autodiscover service parses the client SIP address and then redirects that request to the appropriate pool. Client applications connect to the Autodiscover service by sending an HTTP request to an Autodiscover URL; these URLs must be configured by administrators in order for the Autodiscover service to work. (Note that, in addition to configuring URLs, administrators must also create DNS records that correspond to these URLs.)

Autodiscover URLs are assigned to Autodiscover configuration settings; in turn, these settings can be applied to the global scope or to the site scope. When you install Lync Server a global collection of settings will be created for you. (However, no Autodiscover URLs will be assigned to that collection.) If a single collection of Autodiscover settings will not fill your needs, then you can use the **New-CsAutoDiscoverConfiguration** cmdlet to create additional configuration settings at the site scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAutoDiscoverConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Unique identifier for the collection of Autodiscover configuration settings to be modified. To create a collection configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalSipClientAccessFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the server used for external client access.</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalSipClientAccessPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Port used for eternal client access.</p></td>
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
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of a command called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling the <strong>Set-CsAutoDiscoverConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebLinks</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of Autodiscover URLs. These URLs must be created by using the <strong>New-CsWebLink</strong> cmdlet.</p></td>
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

The **New-CsAutoDiscoverConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.AutoDiscoverConfiguration.AutoDiscoverConfiguration object.

