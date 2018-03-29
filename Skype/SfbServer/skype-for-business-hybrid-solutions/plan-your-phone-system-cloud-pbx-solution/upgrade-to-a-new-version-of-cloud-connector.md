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
ms.custom: Strat_SB_Hybrid
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 了解如何升级你的云连接器版本部署。
ms.openlocfilehash: 0538b5d43c6e11aa11f7d265e43eb5f283e2b74e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升级到新版本的云连接器
 
了解如何升级你的云连接器版本部署。
  
如果已设置联机管理租户帐户并启用自动更新，则现有 Skype for Business 云连接器版本的部署将根据你的自动更新时间窗口配置自动升级到较新版本。你也可以执行手动升级。 
  
云连接器版版本 1.4.1 以及更高版本，默认情况下执行自动更新。 如果您想手动升级到最新版本 (2.1)，请参阅本主题后面部分中[升级到新版本单个站点](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)。
  
自动更新要求云连接器服务正在运行。 以下步骤介绍了自动更新过程：
  
- 自动更新过程将根据你为自动更新配置的计划运行。
    
- 操作系统更新任务
    
  - 检查并下载到所有云接口虚拟机的操作系统更新。 
    
  - 安装并更新所有云连接器 Vm，然后重新启动。
    
  - 云的连接器虚拟机重新启动后，检查是否需要另一个重新启动。
    
  - 在云连接器 Vm 之后成功修补完毕，云连接器宿主计算机重复此过程。
    
  - 云中连接器宿主计算机成功启动后，任何未完成的操作系统更新任务完成。
    
- 云接头更新任务
    
  - 从下载站点下载版本文件并检查。
    
  - 下载新版本的 .msi 文件。 
    
  - 卸载旧的 msi 文件;安装新的 msi 文件。
    
  - 下载新版的 Skype 业务比特数。
    
  - 通过调用 Register-CcAppliance 注册设备。
    
  - 安装新的云连接器版本。
    
  - 排出旧设备，并将网络连接切换到新设备。
    
> [!NOTE]
>  当云接头更新到新版本时，可能不会更新云连接器 cmdlet。 可以这样做，例如，如果一个 PowerShell 窗口处于打开状态时进行自动更新。 要加载更新后的 cmdlet，请执行以下步骤之一： > 关闭 PowerShell 云接头装置和然后重新打开 PowerShell。 > 也可以运行导入模块 CloudConnector 的力。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>将单个站点升级到新版本
<a name="BKMK_Upgrade"> </a>

如果在要升级的网站只有一个设备，请执行以下操作：
  
1. 卸载现有的云连接器版本中**控制面板\>程序\>程序和功能**。
    
2. 安装最新版本的 CloudConnector.msi 从[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。
    
3. 请确认你具有要安装的版本对应的 CloudConnector.ini 文件，并且已更新环境所需的所有值。 不能使用上一个版本中的 .ini 文件。 如果您要升级云连接器，请参考主题[准备云接头装置](prepare-your-cloud-connector-appliance.md)并确保站点名和 EnableReferSupport 设置为正确的值在 CloudConnector.ini 文件中。
    
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
  
如果您想要更新域管理员、 虚拟机管理员、 安全模式管理员和组织管理员凭据，您可以运行该 cmdlet 与要重置所有凭据的_UpdateAllCredentials_参数：
  
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

按照升级单个站点的步骤，每次升级部署中的一个站点。 确认和[验证您的云连接器部署](validate-your-cloud-connector-deployment.md)后升级每个站点。
  

