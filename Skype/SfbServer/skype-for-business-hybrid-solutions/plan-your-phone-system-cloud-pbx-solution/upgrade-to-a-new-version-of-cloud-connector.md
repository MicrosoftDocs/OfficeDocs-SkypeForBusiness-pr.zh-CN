---
title: 升级至新版本的云连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 了解如何升级你的云连接器版本部署。
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359288"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升级至新版本的云连接器

> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。
 
了解如何升级你的云连接器版本部署。
  
如果已设置了联机管理租户帐户并启用了自动更新，则现有的 Skype for Business 云连接器版本部署将根据您的自动更新时间窗口配置自动升级到较新的版本。 您还可以执行手动升级。 
  
云连接器版本1.4.1 和更高版本在默认情况下将执行自动更新。 如果要 (2.1) 手动升级到最新版本，请参阅本主题后面的将 [单个网站升级到新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 。
  
自动更新要求云连接器服务正在运行。 以下步骤介绍了自动更新的过程：
  
- 自动更新过程将根据您为自动更新配置的计划运行。
    
- 操作系统更新任务
    
  - 检查并下载所有云连接器虚拟机的操作系统更新。 
    
  - 逐个安装和更新所有云连接器虚拟机并重新启动。
    
  - 云连接器虚拟机重新启动后，检查是否需要再次重新启动。
    
  - 成功修补云连接器虚拟机后，请对云连接器主机进行重复此过程。
    
  - 云连接器主机成功启动后，将完成任何未完成的操作系统更新任务。
    
- 云连接器更新任务
    
  - 从下载网站下载并检查版本文件。
    
  - 下载新的版本 .msi 文件。 
    
  - 卸载旧的 msi 文件;安装新的 msi 文件。
    
  - 下载新版本的 Skype for Business bits。
    
  - 通过调用 Register-ccappliance 注册设备。
    
  - 安装新的云连接器版本。
    
  - 排出旧设备，并切换到新设备的网络连接。
    
> [!NOTE]
>  当云连接器更新到新版本时，可能不会更新云连接器 cmdlet。 例如，如果在自动更新发生时 PowerShell 窗口保持打开状态，则会发生这种情况。 若要加载更新的 cmdlet，您可以执行以下任一步骤： > 在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。 > 或者，您可以运行 Import-Module Cloudconnector.ini-Force。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>将单个网站升级到新版本
<a name="BKMK_Upgrade"> </a>

如果要升级的站点中只有一台设备，请执行以下操作：
  
1. 在 "控制面板" 中卸载现有的云连接器版本。 ** \> 程序 \> 和功能**。
    
2. 从安装 CloudConnector.msi 的新版本 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。
    
3. 确认您具有要安装的版本的 CloudConnector.ini 文件，并且已更新环境所需的所有值。 您不能使用以前版本中的 .ini 文件。 如果要升级云连接器，请参阅 " [准备云连接器" 设备](prepare-your-cloud-connector-appliance.md) 一主题，确保将 "SiteName" 和 "EnableReferSupport" 设置为 "CloudConnector.ini" 文件中的正确值。
    
4. 以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以注册当前设备：
    
   ```powershell
   Register-CcAppliance
   ```

5. 运行以下 cmdlet 以下载最新版本：
    
   ```powershell
   Start-CcDownload
   ```

6. 运行以下 cmdlet 以开始安装： 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 运行以下 cmdlet 以激活新部署并关闭以前的版本：
    
   ```powershell
   Switch-CcVersion
   ```

如果站点中有多个设备，请按照上述步骤逐个升级每个设备。
  
如果要更新域管理员、虚拟机管理员、安全模式管理员和租户管理员凭据，可以使用  _UpdateAllCredentials_ 参数运行 cmdlet 来重置所有凭据：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

然后，在开始升级到新版本时，将会提升，以输入新的凭据。 
  
如果您只想重置租户管理员凭据，请运行以下 cmdlet：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>将多个网站升级到新版本
<a name="BKMK_Upgrade"> </a>

按照升级单个网站的步骤操作，为部署中的每个网站一次升级一个网站。 在升级每个网站后，请确保并 [验证你的云连接器部署](validate-your-cloud-connector-deployment.md) 。
  

