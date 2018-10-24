---
title: Set-CsSite
TOCTitle: Set-CsSite
ms:assetid: f4165fdb-5828-4e81-b489-7e263b27e36b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413023(v=OCS.15)
ms:contentKeyID: 49314732
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsSite

 

_**上一次修改主题：** 2015-03-09_

Modifies the properties for any of your Lync Server sites. Sites represent a collection of Lync Server pools and are typically designed around geographic regions. Lync Server includes two types of sites: data center sites and remote sites (branch office). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsSite [-Identity <XdsGlobalRelativeIdentity>] [-Confirm [<SwitchParameter>]] [-DefaultPersistentChatPool <String>] [-Description <String>] [-DisplayName <String>] [-FederationRoute <String>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]] [-XmppFederationRoute <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the Description property for the Redmond site (-Identity Redmond).

    Set-CsSite -Identity Redmond -Description "Full-time employees in Redmond, WA."

## EXAMPLE 2

Example 2 changes the display name for the Redmond site to "US Headquarters".

    Set-CsSite -Identity Redmond -DisplayName "US Headquarters"

## EXAMPLE 3

The command shown in Example 3 locates all the sites that do not have a Description, and then assigns each of those sites the generic description "Litwareinc.com." To do this, the command first calls the **Get-CsSite** cmdlet without any parameters in order to return a collection of all the Lync Server sites. The returned collection is then piped to the **Where-Object** cmdlet, which picks out only those sites where the Description property is equal to (-eq) a null value ($Null). These sites are then piped to the **ForEach-Object** cmdlet. This cmdlet takes each item in the collection and uses the **Set-CsSite** cmdlet to modify the value of the Description property.

    Get-CsSite | Where-Object {$_.Description -eq $Null} | ForEach-Object {Set-CsSite $_.Identity -Description "Litwareinc.com"}

## Detailed Description

Lync Server 2010 introduced a new concept to the Lync Server topology: sites. Sites (which should not be confused with Active Directory sites or Microsoft Exchange Server sites) are a collection of Lync Server pools and servers that are typically organized according to geography and network bandwidth. For example, if all your computers in Redmond are located on the same local area network with high-speed, low-latency connections, you might designate a Redmond site that encompasses those computers. If your computers in Dublin are located on their own local area network, and share high-speed, low-latency connections, then you might create a separate Dublin site as well. Sites also play a key role in Lync Server management: many policies and settings can be configured at the site scope, making it easy to do such things as apply one set of dial plans to users in Redmond and a different set of dial plans to users in Dublin.

Sites are created by using 拓扑生成器, and any changes to the site infrastructure (for example, adding new pools) must also be made by using Topology Builder. However, you can use the **Set-CsSite** cmdlet to change the display name, the description, and the federation route of any site in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsSite** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsSite"}

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
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultPersistentChatPool</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the default Persistent Chat pool for the site.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to add additional information to a site object. For example, the Description might include contact information for the site.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Friendly name for the site. For example: -DisplayName &quot;North America and South America&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>FederationRoute</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service location of the 边缘服务器 used to provide a bridge between your internal network and the Internet. For example: -FederationRoute &quot;EdgeServer:atl-edge-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts or non-fatal error messages that might occur when you run the cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Name of the site to be modified; for example: -Identity &quot;Redmond&quot;. Do not use the format &quot;site:Redmond&quot; when specifying the identity.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
<tr class="odd">
<td><p><em>XmppFederationRoute</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the Edge Server used for XMPP (Extensible Messaging and Presence Protocol) federation. For example:</p>
<p>-XmppFederationRoute EdgeServer:atl-xmpp-001.litwareinc.com</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Set-CsSite** cmdlet does not accept pipelined input.

## Return Types

The **Set-CsSite** cmdlet does not return any objects or values. Instead, the cmdlet modifies instances of the Microsoft.Rtc.Management.Deploy.Internal.Site+CentralSite object.

## 另请参阅

#### 其他资源

[Get-CsSite](get-cssite.md)

