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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 了解如何在云连接器版本中部署单个 PSTN 站点。
ms.openlocfilehash: 07262f88f85602b6213dc287babbd05ddec25ed9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610539"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>在云连接器中部署单个站点
 
> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解如何在云连接器版本中部署单个 PSTN 站点。
  
你可以部署支持Skype for Business 云连接器版本高可用性 HA 支持 (高可用性) 部署。 如果要启用 HA，则需要在站点内部署两台或多部设备。 还可以在部署现有设备后将其转换为支持 HA。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>部署第一Skype for Business 云连接器版本设备

若要在站点中部署第一个设备，请以管理员角色打开 PowerShell 控制台并运行以下 cmdlet 以注册该设备：
  
```powershell
Register-CcAppliance
```

按照说明提供租户管理员帐户名称和密码。 使用你为云连接器联机管理创建的帐户。 此外，请按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在 1.4.2 版及更早版本中，还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在 2.0 版及更高版本中，还按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。
  
若要开始安装，请以管理员角色打开 PowerShell 控制台并运行以下 cmdlet：
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>将设备添加到现有站点

可以通过向站点添加其他设备来扩展现有云连接器站点以支持 HA。 
  
1. 按照准备云连接器设备 中所述的步骤准备 [云连接器设备](prepare-your-cloud-connector-appliance.md)。 请注意，只有部署中的第一个设备需要执行某些步骤。 确认站点目录存在且已正确配置为支持 HA。
    
2. 仅在新添加的主机服务器上运行以下 cmdlet，以更新组织配置中的Microsoft 365 Office 365信息。 如果要同时添加多个设备，请分别在每台新添加的主机服务器上运行 cmdlet：
    
   ```powershell
   Register-CcAppliance
   ```

3. 在每个主机服务器上运行以下 cmdlet，更新现有设备上的拓扑。 仅对现有设备运行 cmdlet。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 仅在新添加的主机服务器上运行以下 cmdlet。 不要对现有设备运行此 cmdlet。 如果要同时添加多个设备，请在每个新添加的主机服务器上分别运行 cmdlet。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 如果站点目录设置为本地文件夹路径，则需要为此文件夹定义文件共享，并使用新设备中的站点目录的 UNC 路径。 你可以将第一个设备站点目录保留为本地路径，或修改它以使用共享到同一文件夹的 UNC 路径。 如果共享网站目录的位置发生更改，则需要卸载之前安装的任何设备，然后重新安装。 >重要说明：在站点内部署的所有设备上，CceService 帐户和 CABackupFile 帐户的密码必须相同，以便设备可以访问站点目录中的站点目录共享和加密的 CA 备份文件。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>从现有站点删除设备

如果要从现有站点删除设备：
  
1. 仅在要从站点中删除的主机服务器上运行以下 cmdlet，以更新组织配置中的Microsoft 365 Office 365信息。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 仅在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。
    
   ```powershell
   Uninstall-CcAppliance
   ```