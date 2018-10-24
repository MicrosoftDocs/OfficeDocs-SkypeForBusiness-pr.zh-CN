---
title: Get-CsPersistentChatEndpoint
TOCTitle: Get-CsPersistentChatEndpoint
ms:assetid: 2c37edd6-6892-4b2d-8586-6f59ab668d4b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204764(v=OCS.15)
ms:contentKeyID: 49312345
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatEndpoint

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat endpoints configured for use in the organization. A Persistent Chat endpoint is an Active Directory contact object provides a friendly URL for a Lync Server 2013 Persistent Chat pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatEndpoint [-Identity <UserIdParameter>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-LdapFilter <String>] [-OU <OUIdParameter>] [-PersistentChatPoolFqdn <Fqdn>] [-ResultSize <Unlimited>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the Persistent Chat endpoints configured for use in the organization.

    Get-CsPersistentChatEndpoint

## Example 2

Example 2 uses the Filter parameter to return information for the Persistent Chat endpoint that has the Identity "sip:pce@litwareinc.com". In this case, the SIP address is used as the Identity.

    Get-CsPersistentChatEndpoint -Identity "sip:pce@litwareinc.com"

## Example 3

Example 3 returns information about all the Persistent Chat endpoints configured for use on the Persistent Chat pool atl-pcpool-001.litwareinc.com. This is done by including the PoolFqdn parameter followed by the fully qualified domain name of the Persistent Chat pool.

    Get-CsPersistentChatEndpoint -PersistentChatPoolFqdn atl-pcpool-001.litwareinc.com

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

When you install the Persistent Chat service, an endpoint is automatically created for each Persistent Chat pool; this endpoint is an Active Directory contact object that maintains the pool URI. If all your users are running Lync 2013 this should be sufficient.

However, if you have users running legacy clients (such as Microsoft Lync 2010 these users might find the default Persistent Chat URIs difficult to work with and difficult to use when pointing their legacy client towards the pool. Because of this, administrators can use the [New-CsPersistentChatEndpoint](new-cspersistentchatendpoint.md) cmdlet to create an additional contact object for the pool, a contact object that provides a friendlier, easier-to-use URI. The **Get-CsPersistentChatEndpoint** cmdlet provides a way for you to return information about all the Persistent Chat endpoints configured for use in your organization.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatEndpoint"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsPersistentChatEndpoint** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the <strong>Get-CsPersistentChatEndpoint</strong> cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve user information. To connect to a particular domain controller, include the DomainController parameter followed by the fully qualified domain name (FQDN). For example:</p>
<p>-DomainController &quot;atl-dc-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on Lync Server-specific attributes. For example, you can limit returned data to Persistent Chat endpoints that have been assigned a specific voice policy, or endpoints have not been assigned a specific voice policy.</p>
<p>The Filter parameter uses the same Windows PowerShell filtering syntax that is used by the <strong>Where-Object</strong> cmdlet. For example, a filter that returns only endpoints that have been assigned a per-user conferencing policy would look like this, with ConferencingPolicy representing the Active Directory attribute, -ne representing the comparison operator (not equal to), and $Null (a built-in Windows PowerShell variable) representing the filter value:</p>
<p>-Filter {ConferencingPolicy -ne $Null}</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Unique identifier for the Persistent Chat endpoint to be returned. Endpoint Identities are typically specified using the endpoint's SIP address or display name; for example:</p>
<p>-Identity &quot;sip:pcEndpoint1@litwareinc.com&quot;</p>
<p>However, you can also use the full Identity of the endpoint; for example:</p>
<p>-Identity &quot;CN={33e5014b-dcba-46b5-9bf7-48f4d5fca69d}, CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litwareinc,DC=com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>LdapFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on generic Active Directory attributes (that is, attributes that are not specific to Lync Server). Because Persistent Chat endpoints have very few non-Lync Server attributes this parameter is of minimal value.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Enables you to return information about user accounts in a specific organizational unit (OU) or container. Because new Persistent Chat endpoints are all created in the same Active Directory container (ApplicationContacts/RTC Service/Services/Configuration) this parameter is of minimal value.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the Persistent Chat pool associated with the Persistent Chat endpoint.</p></td>
</tr>
<tr class="even">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven contacts (regardless of the number of users that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven users will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three contacts in your forest, the command will return those three contacts, and then complete without error.</p></td>
</tr>
</tbody>
</table>


## Input Types

String value. The **Get-CsPersistentChatEndpoint** cmdlet can accept a string value representing the Identity or the SIP address of a Persistent Chat endpoint.

## Return Types

The **Get-CsPersistentChatEndpoint** cmdlet returns instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSPersistentChatContact class.

## 另请参阅

#### 其他资源

[New-CsPersistentChatEndpoint](new-cspersistentchatendpoint.md)  
[Remove-CsPersistentChatEndpoint](remove-cspersistentchatendpoint.md)

