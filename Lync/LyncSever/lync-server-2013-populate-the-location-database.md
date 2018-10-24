---
title: 填充位置数据库
TOCTitle: 填充位置数据库
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413069(v=OCS.15)
ms:contentKeyID: 49314825
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 填充位置数据库

 

_**上一次修改主题：** 2015-03-09_

要在网络中自动定位客户端，首先需要使用网络*线路映射* 填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。

可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。

如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>网络元素</th>
<th>所需列</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>无线访问点</strong></p></td>
<td><p>&lt;BSSID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;PreDirectional&gt;……</p>
<p>&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;PostalCode&gt;、&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>子网</strong></p></td>
<td><p>&lt;Subnet&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;PreDirectional&gt;……</p>
<p>&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;PostalCode&gt;、&lt;Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>端口</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;……</p>
<p>&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;PostalCode&gt;、&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>交换机</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;CompanyName&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、&lt;PreDirectional&gt;……</p>
<p>&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;PostalCode&gt;、&lt;Country&gt;</p></td>
</tr>
</tbody>
</table>


如果未填充位置数据库，并且位置策略中的“所需位置”设置为“是”或“免责声明”，客户端将提示用户手动输入位置。

有关填充位置数据库的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

## 将网络元素添加到位置数据库

1.  运行以下 cmdlet，以将子网位置添加到位置数据库。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  运行以下 cmdlet，以将无线位置添加到位置数据库。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  运行以下 cmdlet，以将交换机位置添加到位置数据库。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  运行以下 cmdlet，以将端口位置添加到位置数据库
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName
    
    另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

