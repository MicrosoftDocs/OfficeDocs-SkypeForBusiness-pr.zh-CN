---
title: Get-CsService
TOCTitle: Get-CsService
ms:assetid: f687d41b-2cb3-4c32-ae28-90e25cdd0d6a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413038(v=OCS.15)
ms:contentKeyID: 49314768
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsService

 

_**上一次修改主题：** 2015-03-09_

Returns information about the services and server roles being used in your Lync Server infrastructure. A service is an instance of a role that has been deployed in a Lync Server pool. For example, you might have a pool of computers all running the Monitoring service. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsService [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsService [-ApplicationServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-ApplicationDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-ArchivingServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-ArchivingDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-BackupServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-CentralManagement <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-CentralManagementDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-ConferencingServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-Director <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-EdgeServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-TrustedApplicationPool <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-FileStore <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-PersistentChatServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-PersistentChatComplianceDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-PersistentChatDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-LegalInterceptServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-ManagementServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-MediationServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-MonitoringServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-MonitoringDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-PstnGateway <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-Registrar <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-UserServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-UserDatabase <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-WacServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-WebServer <SwitchParameter>] <COMMON PARAMETERS>

    Get-CsService [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-PoolFqdn <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the Lync Server services and server roles currently running in your organization.

    Get-CsService

## EXAMPLE 2

Example 2 returns information only about the 应用程序服务. You can return information for other services/server roles simply by using the appropriate parameter. For example, this command returns information about the file store:

    Get-CsService -ApplicationServer

## EXAMPLE 3

Example 3 reports back the Identity for each service located on the pool atl-cs-001.litwareinc.com. To carry out this task, the command first calls the **Get-CsService** cmdlet and the PoolFqdn parameter to return only those services and server roles found on the pool atl-cs-001.litwareinc.com. This collection is then piped to the **Select-Object** cmdlet, which reports back the Identity of each item in the collection.

    Get-CsService -PoolFqdn "atl-cs-001.litwareinc.com" | Select-Object Identity

## EXAMPLE 4

In Example 4, information is returned for all the services/server roles found on the Redmond site. This is done by first calling the **Get-CsService** cmdlet without any parameters in order to return a collection of all the services and server roles currently in use in the organization. This data is then piped to the **Where-Object** cmdlet, which picks out only those items where the SiteID property is equal to site:Redmond.

    Get-CsService | Where-Object {$_.SiteID -eq "site:Redmond"}

## EXAMPLE 5

The command shown in Example 5 returns information about all the services that list the Registrar as a dependent service. To do this, the **Get-CsService** cmdlet is called in order to return a collection of all the services and server roles currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects each item where the DependentServiceList property includes the string value "Registrar". The **Where-Object** cmdlet criteria is specified by using the -like operator and the wildcard value "\*Registrar\*".

    Get-CsService | Where-Object {$_.DependentServiceList -like "*Registrar*"}

## Detailed Description

The capabilities found in Lync Server are typically expressed as services or as server roles. For example, you can configure Lync Server to automatically save a transcript of every instant messaging session that takes place in your organization. In order to do this, you must install the 存档服务器 server role. Services and server roles can be configured at the same time you install Lync Server itself, or they can be configured after the software is up and running.

The **Get-CsService** cmdlet enables you to return information about the server roles and services running in your organization. Called without any additional parameters, the **Get-CsService** cmdlet returns detailed information about all your services and server roles. Alternatively, you can limit the returned data to a specified pool by using the PoolFqdn parameter. In addition, you can use any number of switch parameters to limit the returned data to a specific type of service. A switch parameter is a parameter that does not require a parameter value. For example, this command returns information about all your Archiving Servers:

Get-CsService –ArchivingServer

Note that you can only use one such switch parameter per command. The following command, which tries to return information about both Archiving Servers and Monitoring Servers, will fail:

Get-CsService –ArchivingServer –MonitoringServer

If you need to return information for multiple server roles, you can use the **Get-CsService** cmdlet to return a complete collection of service data, and then pipe that data to the **Where-Object** cmdlet:

Get-CsService | Where-Object {$\_.Role –eq "ArchivingServer" –or $\_.Role –eq "MonitoringServer"}

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsService** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsService"}

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
<td><p><em>ApplicationDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Application databases used in your organization. Application databases are used by the 应用程序服务.</p></td>
</tr>
<tr class="even">
<td><p><em>ApplicationServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 应用程序服务. The 应用程序服务 provides a way to run applications created by using the Microsoft 统一通信托管 API (UCMA).</p></td>
</tr>
<tr class="odd">
<td><p><em>ArchivingDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Archiving databases used in your organization. Archiving databases store transcripts of instant messaging sessions.</p></td>
</tr>
<tr class="even">
<td><p><em>ArchivingServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Archiving Servers used in your organization. Archiving Servers enable you to save the transcripts of instant messaging sessions.</p></td>
</tr>
<tr class="odd">
<td><p><em>BackupServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the backup servers used in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>CentralManagement</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 中央管理服务 used in your organization. The 中央管理服务 is used to send configuration data to computers running Lync Server services.</p></td>
</tr>
<tr class="odd">
<td><p><em>CentralManagementDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 中央管理存储 used in your organization. The 中央管理存储 maintains configuration information for Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><em>ConferencingServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the A/V 会议服务 used in your organization. The A/V 会议服务 is used to conduct meetings and conferences.</p></td>
</tr>
<tr class="odd">
<td><p><em>Director</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Directors used in your organization. Directors are empowered to handle user requests and user authentication, but do not house user accounts. Directors are typically used to handle requests from external users.</p></td>
</tr>
<tr class="even">
<td><p><em>EdgeServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Edge Servers used in your organization. Edge Servers provide connectivity between your internal network and the Internet.</p></td>
</tr>
<tr class="odd">
<td><p><em>FileStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the File Stores used in your organization. The File Store is used to maintain Lync Server files, such as audio files used by the Announcement service.</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcards to specify the service (or services) to be returned. You cannot use both the Identity and the Filter parameters in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier of the specific service or server role to be returned. For example: -Identity &quot;Registrar:atl-cs-001.litwareinc.com&quot;.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>LegalInterceptServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the legal intercept servers used in your organization. Legal intercept servers provide real-time interception of instant messaging communications on Office 365.</p></td>
</tr>
<tr class="odd">
<td><p><em>ManagementServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 中央管理服务器 used in your organization. The 中央管理服务器 is commonly collocated with the Front End Servers and is responsible for accessing information in the 中央管理存储.</p></td>
</tr>
<tr class="even">
<td><p><em>MediationServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Mediation Servers used in your organization. Mediation Servers help provide a bridge between your Enterprise Voice network and the public switched telephone network (PSTN).</p></td>
</tr>
<tr class="odd">
<td><p><em>MonitoringDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the monitoring databases used in your organization. Monitoring databases store Enterprise Voice phone usage and call quality information.</p></td>
</tr>
<tr class="even">
<td><p><em>MonitoringServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Monitoring Servers used in your organization. Monitoring Servers are used to track Enterprise Voice phone usage and call quality.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatComplianceDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the databases used for maintaining Persistent Chat compliance information.</p></td>
</tr>
<tr class="even">
<td><p><em>PersistentChatDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the databases used for maintaining Persistent Chat information.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Persistent Chat servers used in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>PoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool hosting the service or server role. If you use the PoolFqdn parameter without specifying a service-specific parameter, then all the services and server roles found on that pool will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>PstnGateway</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the public switched telephone network (PSTN) gateways used in your organization. PSTN gateways translate signals from Enterprise Voice devices to signals that can be understood by PSTN devices, and vice-versa.</p></td>
</tr>
<tr class="even">
<td><p><em>Registrar</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Registrars used in your organization. Registrars are used to authenticate users and to keep track of a user’s current status.</p></td>
</tr>
<tr class="odd">
<td><p><em>TrustedApplicationPool</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the trusted application pools used in your organization. Trusted applications pools host computers that run trusted applications.</p></td>
</tr>
<tr class="even">
<td><p><em>UserDatabase</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 用户数据库 used in your organization. User databases store data needed by the User Server service.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the 用户服务 service used in your organization. The 用户服务 service provides such things as user replication, in-band provisioning, presence publication and notification, and contact card exchange.</p></td>
</tr>
<tr class="even">
<td><p><em>WacServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Office Web Apps servers used with Microsoft Lync Server. Office Web Apps server was previously known as &quot;WacServer&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns information about the Web 服务 service used in your organization. The Web 服务 service host web-based applications such as the Address Book service.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsService** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsService** cmdlet returns different objects based on the parameters used when calling the cmdlet. For example, if you include the MonitoringDatabase parameter, the **Get-CsService** cmdlet returns instances of the Microsoft.Rtc.Management.Xds.DisplayMonitoringDatabase object. To determine the objects returned using other parameters, call the **Get-CsService** cmdlet using one of those parameters, and then pipe the returned object to the **Get-Member** cmdlet. For example: Get-CsService -Registrar | Get-Member.

## 另请参阅

#### 其他资源

[Set-CsApplicationServer](set-csapplicationserver.md)  
[Set-CsArchivingServer](set-csarchivingserver.md)  
[Set-CsConferenceServer](set-csconferenceserver.md)  
[Set-CsDirector](set-csdirector.md)  
[Set-CsEdgeServer](set-csedgeserver.md)  
[Set-CsManagementServer](set-csmanagementserver.md)  
[Set-CsMediationServer](set-csmediationserver.md)  
[Set-CsMonitoringServer](set-csmonitoringserver.md)  
[Set-CsRegistrar](set-csregistrar.md)  
[Set-CsUserServer](set-csuserserver.md)  
[Set-CsWebServer](set-cswebserver.md)

