---
title: 升级到新版本的云连接器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 了解如何升级你的云连接器版本部署。
ms.openlocfilehash: c0946cf26181df81327412c2dc0efc227b5a5586
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370625"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升级到新版本的云连接器
 
了解如何升级你的云连接器版本部署。
  
如果已设置联机管理租户帐户并启用自动更新，则现有 Skype for Business 云连接器版本的部署将根据你的自动更新时间窗口配置自动升级到较新版本。你也可以执行手动升级。 
  
云连接器 Edition 版本 1.4.1 和更高版本默认情况下执行自动更新。 如果您想要手动升级到最新版本 (2.1)，请参阅本主题后面的[升级到新版本的单个网站](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)。
  
自动更新需要云连接器服务正在运行。 以下步骤介绍了自动更新过程：
  
- 自动更新过程将根据你为自动更新配置的计划运行。
    
- 操作系统更新任务
    
  - 检查并将操作系统更新下载到所有云连接器 Vm。 
    
  - 安装和更新所有云连接器 Vm 逐个并重新启动。
    
  - 云连接器 Vm 重新启动后，查看是否需要其他重新启动。
    
  - 后云连接器 Vm 具有已成功修复，为云连接器主机计算机重复此过程。
    
  - 云连接器主机上成功启动后，任何未处理的操作系统更新任务完成。
    
- 云连接器更新任务
    
  - 从下载站点下载版本文件并检查。
    
  - 下载新版本的 .msi 文件。 
    
  - 卸载旧的 msi 文件;安装新的 msi 文件。
    
  - 下载新版本的 Skype 业务位。
    
  - 通过调用 Register-CcAppliance 注册设备。
    
  - 安装新的云连接器版本。
    
  - 排出旧设备，并将网络连接切换到新设备。
    
> [!NOTE]
>  当云连接器更新为新版本时，可能不会更新云连接器 cmdlet。 可以这样做，例如，如果在 PowerShell 窗口处于打开状态时自动更新，发生此事件。 若要加载的更新的 cmdlet，可以执行以下步骤之一： > 云连接器装置和然后重新打开 PowerShell。 关闭 PowerShell > 或者，您可以运行导入模块 CloudConnector-Force。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>将单个站点升级到新版本
<a name="BKMK_Upgrade"> </a>

如果要升级的站点中只有一个设备，请执行以下操作：
  
1. 卸载中的现有云连接器版本**Control Panel\>程序\>程序和功能**。
    
2. 安装新版本的 CloudConnector.msi 从[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。
    
3. 请确认你具有要安装的版本对应的 CloudConnector.ini 文件，并且已更新环境所需的所有值。 不能使用上一个版本中的 .ini 文件。 如果要升级云连接器，请参考主题[准备云连接器 appliance](prepare-your-cloud-connector-appliance.md) ，并确保 SiteName 和 EnableReferSupport 设置为正确值 CloudConnector.ini 文件中。
    
4. 以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以注册当前设备：
    
   ```
   Register-CcAppliance
   ```

5. 运行以下 cmdlet 以下载最新版本：
    
   ```
   Start-CcDownload
   ```

6. 运行以下 cmdlet 以开始安装： 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. 运行以下 cmdlet 以激活新部署并禁用上一版本：
    
   ```
   Switch-CcVersion
   ```

如果站点中有多个设备，请按照上述步骤逐个升级各设备。
  
如果您想要更新域管理员、 虚拟机管理员、 安全模式的管理员和租户管理员凭据，您可以使用_UpdateAllCredentials_参数来重置所有的凭据运行此 cmdlet:
  
```
Install-CcAppliance -UpdateAllCredentials
```

然后，在开始升级到新版本时，系统会提示你输入新凭据。 
  
如果只想重置租户管理员凭据，请运行以下 cmdlet：
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>将多个站点升级到新版本
<a name="BKMK_Upgrade"> </a>

按照升级单个站点的步骤，每次升级部署中的一个站点。升级每个站点后，请确保[Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md)。
  

