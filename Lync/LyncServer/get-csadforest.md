---
title: Get-CsAdForest
TOCTitle: Get-CsAdForest
ms:assetid: f063df2f-fdb2-4599-bfb0-fb4ba3584e3b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412995(v=OCS.15)
ms:contentKeyID: 49314689
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAdForest

 

_**上一次修改主题：** 2015-03-09_

Returns information indicating whether your Active Directory forest has been correctly configured to allow for the installation of Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAdForest [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-RootDomainController <Fqdn>] [-SkipPrepareCheck <$true | $false>]

## Examples

## EXAMPLE 1

Example 1 returns information indicating whether your Active Directory forest has been correctly configured to allow for the installation of Lync Server.

    Get-CsAdForest

## EXAMPLE 2

In Example 2, forest state information is returned and the forest readiness is displayed on the screen. In addition, detailed information about the steps taken to determine the forest state is written to a file named C:\\Logs\\ForestState.html. This file includes a detailed list of all the Active Directory groups and Active Directory containers where permissions were verified.

    Get-CsAdForest -Report C:\Logs\ForestState.html

## Detailed Description

Before you can install Lync Server, you must make a number of forest-level changes to Active Directory 域服务. This includes creating display specifiers and objects specific to Lync Server, creating the universal security groups that are needed to manage Lync Server, and granting global settings object access permissions to these groups. The **Get-CsAdForest** cmdlet returns a single value that tells you whether or not Lync Server can be installed in a forest. If the **Get-CsAdForest** cmdlet returns the value LC\_FORESTSETTINGS\_STATE\_READY then you can install Lync Server in the forest. If the cmdlet returns LC\_FORESTSETTINGS\_STATE\_NOT\_READY then you will need to correctly prepare the forest before trying to install Lync Server.

The **Get-CsAdForest** cmdlet runs as part of the Setup Wizard; if the Wizard determines that the forest is not correctly prepared, then you will receive an error message and Setup will stop. However, you can also run the **Get-CsAdForest** cmdlet independently of the Setup Wizard in order to verify the forest status before you try to install Lync Server.

The **Get-CsAdForest** cmdlet performs the same function as the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /forest /action:CheckForestPrepState

Who can run this cmdlet: By default, anyone who has read permissions to Active Directory can run the **Get-CsAdForest** cmdlet locally. Typically all domain members have this permission.

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAdForest"}

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
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of a global catalog server in your domain. This parameter is not required if you are running the <strong>Get-CsAdForest</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in AD DS, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
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
<td><p>When set to True ($True), causes Get-CsAdForest to run without first doing its initial preparation checks.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsAdForest** cmdlet returns instances of the Microsoft.Rtc.Management.Deployment.LcForestSettingsState object.

