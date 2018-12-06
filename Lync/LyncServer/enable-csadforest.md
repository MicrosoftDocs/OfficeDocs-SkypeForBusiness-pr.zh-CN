---
title: Enable-CsAdForest
TOCTitle: Enable-CsAdForest
ms:assetid: 2381fca7-294b-486d-919d-e8626cef6fea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425713(v=OCS.15)
ms:contentKeyID: 49312254
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsAdForest

 

_**上一次修改主题：** 2015-03-09_

Makes the Active Directory modifications required before you can install Lync Server. This includes making global changes to the Configuration or System containers; creating universal groups; and creating property sets and display specifiers that are specific to Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsAdForest [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-GroupDomain <Fqdn>] [-GroupDomainController <Fqdn>] [-Report <String>] [-RootDomainController <Fqdn>] [-SkipPrepareCheck <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command prepares the Active Directory forest for the installation of Lync Server. Because the GroupDomain parameter is not used, the universal security groups generated when you run the **Enable-CsAdForest** cmdlet will be created in the local domain.

    Enable-CsAdForest

## EXAMPLE 2

This command prepares the Active Directory forest for the installation of Lync Server. The GroupDomain parameter is used to ensure that the universal security groups created by running the **Enable-CsAdForest** cmdlet will be created in the northamerica.litwareinc.com domain.

    Enable-CsAdForest -GroupDomain northamerica.litwareinc.com

## Detailed Description

Before you can install Lync Server, you must make a number of forest-level changes to Active Directory 域服务. This includes creating display specifiers and objects specific to Lync Server, creating the universal security groups that are needed to manage Lync Server, and granting global settings object access rights to these groups. Forest preparation is typically carried out through the Lync Server Setup Wizard. However, enterprise administrators can also perform forest preparation at any time by running the **Enable-CsAdForest** cmdlet.

After the **Enable-CsAdForest** cmdlet finishes running, you can use the **Get-CsAdForest** cmdlet to verify that the forest is ready for the next step in the installation process.

Note that this cmdlet carries out tasks similar to those carried out by the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /forest /action:ForestPrep

Who can run this cmdlet: You must be an enterprise administrator in order to run the **Enable-CsAdForest** cmdlet locally.

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
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Enable-CsAdForest</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>GroupDomain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain where the new universal security groups should be created. If this parameter is not included, then the groups will be created in the local domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GroupDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where universal group information is stored.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\ForestPrep.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>RootDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of the root domain controller, used to create trust paths for clients that need to access resources in domains other than their own.</p></td>
</tr>
<tr class="odd">
<td><p><em>SkipPrepareCheck</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), causes Enable-CsAdForest to run without first doing its initial preparation checks.</p></td>
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

None.

## Return Types

None.

