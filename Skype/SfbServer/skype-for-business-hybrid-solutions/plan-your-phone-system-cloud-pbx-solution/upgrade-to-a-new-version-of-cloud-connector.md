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
description: 了解如何升级云连接器版本部署。
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109128"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升级至新版本的云连接器

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)
 
了解如何升级云连接器版本部署。
  
如果已设置联机管理租户帐户并启用自动更新，则 Skype for Business 云连接器版本的现有部署将自动升级到较新版本，根据自动更新时间窗口配置。 您也可以执行手动升级。 
  
默认情况下，云连接器版本 1.4.1 版和更高版本执行自动更新。 如果要手动升级到最新版本 (2.1) ，请参阅本主题稍后将单个网站升级到新版本。 [](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)
  
自动更新要求云连接器服务正在运行。 以下步骤介绍了自动更新过程：
  
- 自动更新过程将按照为自动更新配置的计划运行。
    
- 操作系统更新任务
    
  - 检查操作系统更新并下载到所有云连接器 VM。 
    
  - 一个接一个地安装并更新所有云连接器 VM，然后重新启动。
    
  - 在云连接器 VM 重启后，请检查以查看是否还需要重新启动。
    
  - 成功修补云连接器 VM 后，对云连接器主机重复此过程。
    
  - 云连接器主机成功启动后，任何未完成的操作系统更新任务都已完成。
    
- 云连接器更新任务
    
  - 从下载网站下载并检查版本文件。
    
  - 下载新版本的 .msi 文件。 
    
  - 卸载旧的 msi 文件;安装新的 msi 文件。
    
  - 下载新版本的 Skype for Business bits。
    
  - 通过调用 Register-CcAppliance 注册设备。
    
  - 安装新的云连接器版本。
    
  - 排出旧设备，将网络连接切换到新设备。
    
> [!NOTE]
>  当云连接器更新到新内部版本时，可能无法更新云连接器 cmdlet。 例如，如果 PowerShell 窗口在自动更新发生时是打开的，则可能会发生这种情况。 若要加载更新的 cmdlet，可以执行下列任一步骤：> 关闭云连接器设备的 PowerShell，然后重新打开 PowerShell.> 或者，你可以运行 Import-Module CloudConnector -Force。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>将单个网站升级到新版本
<a name="BKMK_Upgrade"> </a>

如果站点中只有一个要升级的设备，请执行下列操作：
  
1. 卸载控制面板程序程序和功能中的现有云 **\> \> 连接器版本**。
    
2. 从 安装新版本的 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) CloudConnector.msi。
    
3. 确认你具有要CloudConnector.ini的版本的文件，并且已更新环境的所有必需值。 不能使用以前版本中的 .ini 文件。 如果要升级云连接器，请参阅主题准备云连接器设备，并确保[](prepare-your-cloud-connector-appliance.md)在云连接器文件中将 SiteName 和 EnableReferSupport 设置为正确的CloudConnector.ini值。
    
4. 以管理员角色启动 PowerShell 控制台并运行以下 cmdlet 以注册当前设备：
    
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

如果站点中存在多个设备，请按照上述步骤分别升级每台设备。
  
如果要更新域管理员、虚拟机管理员、安全模式管理员和租户管理员凭据，可以使用  _UpdateAllCredentials_ 参数运行 cmdlet 以重置所有凭据：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

然后，当你开始升级到新版本时，你将被提升为输入新的凭据。 
  
如果只想重置租户管理员凭据，请运行以下 cmdlet：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>将多个网站升级到新版本
<a name="BKMK_Upgrade"> </a>

按照升级单个站点的步骤操作，为部署中的每个站点一次升级一个站点。 请确保在升级 [每个站点后验证](validate-your-cloud-connector-deployment.md) 云连接器部署。
