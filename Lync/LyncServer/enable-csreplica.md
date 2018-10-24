---
title: Enable-CsReplica
TOCTitle: Enable-CsReplica
ms:assetid: 4a745da5-5b09-4b5a-8ab6-8b8b03d7afc6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425965(v=OCS.15)
ms:contentKeyID: 49312766
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsReplica

 

_**上一次修改主题：** 2015-03-09_

Adds the local computer to the Lync Server replication path. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsReplica [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 adds the local computer to the Lync Server replication path.

    Enable-CsReplica

## Detailed Description

When a service or server role is installed on a computer, that computer needs to be added to the replication path; doing so enables the computer to receive the topology and configuration files from the 中央管理存储. The **Enable-CsReplica** cmdlet provides a way for you to manually add a computer to the replication path. As a general rule, you will not need to manually add a computer to the replication path. Instead, this will automatically take place when you install Lync Server on a computer.

Who can run this cmdlet: You must be a local administrator and a member of the domain in order to run the **Enable-CsReplica** cmdlet locally.

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
<td><p>Fully qualified domain name (FQDN) of a global catalog server in your domain. This parameter is not required if you are running the <strong>Enable-CsReplica</strong> cmdlet on a computer with an account in your domain.</p></td>
</tr>
<tr class="even">
<td><p><em>GlobalSettingsDomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of a domain controller where global settings are stored. If global settings are stored in the System container in Active Directory 域服务, then this parameter must point to the root domain controller. If global settings are stored in the Configuration container, then any domain controller can be used and this parameter can be omitted.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\EnableReplica.html&quot;</p></td>
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

None. The **Enable-CsReplica** cmdlet does not accept pipelined input.

## Return Types

None. The **Enable-CsReplica** cmdlet does not return any values or objects.

## 另请参阅

#### 其他资源

[Get-CsManagementStoreReplicationStatus](get-csmanagementstorereplicationstatus.md)

