---
title: Get-CsRgsConfiguration
TOCTitle: Get-CsRgsConfiguration
ms:assetid: a3667917-cfbf-47c1-8b48-e936594b5357
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412762(v=OCS.15)
ms:contentKeyID: 49313816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRgsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about configuration settings for the 响应组应用程序. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRgsConfiguration -Identity <RgsIdentity>

## Examples

## EXAMPLE 1

Example 1 returns the Response Group configuration settings for the service ApplicationServer:atl-cs-001.litwareinc.com. Because there can only be one collection of settings per service, this command will never return more than a single item.

    Get-CsRgsConfiguration -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com"

## EXAMPLE 2

The command shown in Example 2 returns the value of a single property -- DisableCallContext -- for the Response Group configuration settings found on the service ApplicationServer:atl-cs-001.litwareinc.com. To accomplish this task, **Get-CsRgsConfiguration** is first used to retrieve all the property values for the Response Group configuration settings for ApplicationServer:atl-cs-001.litwareinc.com. Note that this command is enclosed in parentheses; that ensures that Windows PowerShell returns all the property values before doing anything else.

After all the property values have been returned, standard "dot notation" is used to display the value of the property DisableCallContext (and only the value of that property). Standard dot notation consists of the object followed by a period (dot) followed by the name of the property to be displayed. For example, to display the value of the AgentRingbackGracePeriod property (and only the value of that property), you can use this command:

(Get-CsRgsConfiguration -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com").AgentRingbackGracePeriod.

    (Get-CsRgsConfiguration -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com").DisableCallContext

## EXAMPLE 3

The command shown in Example 3 demonstrates how you can return Response Group configuration information from all the computers running the 应用程序服务 that host an instance of the Response Group application. To do this, the command first uses the **Get-CsService** cmdlet and the ApplicationServer parameter to return information about all the servers in the organization that are running the 应用程序服务. This collection is then piped to the **Where-Object** cmdlet, which picks out only those servers where the Applications property contains the application "urn:application:RGS"; that value indicates that the 响应组应用程序 is running on the server.

In turn, those servers are piped to the **ForEach-Object** cmdlet. **ForEach-Object** then takes each server in the collection and uses **Get-CsRgsConfiguration** to return Response Group configuration information from each server.

    Get-CsService -ApplicationServer | Where-Object {$_.Applications -contains "urn:application:RGS"} | ForEach-Object {Get-CsRgsConfiguration -Identity $_.Identity}

## Detailed Description

The 响应组应用程序 provides a way for you to automatically route phone calls to entities such as a help desk or customer support line. When someone calls a designated phone number, that call can be directly routed to the appropriate set of Response Group agents. Alternatively, the call might first be routed to an interactive voice response (IVR) queue. In that queue, the caller will be asked a series of questions (for example, "Are you calling about an existing order?") and then, based on the answers to those questions, be routed to the appropriate Response Group queue.

The **Get-CsRgsConfiguration** cmdlet provides a way for you to return information about how the 响应组应用程序 has been configured. Note that, by default, this cmdlet only returns information from one instance of the 响应组应用程序 at a time. For example, if you have separate installations of the 响应组应用程序 -- one on ApplicationServer:atl-cs-001.litwareinc.com and one on ApplicationServer:dublin-cs-001.litwareinc.com -- you will typically need to make separate calls to **Get-CsRgsConfiguration** in order to return information for each of these Response Group instances. However, the Examples section in this topic shows a way to work around this issue.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRgsConfiguration** cmdlet locally: RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRgsConfiguration"}

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
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Name of the service hosting the Response Group configuration settings; for example: -Identity &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;. If you do not include this parameter, <strong>Get-CsRgsConfiguration</strong> will prompt you to supply an Identity.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. **Get-CsRgsConfiguration** accepts a string value representing the Identity of the Response Group configuration settings.

## Return Types

**Get-CsRgsConfiguration** returns instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.ServiceSettings object.

## 另请参阅

#### 其他资源

[Move-CsRgsConfiguration](move-csrgsconfiguration.md)  
[Set-CsRgsConfiguration](set-csrgsconfiguration.md)

