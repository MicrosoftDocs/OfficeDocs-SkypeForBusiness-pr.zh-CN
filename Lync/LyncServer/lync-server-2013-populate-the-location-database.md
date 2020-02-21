---
title: Lync Server 2013：填充位置数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中填充位置数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

要在网络中自动定位客户端，首先需要使用网络*线路映射* 填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。

可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。

如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”**** 字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。


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
<td><p>&lt;BSSID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;市&gt;/&lt;县&gt;、&lt;州&gt;、&lt;邮政编码、国家/地区&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>子网</strong></p></td>
<td><p>&lt;子&gt;网&lt;、&gt;说明&lt;、&gt;位置&lt;、&gt;公司&lt;名称&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;市&gt;/&lt;县&gt;、&lt;州&gt;、&lt;邮政编码、国家/地区&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix,.。。</p>
<p>...&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;邮政编码&gt;、&lt;国家/地区&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>开关</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;Description&gt;、&lt;Location&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;市&gt;/&lt;县&gt;、&lt;州&gt;、&lt;邮政编码、国家/地区&gt;</p></td>
</tr>
</tbody>
</table>


如果未填充位置数据库，并且位置策略中的“所需位置”**** 设置为“是”**** 或“免责声明”****，客户端将提示用户手动输入位置。

有关填充位置数据库的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **CsLisSubnet**

  - **CsLisSubnet**

  - CsLisSubnet

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **CsLisPort**

  - **CsLisPort**

  - **CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>将网络元素添加到位置数据库

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

