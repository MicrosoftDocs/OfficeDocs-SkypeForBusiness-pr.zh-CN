---
title: Publish-CsTopology
TOCTitle: Publish-CsTopology
ms:assetid: d8f5dfd9-0ab6-4703-9d50-2fa50b3fd58b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398953(v=OCS.15)
ms:contentKeyID: 49314430
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publish-CsTopology

 

_**上一次修改主题：** 2015-03-09_

Publishes the Lync Server topology retrieved by using the **Get-CsTopology** cmdlet. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Publish-CsTopology -FileName <String> <COMMON PARAMETERS>

    Publish-CsTopology -Document <XElement> <COMMON PARAMETERS>

    Publish-CsTopology -FinalizeUninstall <SwitchParameter> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BackupFileName <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 retrieve and then republish the current topology. To carry out these tasks, the first command in the example uses the **Get-CsTopology** cmdlet and the AsXml parameter to retrieve the current topology; the Windows PowerShell redirection symbol \> is then used to save the retrieved data to a file named C:\\Topologies\\Topology.xml. (Note, too, that the ToString method is used to convert the retrieved topology to a string value.) The second command in the example then uses the **Publish-CsTopology** cmdlet to republish the newly retrieved topology.

    (Get-CsTopology -AsXml).ToString() > C:\Topologies\Topology.xml 
    Publish-CsTopology -FileName "C:\Topologies\Topology.xml"

## Detailed Description

After you have installed Lync Server, you will eventually need to make changes to the Lync Server infrastructure; for example, you might need to add a new site, delete an existing Registrar pool, or add an additional 存档服务器. These infrastructure changes must be made by using 拓扑生成器. After you have made the changes in 拓扑生成器, you can then publish and enable those changes using that same tool. These latter two steps are very important: although you can make as many modifications as you want using the 拓扑生成器, those modifications do not actually take effect, and your Lync Server infrastructure will not actually change, until the modifications have been published and the new topology has been enabled.

When changes are published, the new information (for example, a new site or a new server role) is written to the 中央管理存储. However, these new (or the newly modified) objects do not immediately join your topology; that occurs only when the updated topology has been enabled. If you select the Publish option in 拓扑生成器 both of these steps will take place: the changes will be published (written to the 中央管理存储) and then the new topology will be enabled.

The **Publish-CsTopology** cmdlet is no longer the recommended way to publish topologies created by using 拓扑生成器; instead, publishing should be done within 拓扑生成器, using the steps outlined in the previous paragraph. This is because 拓扑生成器 now uses the 拓扑生成器 XML file format (.tbxml); this file format cannot be published by using the **Publish-CsTopology** cmdlet. The only thing you can do with the **Publish-CsTopology** cmdlet is republish a topology retrieved by using the **Get-CsTopology** cmdlet. After publishing the topology in this manner, you will then need to reconfigure your simple URLs.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Publish-CsTopology** cmdlet: RTCUniversalServerAdmins. However, if setup permissions have not been delegated then you must be a domain administrator in order to run the **Publish-CsTopology** cmdlet. In order to give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet against every Active Directory container that contains computers running Lync Server services. Note that this restriction also applies to enabling a topology through 拓扑生成器. If you have not delegated permissions by using the **Set-CsSetupPermission** cmdlet, then only a domain administrator will be able to publish a topology through 拓扑生成器.

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
<td><p><em>Document</em></p></td>
<td><p>Required</p></td>
<td><p>System.Xml.Linq.XElement</p></td>
<td><p>Enables you to publish an XML element rather than an XML file. This XML element must be configured as a System.XML.Linq.XElement object.</p></td>
</tr>
<tr class="even">
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the XML file containing the new topology information.</p></td>
</tr>
<tr class="odd">
<td><p><em>FinalizeUninstall</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Used only when uninstall Lync Server.After the Central Management Server has been removed, use Publish-CsTopology and the FinalizeUninstall parameter to publish an empty topology. Among other things, this removes all the Active Directory entries for the Central Management Server.</p></td>
</tr>
<tr class="even">
<td><p><em>BackupFileName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the backup file automatically created when you run the <strong>Publish-CsTopology</strong> cmdlet. If this parameter is not specified, then the <strong>Publish-CsTopology</strong> cmdlet will create a backup file in your Temp folder (%temp%) similar to this: Publish-CsTopology-Backup-[2010_10_01][08_30_00]. In that file name, 2010_10_01 represents the date that publication took place: year (2010), month (10), and day (01). In addition, 08_30_00 represents the time of day when publication took place: hour (08), minutes (30), and seconds (00).</p></td>
</tr>
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
<td><p>Fully qualified domain name (FQDN) of a global catalog server in your domain. This parameter is not required if you are running the <strong>Publish-CsTopology</strong> cmdlet on a computer with an account in your domain.</p></td>
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
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\Publish_Topology.html&quot;</p></td>
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

None. The **Publish-CsTopology** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Publish-CsTopology** cmdlet publishes instances of the Microsoft.Rtc.Management.Deploy.Internal.DefaultTopology object.

## 另请参阅

#### 其他资源

[Enable-CsTopology](enable-cstopology.md)  
[Get-CsTopology](get-cstopology.md)  
[New-CsSimpleUrlConfiguration](new-cssimpleurlconfiguration.md)  
[Test-CsTopology](test-cstopology.md)

