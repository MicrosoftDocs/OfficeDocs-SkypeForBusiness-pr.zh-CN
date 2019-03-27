---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcAppliance cmdlet 用于在主机服务器上安装 Skype for Business 云连接器版本设备，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。
ms.openlocfilehash: 8f1a8b7d99a555006c1d69ee52f2403e9bf0a874
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880212"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Install-CcAppliance cmdlet 用于在主机服务器上安装 Skype for Business 云连接器版本设备，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例在主机服务器上安装新的云连接器装置：
  
```
Install-CcAppliance
```

### <a name="example-2"></a>示例 2

下面的示例升级到最新版本的云连接器：
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>示例 3

下面的示例删除所有缓存的主机服务器上，提示用户指定再次，所有的凭据信息的云连接器凭据，然后安装云连接器：
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>示例 4

以下示例显示 PowerShell 控制台中的所有部署步骤：
  
```
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 参数仅用于故障排除。
  
### <a name="example-5"></a>示例 5

以下示例在主机服务器上为每个部署步骤生成配置文件。 配置文件保存到\<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig 主机服务器上的文件夹：
  
```
Install-CcAppliance -PrepareOnly
```

要确定设备根，请运行 Get-CcApplianceDirectory cmdlet。 
  
### <a name="example-6"></a>示例 6

在以下示例中，云连接器运行部署步骤 1、2 和 3 来创建虚拟交换机、创建 AD 虚拟机以及在 AD 服务器上安装域服务。如果已执行某步骤，则跳过该步骤：
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 参数必须与 Steps 参数一起使用。
  
> [!NOTE]
> Steps 参数仅用于故障排除目的。 请勿使用此参数来部署设备或升级正在使用的设备。 
  
要确定部署步骤，请运行以下命令：
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

安装 CcAppliance cmdlet 用于将云连接器部署到新装置或升级到最新版本的现有设备。
  
如果你有新设备，请务必先阅读“为云连接器准备你的环境”，运行 Register-CcAppliance cmdlet 来注册该设备，然后运行 Install-CcAppliance cmdlet。 有关详细信息，请参阅[Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)和[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果您具有云连接器的现有部署并且要升级，请按照[升级到云连接符的新版本](upgrade-to-a-new-version-of-cloud-connector.md)中的说明。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必需**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> | 为每个部署步骤生成配置文件。此参数仅用于故障排除。 <br/> |
|ShowStepsOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |仅显示部署步骤名称。此参数仅用于故障排除。  <br/> |
|SkipExistingObjects  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |此参数必须与 Steps 参数一起使用。此参数仅用于故障排除。  <br/> |
|步骤  <br/> |可选  <br/> |System.Array  <br/> |运行部署步骤。此参数仅用于故障排除。  <br/> |
|升级  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |将现有云连接器升级到最新版本。  <br/> |
|UpdateAllCredentials  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |在缓存中删除所有云连接器凭据。 提示用户为安装指定新凭据信息。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Install-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

