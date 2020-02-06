---
title: 在云连接器中部署单个站点
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 了解有关在云连接器版本中部署单个 PSTN 站点的信息。
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799702"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
了解有关在云连接器版本中部署单个 PSTN 站点的信息。
  
你可以部署具有或不具有高可用性（HA）支持的 Skype for Business 云连接器版本。 如果要启用 HA，你需要在一个站点中部署两个或更多设备。 你也可以在部署现有设备后将其转换为支持 HA。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>部署第一个 Skype for Business 云连接器版本设备

要在站点中部署第一个设备，请以管理员身份打开 PowerShell 控制台并运行以下 cmdlet，以注册该设备：
  
```powershell
Register-CcAppliance
```

按照说明提供租户管理员帐户名称和密码。请使用你为云连接器在线管理创建的帐户。此外，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和虚拟机管理员密码。 
  
在1.4.2 及更早版本中，还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在 2.0 版和更高版本中，还要按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。
  
要开始安装，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>将设备添加到现有站点

你可以通过向网站添加其他装置来扩展现有云连接器网站以支持 HA。 
  
1. 按照[准备云连接器设备](prepare-your-cloud-connector-appliance.md)中所述，按照步骤准备云连接器设备。 请注意，有些步骤仅限于部署中的第一个设备。 请确认站点目录已存在且已为支持 HA 进行了正确配置。
    
2. 仅在新添加的主机服务器上运行以下 cmdlet 以更新 Office 365 租户配置中的拓扑信息。如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet：
    
   ```powershell
   Register-CcAppliance
   ```

3. 在每个主机服务器上运行以下 cmdlet 以更新现有设备中的拓扑。只在现有设备例上运行该 cmdlet。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 只在新添加的主机服务器上运行以下 cmdlet。 请勿在现有设备上运行该 cmdlet。 如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 如果将站点目录设置为本地文件夹路径，则需为此文件夹定义文件共享，并对新设备上的站点目录使用 UNC 路径。 可将第一个设备站点目录保留为本地路径，或对其进行修改以使用到同一文件夹的共享的 UNC 路径。 如果共享站点目录的位置发生变化，则需卸载再重新安装之前安装的所有设备。 > 重要： CceService 帐户和 CABackupFile 帐户的密码在网站中部署的所有设备上必须相同，以便装置可以访问网站目录中的网站目录共享和加密的 CA 备份文件。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>从现有站点中删除设备

如果要从现有站点中删除设备，请执行以下操作：
  
1. 只在要从站点中删除的主机服务器上运行以下 cmdlet 以更新 Office 365 租户配置中的拓扑信息。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 只在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。
    
   ```powershell
   Uninstall-CcAppliance
   ```


