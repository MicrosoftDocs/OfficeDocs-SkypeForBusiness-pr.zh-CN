---
title: Get-CsAdDomain
TOCTitle: Get-CsAdDomain
ms:assetid: 64554035-3ba5-4aa7-b5d3-91277f107275
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398453(v=OCS.15)
ms:contentKeyID: 49313058
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAdDomain

 

_**上一次修改主题：** 2015-03-09_

Returns information indicating whether Active Directory 域服务 has been correctly configured to allow for the installation of Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>]

## Examples

## EXAMPLE 1

Example 1 returns information regarding the current status of your local Active Directory domain. If your domain settings are up-to-date, and the domain is ready to host Lync Server, the value LC\_DOMAIN\_SETTINGS\_STATE\_READY will be returned.

    Get-CsAdDomain

## EXAMPLE 2

The command shown in Example 2 returns the current status of a specific domain: fabrikam.com. In a multi-domain environment, you can return information for a given domain by including the Domain parameter.

    Get-CsAdDomain -Domain "fabrikam.com" 

## EXAMPLE 3

Example 3 retrieves the current status of your Active Directory domain and, at the same time, writes information about that status to a file named C:\\Logs\\DomainReport.html. This file will detail the steps taken by the **Get-CsAdDomain** cmdlet to determine the readiness status for the domain. Those steps include tasks such as verifying the existence of Active Directory groups and checking permission settings on various Active Directory containers.

    Get-CsAdDomain -Report "C:\Logs\DomainReport.html"

## Detailed Description

Before you can install Lync Server your domain must be correctly prepared, a process that includes extending the Active Directory schema to allow for the addition of attributes specific to Lync Server, in addition to assigning the required Access Control Entries to the universal groups used for managing and operating Lync Server. The **Get-CsAdDomain** cmdlet returns a single value that tells you whether or not Lync Server can be installed on a domain. If the **Get-CsAdDomain** cmdlet returns the value LC\_DOMAINSETTINGS\_STATE\_READY then you can install Lync Server on that domain. If the cmdlet returns LC\_DOMAINSETTINGS\_STATE\_NOT\_READY then you will need to correctly prepare the domain before trying to install Lync Server.

The **Get-CsAdDomain** cmdlet runs as part of the Setup Wizard. If the Wizard determines that the domain is not correctly prepared, an error message is displayed and setup will stop. However, you can run the **Get-CsAdDomain** cmdlet independently of the Setup Wizard in order to verify the domain status before you try to install Lync Server.

The **Get-CsAdDomain** cmdlet performs the same function as the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /domain /action:CheckDomainPrepState

Who can run this cmdlet: By default, any user who has read permissions to Active Directory can run the **Get-CsAdDomain** cmdlet. Typically all domain members have this permission.

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAdDomain"}

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
<td><p><em>Domain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain to be checked; for example: -Domain &quot;litwareinc.com&quot;. If this parameter is not specified, then the local domain will be checked.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the FQDN of the domain controller to be used when running the <strong>Get-CsAdDomain</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Get-CsAdDomain</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\DomainPrep.html&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsAdDomain** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsAdDomain** cmdlet returns instances of the Microsoft.Rtc.Management.Deployment.LcDomainSettingsState object.

## 另请参阅

#### 其他资源

[Disable-CsAdDomain](disable-csaddomain.md)  
[Enable-CsAdDomain](enable-csaddomain.md)

