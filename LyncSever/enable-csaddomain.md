---
title: Enable-CsAdDomain
TOCTitle: Enable-CsAdDomain
ms:assetid: a39768de-51ae-45e8-b6b7-441b5da0b3b2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412764(v=OCS.15)
ms:contentKeyID: 49313799
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsAdDomain

 

_**上一次修改主题：** 2015-03-09_

Modifies the security settings on the universal groups created during forest preparation. These modifications provide the permissions needed to host and manage users enabled for Lync Server within the domain. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsAdDomain [-Confirm [<SwitchParameter>]] [-CrossForest <SwitchParameter>] [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-SkipPrepareCheck <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 prepares the local domain for the installation of Lync Server.

    Enable-CsAdDomain

## EXAMPLE 2

Example 2 prepares the domain asia.litwareinc.com for the installation of Lync Server.

    Enable-CsAdDomain -Domain asia.litwareinc.com

## Detailed Description

Before you can install Lync Server in a domain, that domain must be correctly prepared, a process that includes extending the Active Directory schema to allow for the addition of attributes specific to Lync Server as well as assigning the required Access Control Entries to the universal groups needed for managing and operating Lync Server. Domain preparation is typically carried out through the Lync Server Setup Wizard. However, administrators can also perform domain preparation by running the **Enable-CsAdDomain** cmdlet.

After the **Enable-CsAdDomain** cmdlet finishes running, you can use the **Get-CsAdDomain** cmdlet to verify that the domain is ready for the next step in the installation process.

> [!NOTE]  
> If you receive the following error, “Cannot find the object ‘CrossRef’ in Active Directory” while running tasks to prepare a child domain of a single-forest environment with multiple domains, you may have to manually add the RTCComponentUniversalServices group from the parent domain to the Windows Authorization Access group in the child domain.



This cmdlet carries out tasks similar to those carried out by the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /domain /action:DomainPrep

Who can run this cmdlet: You must be a domain administrator in order to run the **Enable-CsAdDomain** cmdlet locally.

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
<td><p><em>CrossForest</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, indicates that domain preparation is taking place in a domain in a different forest. This parameter is not required if the domain being enabled is in the same forest as the computer where the command is being run.</p></td>
</tr>
<tr class="odd">
<td><p><em>Domain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain where domain preparation is to take place (for example, -Domain asia.litwareinc.com). If this parameter is not included, domain preparation will take place on the local domain.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the FQDN of the domain controller to be used when running the <strong>Enable-CsAdDomain</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Enable-CsAdDomain</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory 域服务, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="even">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\DomainPrep.html&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>SkipPrepareCheck</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True ($True), then the <strong>Enable-CsAdDomain</strong> cmdlet will skip its initial preparation check.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Enable-CsAdDomain** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Disable-CsAdDomain](disable-csaddomain.md)  
[Get-CsAdDomain](get-csaddomain.md)

