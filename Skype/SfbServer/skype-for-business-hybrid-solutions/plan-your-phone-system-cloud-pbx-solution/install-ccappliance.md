---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 此 Install-CcAppliance cmdlet 在主机服务器上Skype for Business 云连接器版本服务器，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343176"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
此 Install-CcAppliance cmdlet 在主机服务器上Skype for Business 云连接器版本服务器，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>示例
<a name="Examples"> </a>

### <a name="example-1"></a>示例 1

以下示例在主机服务器上安装新的云连接器设备：
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>示例 2

以下示例将云连接器升级到最新版本：
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>示例 3

以下示例删除主机服务器上缓存的所有云连接器凭据，提示用户重新指定所有凭据信息，然后安装云连接器：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>示例 4

以下示例显示 PowerShell 控制台中的所有部署步骤：
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 参数仅适用于疑难解答。
  
### <a name="example-5"></a>示例 5

以下示例为主机服务器上每个部署步骤生成配置文件。 配置文件保存到主机服务器的 \<ApplianceRoot\> \Instances \\<Version \> -default\ExportedConfig 文件夹中：
  
```powershell
Install-CcAppliance -PrepareOnly
```

若要确定设备根目录，请运行 Get-CcApplianceDirectory cmdlet。 
  
### <a name="example-6"></a>示例 6

在下面的示例中，云连接器运行部署步骤 1、2 和 3，以创建虚拟交换机、创建 AD 虚拟机，以及安装 AD 服务器上域服务。 如果已执行该步骤，则跳过该步骤：
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 参数必须与 Steps 参数一起使用。
  
> [!NOTE]
> Steps 参数仅供疑难解答。 请勿使用此参数部署设备或升级运行中的设备。 
  
若要确定部署的步骤，请运行以下命令：
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>详细说明
<a name="DetailedDescription"> </a>

Install-CcAppliance cmdlet 用于将云连接器部署到新设备或将现有设备升级到最新版本。
  
如果你有新设备，请务必先阅读为云连接器准备环境，运行 Register-CcAppliance cmdlet 注册该设备，然后运行 Install-CcAppliance cmdlet。 有关详细信息，请参阅在云 [连接器](deploy-a-single-site-in-cloud-connector.md) 中部署单个站点和在云连接器 [中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果你有云连接器的现有部署，并且想要升级，请按照升级到云连接器的 [新版本中的说明操作](upgrade-to-a-new-version-of-cloud-connector.md)。
  
## <a name="parameters"></a>参数
<a name="DetailedDescription"> </a>

|**参数**|**Required**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> | 生成每个部署步骤的配置文件。 此参数仅适用于疑难解答。 <br/> |
|ShowStepsOnly  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |仅显示部署步骤名称。 此参数仅适用于疑难解答。  <br/> |
|SkipExistingObjects  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |此参数必须与 Steps 参数一起使用。 此参数仅适用于疑难解答。  <br/> |
|步骤  <br/> |可选  <br/> |System.Array  <br/> |运行部署步骤。 此参数仅适用于疑难解答。  <br/> |
|升级  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |将现有云连接器升级到最新版本。  <br/> |
|UpdateAllCredentials  <br/> |可选  <br/> |System.Management.Automation.SwitchParameter  <br/> |删除缓存中所有的云连接器凭据。 提示用户为安装指定新的凭据信息。  <br/> |
   
## <a name="input-types"></a>输入类型
<a name="InputTypes"> </a>

无。 Install-CcAppliance cmdlet 不接受通过管道的输入。
  
## <a name="return-types"></a>返回类型
<a name="ReturnTypes"> </a>

无
  
## <a name="see-also"></a>另请参阅
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

