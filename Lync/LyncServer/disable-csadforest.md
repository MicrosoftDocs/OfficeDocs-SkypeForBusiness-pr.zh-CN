---
title: Disable-CsAdForest
TOCTitle: Disable-CsAdForest
ms:assetid: 06a6117c-27da-400f-8db9-eb28fe353aae
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398122(v=OCS.15)
ms:contentKeyID: 49311888
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsAdForest

 

_**上一次修改主题：** 2015-03-09_

Undoes the forest preparation tasks carried out by the **Enable-CsAdForest** cmdlet. This cmdlet is typically used only if you are uninstalling Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Disable-CsAdForest [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-GroupDomain <Fqdn>] [-GroupDomainController <Fqdn>] [-Report <String>] [-RootDomainController <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 rolls back the forest preparation tasks carried out by the **Enable-CsAdForest** cmdlet. Because the Force parameter is not included, the command will fail if the **Disable-CsAdForest** cmdlet detects that at least one of the domains in the forest is still prepared for Lync Server. In that case, you will need to rolls back the domain preparation by running the **Disable-CsAdDomain** cmdlet.

    Disable-CsAdForest

## EXAMPLE 2

In Example 2, forest preparation is rolled back even if the **Disable-CsAdForest** cmdlet detects that at least one of the domains in the forest is still prepared for Lync Server. Rollback is forced by including the Force parameter.

    Disable-CsAdForest -Force

## Detailed Description

When you install Lync Server, you make a number of forest-level changes to Active Directory 域服务. These changes (which can be carried out by using the **Enable-CsAdForest** cmdlet) include creating objects and display specifiers that are specific to Lync Server, creating universal security groups needed to manage Lync Server, and granting global settings object access administrative rights and permissions to these groups. If you later decide to uninstall Lync Server (or if you encounter issues during the setup process) you might need to roll back these forest-level changes. The **Disable-CsAdForest** cmdlet provides a way for you to undo all the forest-level modifications made by the **Enable-CsAdForest** cmdlet.

The tasks carried out by the **Disable-CsAdForest** cmdlet are similar to the tasks carried out by the following Microsoft Office Communications Server 2007 R2 command:

Lcscmd.exe /forest /action:ForestUnprep

Who can run this cmdlet: You must be an enterprise administrator in order to run the **Disable-CsAdForest** cmdlet locally.

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
<td><p>If present, forces the rollback of the forest preparation steps even if the <strong>Disable-CsAdForest</strong> cmdlet detects that at least one of the domains in the forest is still prepared for Lync Server. If not present, the command will fail if the <strong>Disable-CsAdForest</strong> cmdlet detects that at least one of the domains in the forest is still prepared for Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>GlobalCatalog</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a global catalog server in your domain. This parameter is not required if you are running the <strong>Disable-CsComputer</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory 域服务, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>GroupDomain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain where the Lync Server universal groups were created (for example, -GroupDomain asia.litwareinc.com). If this parameter is not included, the <strong>Disable-CsAdForest</strong> cmdlet will look for the universal groups in the local domain.</p></td>
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
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\DisableForest.html&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>RootDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of the root domain controller, used to create trust paths for clients that need to access resources in domains other than their own.</p></td>
</tr>
<tr class="odd">
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

