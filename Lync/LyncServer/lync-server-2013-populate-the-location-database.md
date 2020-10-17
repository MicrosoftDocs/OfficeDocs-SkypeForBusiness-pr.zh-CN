---
title: Lync Server 2013：填充位置数据库
description: Lync Server 2013：填充位置数据库。
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
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543168"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="f6569-103">在 Lync Server 2013 中填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="f6569-103">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6569-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f6569-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f6569-p101">要在网络中自动定位客户端，首先需要使用网络*线路映射* 填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。</span><span class="sxs-lookup"><span data-stu-id="f6569-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="f6569-107">可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。</span><span class="sxs-lookup"><span data-stu-id="f6569-107">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="f6569-p102">如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”\*\*\*\* 字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="f6569-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6569-110">网络元素</span><span class="sxs-lookup"><span data-stu-id="f6569-110">Network Element</span></span></th>
<th><span data-ttu-id="f6569-111">所需列</span><span class="sxs-lookup"><span data-stu-id="f6569-111">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6569-112"><strong>无线访问点</strong></span><span class="sxs-lookup"><span data-stu-id="f6569-112"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="f6569-113">&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; 公司名称 &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="f6569-113">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="f6569-114">&lt;.。。StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; 市/县 &gt; 、 &lt; 州 &gt; 、 &lt; 邮政编码 &gt; 、 &lt; 国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="f6569-114">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6569-115"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="f6569-115"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f6569-116">&lt;子网 &gt; 、 &lt; 说明 &gt; 、 &lt; 位置 &gt; 、 &lt; 公司名称 &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="f6569-116">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="f6569-117">&lt;.。。StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; 市/县 &gt; 、 &lt; 州 &gt; 、 &lt; 邮政编码 &gt; 、 &lt; 国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="f6569-117">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6569-118"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="f6569-118"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="f6569-119">&lt;ChassisID &gt; 、 &lt; PortIDSubType &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; 公司名称 &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="f6569-119">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="f6569-120">&lt;.。。PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; City &gt; 、 &lt; State &gt; 、 &lt; 邮政编码 &gt; 、 &lt; 国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="f6569-120">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6569-121"><strong>开关</strong></span><span class="sxs-lookup"><span data-stu-id="f6569-121"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="f6569-122">&lt;ChassisID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; 公司名称 &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="f6569-122">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="f6569-123">&lt;.。。StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; 市/县 &gt; 、 &lt; 州 &gt; 、 &lt; 邮政编码 &gt; 、 &lt; 国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="f6569-123">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6569-124">如果未填充位置数据库，并且位置策略中的“所需位置”\*\*\*\* 设置为“是”\*\*\*\* 或“免责声明”\*\*\*\*，客户端将提示用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="f6569-124">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="f6569-125">有关填充位置数据库的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6569-125">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="f6569-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="f6569-126">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="f6569-127">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="f6569-127">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="f6569-128">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="f6569-128">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="f6569-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="f6569-129">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="f6569-130">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="f6569-130">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="f6569-131">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="f6569-131">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="f6569-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="f6569-132">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="f6569-133">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="f6569-133">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="f6569-134">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="f6569-134">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="f6569-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="f6569-135">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="f6569-136">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="f6569-136">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="f6569-137">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="f6569-137">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="f6569-138">将网络元素添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="f6569-138">To add network elements to the location database</span></span>

1.  <span data-ttu-id="f6569-139">运行以下 cmdlet，以将子网位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="f6569-139">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="f6569-p103">对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：</span><span class="sxs-lookup"><span data-stu-id="f6569-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="f6569-143">另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。</span><span class="sxs-lookup"><span data-stu-id="f6569-143">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="f6569-144">运行以下 cmdlet，以将无线位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="f6569-144">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="f6569-145">另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。</span><span class="sxs-lookup"><span data-stu-id="f6569-145">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="f6569-146">运行以下 cmdlet，以将交换机位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="f6569-146">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="f6569-147">另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。</span><span class="sxs-lookup"><span data-stu-id="f6569-147">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="f6569-148">运行以下 cmdlet，以将端口位置添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="f6569-148">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="f6569-p104">PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="f6569-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="f6569-151">另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。</span><span class="sxs-lookup"><span data-stu-id="f6569-151">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

