---
title: 在 Skype for Business 服务器中配置位置数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 在 Skype for Business Server Enterprise Voice 中配置、填充和发布 E9-1-1 位置数据库。
ms.openlocfilehash: 5aad449d8d286fb4bd71373be33baea9cbb2c8f3
ms.sourcegitcommit: 5e6eb8286bd5eb318a901e42235e91a58946c3a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "38038701"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置位置数据库
 
在 Skype for Business Server Enterprise Voice 中配置、填充和发布 E9-1-1 位置数据库。 
  
为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。 
  
要配置位置数据库，请执行下列任务：
  
- 使用网络元素到位置的映射填充数据库。 如果您使用紧急位置识别号码（ELIN）网关，则需要在 " \<公司名称\> " 字段中包含 ELIN。
    
    如果未填充位置数据库，并且位置策略中的“所需位置”**** 设置为“是”**** 或“免责声明”****，客户端将提示用户手动输入位置。
    
- 根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。
    
- 发布更新的数据库。
    
## <a name="populate-the-location-database"></a>填充位置数据库

要在网络中自动定位客户端，首先需要使用网络线路映射填充位置数据库，网络线路映射会将网络元素映射到市政（即，街道）地址。 可以使用子网、无线访问点、交换机和端口来定义线路映射。
  
可以分别将地址添加到位置数据库中，也可以使用包含下表所述的列格式的 CSV 文件批量添加。
  
如果您使用紧急位置标识号 (ELIN) 网关，包括每个位置“CompanyName”**** 字段中的 ELIN。可以包括每个位置的多个 ELIN，每个以逗号分隔。
  
|**网络元素**|**所需列**|
|:-----|:-----|
|**无线访问点** <br/> |\<BSSID\>、\<说明\>、\<位置\>、\<公司\>名称\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<城市\>、\<州\>、\<邮政编码\>、\<国家/地区\>  <br/> |
|**Subnet** <br/> |\<子\>网\<、\>说明\<、\>位置\<、\>公司\<名称\>、\<HouseNumber\>、\<HouseNumberSuffix\>、PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<城市\>、\<州\>、\<邮政编码\>、\<国家/地区\>  <br/> |
|**端口** <br/> |\<ChassisID\>、\<PortIDSubType\>、\<PortID\>、\<说明\>、\<位置\>、\<公司\>名称\<、\>HouseNumber\<、\>HouseNumberSuffix,.。。  <br/> ...\<PreDirectional\>、\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<City\>、\<州\>、\<邮政编码\>、\<国家/地区\>  <br/> |
|**交换机** <br/> |\<ChassisID\>、\<说明\>、\<位置\>、\<公司\>名称\<、\>HouseNumber\<、\>HouseNumberSuffix\<、\>PreDirectional,.。。  <br/> ...\<StreetName\>、\<StreetSuffix\>、\<PostDirectional\>、\<城市\>、\<州\>、\<邮政编码\>、\<国家/地区\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>将网络元素添加到位置数据库

1. 运行以下 cmdlet，以将子网位置添加到位置数据库。
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    对于 ELIN 网关，将 ELIN 放在 CompanyName 字段中。可以包括多个 ELIN。例如：
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    另外，可以运行以下 cmdlet，并使用名为“subnets.csv”的文件批量更新子网位置。
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 运行以下 cmdlet，以将无线位置添加到位置数据库。
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   另外，可以运行以下 cmdlet，并使用名为“waps.csv”的 文件批量更新无线位置。
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 运行以下 cmdlet，以将交换机位置添加到位置数据库。
    
   ```
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   另外，可以运行以下 cmdlet，并使用名为“switches.csv”的文件批量更新交换机位置。
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 运行以下 cmdlet，以将端口位置添加到位置数据库
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType 的默认值为 LocallyAssigned。还可以将其设置为 InterfaceAlias 或 InterfaceName
    
   另外，可以运行以下 cmdlet，并使用名为“ports.csv”的文件批量更新端口位置。
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>验证地址

### <a name="to-validate-addresses-located-in-the-location-database"></a>验证位于位置数据库中的地址

1.  启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 配置紧急服务提供商连接。
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 运行以下 cmdlet 验证位置数据库中的地址。
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   还可以使用 **Test-CsLisCivicAddress** cmdlet 验证单个地址。
    
## <a name="publish-the-location-database"></a>发布位置数据库

只有在添加到位置数据库的新位置发布后，客户端才能使用这些位置。
  
如果使用紧急位置标识号 (ELIN) 网关，还需要将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。 PSTN 运营商可能需要特定格式的 ELIN 记录。 请联系 PSTN 运营商了解详细信息。 你可以从位置信息服务数据库导出记录，并根据需要设置其格式。
  
### <a name="to-publish-the-location-database"></a>发布位置数据库

-  启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
- 运行以下 cmdlet 发布位置数据库。
    
  ```
  Publish-CsLisConfiguration
  ```


