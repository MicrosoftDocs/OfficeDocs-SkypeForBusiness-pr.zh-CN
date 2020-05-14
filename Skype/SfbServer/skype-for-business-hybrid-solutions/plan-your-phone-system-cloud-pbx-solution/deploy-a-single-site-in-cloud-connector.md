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
description: 了解如何在云连接器版本中部署单个 PSTN 站点。
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220532"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>在云连接器中部署单个站点
 
了解如何在云连接器版本中部署单个 PSTN 站点。
  
您可以部署具有或不具有高可用性（HA）支持的 Skype for Business 云连接器版本。 如果要启用 HA，则需要在站点中部署两个或更多个设备。 您还可以在部署现有设备后将其转换为支持 HA。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>部署第一个 Skype for Business 云连接器版本设备

若要在站点中部署第一个设备，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet 来注册设备：
  
```powershell
Register-CcAppliance
```

按照说明提供租户管理员帐户名称和密码。 使用为云连接器在线管理创建的帐户。 此外，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码以及虚拟机管理员密码。 
  
在1.4.2 版和早期版本中，还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。 
  
在版本2.0 及更高版本中，还要按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。
  
若要开始安装，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>将设备添加到现有网站

您可以通过向站点添加其他设备来扩展现有云连接器网站，以支持 HA。 
  
1. 按照[准备云连接器设备](prepare-your-cloud-connector-appliance.md)中所述的步骤准备云连接器设备。 请注意，仅在部署中的第一台设备上需要一些步骤。 确认网站目录存在，并且已正确配置 HA 支持。
    
2. 仅在新添加的主机服务器上运行以下 cmdlet，以更新 Microsoft 365 或 Office 365 组织配置中的拓扑信息。 如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行 cmdlet：
    
   ```powershell
   Register-CcAppliance
   ```

3. 通过在每台主机服务器上运行以下 cmdlet 来更新现有设备上的拓扑。 仅在现有设备上运行 cmdlet。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 仅在新添加的主机服务器上运行以下 cmdlet。 请勿在现有设备上运行此 cmdlet。 如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 如果网站目录设置为本地文件夹路径，则需要为该文件夹定义文件共享，并在新设备上对网站目录使用 UNC 路径。 你可以将第一个装置网站目录保留为本地路径，或将其修改为将共享的 UNC 路径用于同一文件夹。 如果共享网站目录的位置发生更改，则需要卸载之前安装的所有设备，然后重新安装。 > 重要说明： CceService 帐户和 CABackupFile 帐户的密码必须在网站中部署的所有设备上都相同，这样设备才能访问网站目录中的网站目录共享和加密的 CA 备份文件。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>从现有网站中删除设备

如果要从现有站点中删除设备，请执行以下操作：
  
1. 仅在要从网站中删除的主机服务器上运行以下 cmdlet，以更新 Microsoft 365 或 Office 365 组织配置中的拓扑信息。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 仅在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。
    
   ```powershell
   Uninstall-CcAppliance
   ```


