---
title: Remove-CsAutodiscoverConfiguration
TOCTitle: Remove-CsAutodiscoverConfiguration
ms:assetid: f7cda472-c23b-4eb9-b45b-b9353b93e1df
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690054(v=OCS.15)
ms:contentKeyID: 49314782
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsAutodiscoverConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes a collection of Autodiscover configuration settings. The Autodiscover service provides a way for client applications such as Lync Web App to locate key resources such as a user's home pool or the URL for joining a dial-in conference. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Remove-CsAutodiscoverConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the Autodiscover configuration settings for the Redmond site.

    Remove-CsAutoDiscoverConfiguration -Identity "site:Redmond"

## EXAMPLE 2

In Example 2, all the Autodiscover configurations settings assigned to the site scope are removed. To do this, the command first uses the **Get-CsAutoDiscoverConfiguration** cmdlet and the Filter parameter to return a collection of configuration settings; the filter value "site:\*" ensures that only settings that have an Identity that begins with the string value "site:" are returned. That filtered collection is then piped to the **Remove-CsAutoDiscoverConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsAutoDiscoverConfiguration -Filter "site:*" | Remove-CsAutoDiscoverConfiguration

## Detailed Description

For client applications to make the most effective use of Lync Server those applications need to know the location of key Lync Server components. For example, authenticated users must be able to locate their home pool; after all, they can only be authenticated by that home pool. Likewise, unauthenticated users must be able to do such things as locate the URL used for joining a conference.

If all your users logged on from behind the organization's firewall discovering these locations would be a relatively simple task. However, this relatively simple task gets more and more complicated as users access the system from external locations using applications such as Lync Web App.

This is especially true in split-domain scenarios, scenarios in which some of an organization's users have accounts on the on-premises version of Lync Server while other users have accounts on Skype for Business Online. In cases such as this, user accounts might be located in different Active Directory forests. That can pose a problem: for example, if a US-based user logs on from Europe the system must be able to recognize his or her forest and then refer the logon request to the proper pool.

The Autodiscover service was introduced in the cumulative update for Lync Server: November 2011 in order to address these issues. When a client application attempts to access Lync Server, the Autodiscover service parses the client SIP address and then redirects that request to the appropriate pool. Client applications connect to the Autodiscover service by sending an HTTP request to an Autodiscover URL; these URLs must be configured by administrators in order for the Autodiscover service to work. (Note that, in addition to configuring URLs, administrators must also create DNS records that correspond to these URLs.)

Autodiscover URLs are assigned to Autodiscover configuration settings; in turn, these settings can be applied to the global scope or to the site scope. If you later decide to remove settings assigned to the site scope you can do so by running the **Remove-CsAutoDiscoverConfiguration** cmdlet. Note that this cmdlet can also be run against the global settings. In that case, however, the global settings will not be removed; however, any Autodiscover URLs assigned to the global collection will be deleted.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsAutoDiscoverConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Unique identifier for the Autodiscover settings to be removed. Autodiscover settings can be configured at the global or the site scope. To “remove” the global policy, use this syntax: -Identity global. (Note that the global settings cannot actually be removed. Instead, all the properties in the global settings will be reset to their default values.)</p>
<p>To remove settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>Note that wildcards are not allowed when specifying an Identity.</p></td>
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
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

Microsoft.Rtc.Management.WriteableConfig.Settings.AutoDiscoverConfiguration.AutoDiscoverConfiguration. The **Remove-CsAutoDiscoverConfiguration** cmdlet accepts pipelined input of AutoDiscoverConfiguration objects

## Return Types

None. Instead, the cmdlet deletes instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.AutoDiscoverConfiguration.AutoDiscoverConfiguration object.

