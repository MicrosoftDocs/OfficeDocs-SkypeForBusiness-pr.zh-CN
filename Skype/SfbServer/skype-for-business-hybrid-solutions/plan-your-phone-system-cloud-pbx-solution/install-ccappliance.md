---
title: 安装 CcAppliance
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
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a>安装 CcAppliance
 
Install-CcAppliance cmdlet 用于在主机服务器上安装 Skype for Business 云连接器版本设备，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

下面的示例将新云接头装置安装在主机服务器上：
  
```
Install-CcAppliance
```

### <a name="example-2"></a>示例 2

下面的示例将云连接器升级到最新版本：
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>示例 3

下面的示例移除所有云连接器凭据缓存在主机服务器上，会提示用户指定所有凭据信息，，然后再安装云连接器：
  
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

以下示例在主机服务器上为每个部署步骤生成配置文件。 配置文件保存到\<ApplianceRoot\>\Instances\\< 版本\>-default\ExportedConfig 的主机服务器上的文件夹：
  
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
  
安装 CcAppliance ShowStepsOnly
  
## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

安装 CcAppliance cmdlet 用于部署到新装置的云连接器或将现有设备升级到最新版本。
  
如果你有新设备，请务必先阅读“为云连接器准备你的环境”，运行 Register-CcAppliance cmdlet 来注册该设备，然后运行 Install-CcAppliance cmdlet。 有关详细信息，请参阅[部署单个站点在云接头](deploy-a-single-site-in-cloud-connector.md)和[部署云连接器中的多个站点](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果您有云连接器的现有部署，并且您想要升级，请按照在[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)中的说明进行操作。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**必填**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> | 为每个部署步骤生成配置文件。此参数仅用于故障排除。 <br/> |
|ShowStepsOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |仅显示部署步骤名称。此参数仅用于故障排除。  <br/> |
|SkipExistingObjects  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |此参数必须与 Steps 参数一起使用。此参数仅用于故障排除。  <br/> |
|步骤  <br/> |可选  <br/> |System.Array  <br/> |运行部署步骤。此参数仅用于故障排除。  <br/> |
|升级  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |将现有云连接器升级到最新版本。  <br/> |
|UpdateAllCredentials  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |删除所有云连接器凭据缓存中。 提示用户为安装指定新凭据信息。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。Install-CcAppliance cmdlet 不接受主线输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[将发布 CcAppliance](publish-ccappliance.md)
  
[注册 CcAppliance](register-ccappliance.md)
  
[取消注册 CcAppliance](unregister-ccappliance.md)
  
[卸载-CcAppliance](uninstall-ccappliance.md)
  

