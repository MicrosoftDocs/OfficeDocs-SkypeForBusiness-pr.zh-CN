---
title: Get-CsClientAccessLicense
TOCTitle: Get-CsClientAccessLicense
ms:assetid: 435062d3-b7f9-400c-9ce7-fb6b6ffce44a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204853(v=OCS.15)
ms:contentKeyID: 49312678
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClientAccessLicense

 

_**上一次修改主题：** 2015-03-09_

Returns information about client license usage in your organization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsClientAccessLicense -LicenseBasedType <String> -LicenseName <String> -MonitoringDatabase <String> -StartDate <DateTime> [-DailyUsage <SwitchParameter>] [-EndDate <DateTime>] <COMMON PARAMETERS>

    Get-CsClientAccessLicense -License <SwitchParameter> <COMMON PARAMETERS>

    COMMON PARAMETERS:

## Examples

## Example 1

The command shown in Example 1 returns Standard license usage for user-based licenses as recorded in the monitoring database atl-sql-001\\Archinst. License usage information will be returned for the time period beginning on June 1, 2012 (6/1/2012) and continuing through the current date.

    Get-CsClientAccessLicense -MonitoringDatabase "atl-sql-001\Archinst" -LicenseName "Standard" -LicenseBasedType "UserBased" -StartDate "6/1/2012"

## Detailed Description

The **Get-CsClientAccessLicense** cmdlet enables administrators to monitor use of their Lync client licenses; this is done by showing client license usage (based on user registrations) during a specified period of time. Note that the cmdlet does not manage your client licenses for you; for example, it will not tell you that you need additional licenses. Instead, the cmdlet simply returns information about the number of licenses that were in use during the specified time period.

You cannot use the **Get-CsClientAccessLicense** cmdlet unless you have enabled the Monitoring Service and call detail recording; that's because registration information is stored in the call detail recording database. Note, too that, as the name suggests, the **Get-CsClientAccessLicense** cmdlet only returns only returns information about your client licenses. If you need information about your server licenses, you can use the [Get-CsService](get-csservice.md) cmdlet to return the fully qualified domain names (FQDN) of all your Lync Server 2013 databases. If the FQDN of a front End server matches the FQDN of a backend database that means you have a Standard license. If the two FQDNs do not match then that means that you have an Enterprise license.

You might also encounter instances when the **Get-CsClientAccessLicense** cmdlet returns incorrect license counts. For example:

\* Licenses can be overcounted if a mobile user logs on from more than one location using a desktop client.

\* Licenses can be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined. In addition, licenses can be overcounted if the mobile device changes its IP address during a session.

\* Licenses can be counted twice for PSTN calls to a Lync client or for a call from a Lync client to a PSTN phone. This is due to the fact that both the Lync user account and the PSTN phone number are used when determining the number of licenses employed in the session.

\* Licenses for Lync phones might not be counted if the phone was logged on to the system before you ran the license usage query.

\* If a user joins a conference using a PSTN phone, a single license usage will be recorded for that call. However, no license is actually required to join a conference using a PSTN phone.

> [!NOTE]  
> For more information, and for ways to work around these issues, see the <a href="lync-server-2013-release-notes.md">Lync Server 2013 发行说明</a>.



To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClientAccessLicense"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsClientAccessLicense** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>License</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns the available license names. This parameter cannot be used with any other parameters; this is the only valid syntax:</p>
<p>Get-CsClientAccessLicense -License</p></td>
</tr>
<tr class="even">
<td><p><em>LicenseBasedType</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Indicates whether the license is UserBased or DeviceBased. With UserBased licenses, each user who accesses Lync Server is required to have a client access license, regardless of the number of devices he or she uses to access Lync Server. With DeviceBased licenses, each device used to access Lync Server requires a separate license.</p>
<p>User-based licensing is typically recommended for users who are not always on site, and who might access Lync Server using any number of different devices. Device-based licensing is aimed at on-site users who typically access Lync Server only through shared devices (such as their desktop computer).</p></td>
</tr>
<tr class="odd">
<td><p><em>LicenseName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the kind of license being retrieved. Valid values are:</p>
<p>* Standard</p>
<p>* Enterprise</p>
<p>* Plus</p></td>
</tr>
<tr class="even">
<td><p><em>MonitoringDatabase</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SQL Server instance for the monitoring database. This is typically specified by using the fully qualified domain name of the SQL Server computer and SQL Server instance of the monitoring database. For example:</p>
<p>-MonitoringDatabase &quot;atl-sql-001.litwareinc.com\archinst&quot;</p>
<p>If the monitoring database is in the default SQL Server instance then you only need to specify the FQDN of the computer running SQL Server:</p>
<p>-MonitoringDatabase &quot;atl-sql-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>StartDate</em></p></td>
<td><p>Required</p></td>
<td><p>System.DateTime</p></td>
<td><p>Beginning date for the time period for which client license usage should be checked. For example, using the US English format the StartDate parameter might look like this:</p>
<p>-StartDate &quot;1/1/2012&quot;</p>
<p>The StartDate must be earlier than the EndDate.</p></td>
</tr>
<tr class="even">
<td><p><em>DailyUsage</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If specified, license usage is broken down on a day-by-day basis for the specified time period. If not specified, then license usage is summarized for the specified time period.</p></td>
</tr>
<tr class="odd">
<td><p><em>EndDate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Ending date for the time period for which client license usage should be checked. For example:</p>
<p>-EndDate &quot;2/1/2012&quot;</p>
<p>The EndDate must be later than the StartDate. Note that the end date does not appear in the output when you call the <strong>Get-CsClientAccessLicense</strong> cmdlet.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsClientAccessLicense** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsClientAccessLicense** cmdlet returns licensing information.

## 另请参阅

#### 其他资源

[Get-CsUser](get-csuser.md)

