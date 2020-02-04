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
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="ec96a-102">在 Lync Server 2013 中填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="ec96a-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec96a-103">_**主题上次修改时间：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="ec96a-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="ec96a-p101">要在网络中自动定位客户端，首先需要使用网络*线路映射*填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。</span><span class="sxs-lookup"><span data-stu-id="ec96a-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="ec96a-106">可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。</span><span class="sxs-lookup"><span data-stu-id="ec96a-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="ec96a-p102">如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”\*\*\*\* 字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="ec96a-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec96a-109">网络元素</span><span class="sxs-lookup"><span data-stu-id="ec96a-109">Network Element</span></span></th>
<th><span data-ttu-id="ec96a-110">所需列</span><span class="sxs-lookup"><span data-stu-id="ec96a-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec96a-111"><strong>无线访问点</strong></span><span class="sxs-lookup"><span data-stu-id="ec96a-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="ec96a-112">&lt;BSSID&gt;、&lt;说明&gt;、&lt;位置&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="ec96a-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="ec96a-113">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;城市&gt;、&lt;州&gt;、&lt;邮政编码&gt;、&lt;国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="ec96a-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec96a-114"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="ec96a-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="ec96a-115">&lt;子&gt;网&lt;、&gt;说明&lt;、&gt;位置&lt;、&gt;公司&lt;名称&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="ec96a-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="ec96a-116">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;城市&gt;、&lt;州&gt;、&lt;邮政编码&gt;、&lt;国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="ec96a-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec96a-117"><strong>端口</strong></span><span class="sxs-lookup"><span data-stu-id="ec96a-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="ec96a-118">&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;、&lt;说明&gt;、&lt;位置&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix,.。。</span><span class="sxs-lookup"><span data-stu-id="ec96a-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="ec96a-119">...&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;州&gt;、&lt;邮政编码&gt;、&lt;国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="ec96a-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec96a-120"><strong>交换机</strong></span><span class="sxs-lookup"><span data-stu-id="ec96a-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="ec96a-121">&lt;ChassisID&gt;、&lt;说明&gt;、&lt;位置&gt;、&lt;公司&gt;名称&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</span><span class="sxs-lookup"><span data-stu-id="ec96a-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="ec96a-122">...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;城市&gt;、&lt;州&gt;、&lt;邮政编码&gt;、&lt;国家/地区&gt;</span><span class="sxs-lookup"><span data-stu-id="ec96a-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ec96a-123">如果未填充位置数据库，并且位置策略中的“所需位置”\*\*\*\* 设置为“是”\*\*\*\* 或“免责声明”\*\*\*\*，客户端将提示用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="ec96a-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="ec96a-124">有关填充位置数据库的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="ec96a-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="ec96a-125">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="ec96a-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="ec96a-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="ec96a-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="ec96a-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="ec96a-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="ec96a-128">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="ec96a-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="ec96a-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="ec96a-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="ec96a-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="ec96a-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="ec96a-131">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="ec96a-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="ec96a-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="ec96a-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="ec96a-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="ec96a-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="ec96a-134">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="ec96a-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="ec96a-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="ec96a-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="ec96a-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="ec96a-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="ec96a-137">将网络元素添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="ec96a-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="ec96a-138">运行以下 cmdlet，以将子网位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="ec96a-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="ec96a-p103">对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：</span><span class="sxs-lookup"><span data-stu-id="ec96a-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="ec96a-142">另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。</span><span class="sxs-lookup"><span data-stu-id="ec96a-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="ec96a-143">运行以下 cmdlet，以将无线位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="ec96a-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="ec96a-144">另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。</span><span class="sxs-lookup"><span data-stu-id="ec96a-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="ec96a-145">运行以下 cmdlet，以将交换机位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="ec96a-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="ec96a-146">另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。</span><span class="sxs-lookup"><span data-stu-id="ec96a-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="ec96a-147">运行以下 cmdlet，以将端口位置添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="ec96a-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="ec96a-p104">PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="ec96a-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="ec96a-150">另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。</span><span class="sxs-lookup"><span data-stu-id="ec96a-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

