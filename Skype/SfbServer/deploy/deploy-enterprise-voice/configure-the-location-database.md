---
title: 在 Skype for Business Server 中配置位置数据库
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 配置、 填充和业务 Server 企业语音中 Skype 发布 E9-1-1 位置数据库。
ms.openlocfilehash: e57f9ba299abad613df2f4c54ae9ecbbea748f9a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885497"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="eebe8-103">在 Skype for Business Server 中配置位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="eebe8-104">配置、 填充和业务 Server 企业语音中 Skype 发布 E9-1-1 位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="eebe8-105">为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="eebe8-106">要配置位置数据库，请执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="eebe8-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="eebe8-107">使用网络元素到位置的映射填充数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="eebe8-108">如果您使用的紧急位置识别号码 (ELIN) 网关，您需要包括在 ELIN \<CompanyName\>字段。</span><span class="sxs-lookup"><span data-stu-id="eebe8-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="eebe8-109">如果未填充位置数据库，并且位置策略中的“所需位置”\*\*\*\* 设置为“是”\*\*\*\* 或“免责声明”\*\*\*\*，客户端将提示用户手动输入位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="eebe8-110">根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。</span><span class="sxs-lookup"><span data-stu-id="eebe8-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="eebe8-111">发布更新的数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="eebe8-112">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-112">Populate the location database</span></span>

<span data-ttu-id="eebe8-p102">要在网络中自动定位客户端，首先需要使用网络线路映射填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。</span><span class="sxs-lookup"><span data-stu-id="eebe8-p102">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="eebe8-115">可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。</span><span class="sxs-lookup"><span data-stu-id="eebe8-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="eebe8-p103">如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”\*\*\*\* 字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="eebe8-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="eebe8-118">**网络元素**</span><span class="sxs-lookup"><span data-stu-id="eebe8-118">**Network Element**</span></span>|<span data-ttu-id="eebe8-119">**所需列**</span><span class="sxs-lookup"><span data-stu-id="eebe8-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eebe8-120">**无线访问点**</span><span class="sxs-lookup"><span data-stu-id="eebe8-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="eebe8-121">\<BSSID\>，\<说明\>，\<位置\>，\<CompanyName\>，\<HouseNumber\>，\<HouseNumberSuffix\>，\<PreDirectional\>，...</span><span class="sxs-lookup"><span data-stu-id="eebe8-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="eebe8-122">...\<StreetName\>，\<StreetSuffix\>，\<PostDirectional\>，\<市/县\>，\<状态\>，\<PostalCode\>，\<国家/地区\></span><span class="sxs-lookup"><span data-stu-id="eebe8-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="eebe8-123">**子网**</span><span class="sxs-lookup"><span data-stu-id="eebe8-123">**Subnet**</span></span> <br/> |<span data-ttu-id="eebe8-124">\<子网\>，\<说明\>，\<位置\>，\<CompanyName\>，\<HouseNumber\>，\<HouseNumberSuffix\>，\<PreDirectional\>，...</span><span class="sxs-lookup"><span data-stu-id="eebe8-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="eebe8-125">...\<StreetName\>，\<StreetSuffix\>，\<PostDirectional\>，\<市/县\>，\<状态\>，\<PostalCode\>，\<国家/地区\></span><span class="sxs-lookup"><span data-stu-id="eebe8-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="eebe8-126">**端口**</span><span class="sxs-lookup"><span data-stu-id="eebe8-126">**Port**</span></span> <br/> |<span data-ttu-id="eebe8-127">\<机架 Id\>，\<PortIDSubType\>，\<PortID\>，\<说明\>，\<位置\>，\<CompanyName\>，\<HouseNumber\>，\<HouseNumberSuffix\>，...</span><span class="sxs-lookup"><span data-stu-id="eebe8-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="eebe8-128">...\<PreDirectional\>，\<StreetName\>，\<StreetSuffix\>，\<PostDirectional\>，\<市/县\>，\<状态\>，\<PostalCode\>，\<国家/地区\></span><span class="sxs-lookup"><span data-stu-id="eebe8-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="eebe8-129">**交换机**</span><span class="sxs-lookup"><span data-stu-id="eebe8-129">**Switch**</span></span> <br/> |<span data-ttu-id="eebe8-130">\<机架 Id\>，\<说明\>，\<位置\>，\<CompanyName\>，\<HouseNumber\>，\<HouseNumberSuffix\>，\<PreDirectional\>，...</span><span class="sxs-lookup"><span data-stu-id="eebe8-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="eebe8-131">...\<StreetName\>，\<StreetSuffix\>，\<PostDirectional\>，\<市/县\>，\<状态\>，\<PostalCode\>，\<国家/地区\></span><span class="sxs-lookup"><span data-stu-id="eebe8-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="eebe8-132">将网络元素添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="eebe8-133">运行以下 cmdlet，以将子网位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="eebe8-p104">对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：</span><span class="sxs-lookup"><span data-stu-id="eebe8-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="eebe8-137">另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="eebe8-138">运行以下 cmdlet，以将无线位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="eebe8-139">另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="eebe8-140">运行以下 cmdlet，以将交换机位置添加到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="eebe8-141">另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="eebe8-142">运行以下 cmdlet，以将端口位置添加到位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="eebe8-p105">PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="eebe8-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="eebe8-145">另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="eebe8-146">验证地址</span><span class="sxs-lookup"><span data-stu-id="eebe8-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="eebe8-147">验证位于位置数据库中的地址</span><span class="sxs-lookup"><span data-stu-id="eebe8-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="eebe8-148">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="eebe8-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="eebe8-149">运行以下 cmdlet 配置紧急服务提供商连接。</span><span class="sxs-lookup"><span data-stu-id="eebe8-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="eebe8-150">运行以下 cmdlet 验证位置数据库中的地址。</span><span class="sxs-lookup"><span data-stu-id="eebe8-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="eebe8-151">您可以使用**Test-csliscivicaddress** cmdlet 验证单个地址。</span><span class="sxs-lookup"><span data-stu-id="eebe8-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="eebe8-152">发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-152">Publish the location database</span></span>

<span data-ttu-id="eebe8-153">只有在添加到位置数据库的新位置发布后，客户端才能使用这些位置。</span><span class="sxs-lookup"><span data-stu-id="eebe8-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="eebe8-154">如果使用紧急位置标识号 (ELIN) 网关，还需要将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="eebe8-155">PSTN 运营商可能需要特定格式的 ELIN 记录。</span><span class="sxs-lookup"><span data-stu-id="eebe8-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="eebe8-156">请联系 PSTN 运营商了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="eebe8-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="eebe8-157">可以从位置信息服务数据库导出记录，并设置它们所需的格式。</span><span class="sxs-lookup"><span data-stu-id="eebe8-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="eebe8-158">发布位置数据库</span><span class="sxs-lookup"><span data-stu-id="eebe8-158">To publish the location database</span></span>

-  <span data-ttu-id="eebe8-159">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="eebe8-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="eebe8-160">运行以下 cmdlet 发布位置数据库。</span><span class="sxs-lookup"><span data-stu-id="eebe8-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


