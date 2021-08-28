---
title: 在数据库中配置位置Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 配置、填充和发布 E9-1-1 位置Skype for Business Server 企业语音。
ms.openlocfilehash: 0eb2fd8e09c09688cf8c8282b35328ca7eb1761b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597736"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>在数据库中配置位置Skype for Business Server
 
配置、填充和发布 E9-1-1 位置Skype for Business Server 企业语音。 
  
为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。 
  
若要配置位置数据库，请执行以下任务：
  
- 使用网络元素到位置的映射填充数据库。 如果使用 ELIN 网关中的紧急 (标识号) ELIN，则需要在字段中包括 \<CompanyName\> ELIN。
    
    如果未填充位置数据库，并且位置策略中的“所需位置”设置为“是”或“免责声明”，客户端将提示用户手动输入位置。
    
- 根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。
    
- 发布更新的数据库。
    
## <a name="populate-the-location-database"></a>填充位置数据库

要在网络中自动定位客户端，首先需要使用网络线路映射 填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。可以使用子网、无线访问点、交换机和端口来定义线路映射。
  
可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。
  
如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。
  
|**网络元素**|**所需列**|
|:-----|:-----|
|**无线访问点** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**开关** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>将网络元素添加到位置数据库

1. 运行以下 cmdlet，以将子网位置添加到位置数据库。
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 运行以下 cmdlet，以将无线位置添加到位置数据库。
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 运行以下 cmdlet，以将交换机位置添加到位置数据库。
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 运行以下 cmdlet，以将端口位置添加到位置数据库
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName
    
   另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>验证地址

### <a name="to-validate-addresses-located-in-the-location-database"></a>验证位于位置数据库中的地址

1.  启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行以下 cmdlet 以配置紧急服务提供商连接。
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 运行以下 cmdlet 以验证位置数据库中的地址。
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   您还可以使用 **Test-CsLisCivicAddress cmdlet** 验证单个地址。
    
## <a name="publish-the-location-database"></a>发布位置数据库

添加到位置数据库的新位置在发布之前对客户端不可用。
  
如果使用紧急位置标识号 (ELIN) 网关，则还需要将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。 PSTN 运营商可能要求对 ELIN 记录使用特定格式。 有关详细信息，请与 PSTN 运营商联系。 可以从位置信息服务数据库中导出记录，并设置这些记录的格式。
  
### <a name="to-publish-the-location-database"></a>发布位置数据库

-  启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
- 运行以下 cmdlet 以发布位置数据库。
    
  ```powershell
  Publish-CsLisConfiguration
  ```


