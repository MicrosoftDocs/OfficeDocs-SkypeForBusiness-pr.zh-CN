---
title: 修改现有云连接器部署的配置
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 按照本主题中的步骤修改现有部署Skype for Business 云连接器版本 1.4.1 或更高版本部署。
ms.openlocfilehash: 5d0771e1f6a62015cf040a899c88696016366e47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590006"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改现有云连接器部署的配置

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

按照本主题中的步骤修改现有部署Skype for Business 云连接器版本 1.4.1 或更高版本部署。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改单个网站的配置
<a name="BKMK_SIngleSite"> </a>

如果站点中只有一个设备，当你想要在部署设备后更改配置设置时，你可以修改 CloudConnector.ini 文件，然后重新开始部署。
  
1. 运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新CloudConnector.ini目录中的安装文件。
    
4. 运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳到下一步。) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 再次运行以下 cmdlet 以注册设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 运行以下 cmdlet 以安装Skype for Business 云连接器版本：
    
   ```powershell
   Install-CcAppliance
   ```

如果站点中存在多个设备，你将需要按照以下步骤操作、修改 CloudConnector.ini 文件，然后一个一个地重新部署设备。
  
1. 运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新CloudConnector.ini目录中的安装文件。
    
4. 运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳到下一步。) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 再次运行以下 cmdlet 以注册设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：
    
   ```powershell
   Publish-CcAppliance
   ```

7. 运行以下 cmdlet 以在当前设备中重新部署云连接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多个网站的配置
<a name="BKMK_MultipleSites"> </a>

若要修改部署中多个站点的配置，请按照单个站点的步骤操作，一次更新一个站点。
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>修改组织或组织Microsoft 365 Office 365以启用自动更新
<a name="BKMK_MultipleSites"> </a>

若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。
  
如果禁用操作系统自动更新或 Bits 自动更新，主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器不会自动升级到新版本。 强烈建议您启用自动更新。
  
1. 网站的 EnableAutoUpdate 属性需要设置为 true， (默认值) 。 运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 为租户创建自动更新时间窗口。
    
    时间窗口可以是每天、每周和每月。 所有时间窗口都需要开始时间和持续时间。
    
   - 对于每日时间窗口，只需要开始时间和持续时间。 
    
   - 对于每周时间窗口，需要一周中的几天，可以是一天或多天。
    
   - 对于每月时间窗口，可以有两种类型。 第一种类型是指定月中的哪一天，可以是一天。 第二种类型是指定一个月的星期数以及一周中的哪几天，这两者都可以是单个项目或多个项目。
    
   - 每个租户可以定义 20 个时间窗口。 将为新租户创建默认时间窗口，作为操作系统更新和 Bits 更新的默认时间窗口。 运行以下 cmdlet () 设置每日、每周或每月时间窗口：
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - 将更新时间窗口分配给网站。 
    
     位更新时间和操作系统更新时间窗口是单独配置的。 这两个窗口都可以分配一个或多个时间窗口。 可以将每个时间窗口分配给不同的站点和不同的用途 (位更新和操作系统更新) 。 运行以下 cmdlet 设置网站的时间窗口： 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新专用租户管理员凭据
<a name="BKMK_MultipleSites"> </a>

云连接器Microsoft 365或Office 365管理更改是由具有所需权限的帐户进行。 在 2.0 以前的云连接器版本中，该帐户是专用全局租户管理员帐户。 在云连接器 2.0 版和更高版本中，该帐户可以是具有 Microsoft 365 或 Office 365 管理员权限Skype for Business帐户。
  
如果你的管理员帐户凭据在 Microsoft 365 或 Office 365 中更改，则还需要更新云连接器中本地缓存的凭据，只需在已部署的每个云连接器设备上运行以下管理员 PowerShell 命令：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主机服务器的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本部分适用于云连接器 2.0 版和更高版本。 
  
所有云连接器凭据都存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials"。 \<CurrentUser\>.xml"。 当主机服务器上密码更改时，您需要更新本地存储的凭据。
  
若要更新云连接器设备本地存储的凭据，请使用 [Get-CcCredential](get-cccredential.md) 和 [Set-CcCredential](set-cccredential.md) cmdlet 并按照以下步骤操作：
  
1. 运行以下命令以检索稍后将需要的密码： 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. 更改主机服务器上帐户的密码。
    
3. 重新启动主机服务器。
    
4. 删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials"。 \<CurrentUser\>.xml"。
    
5. 以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。 请务必输入之前为云连接器部署输入的相同密码。
    
默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果步骤 1 中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
  
1. 运行 Set-CcCredential -AccountType DomainAdmin，如下所示：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 DomainAdmin 密码的密码。
    
2. 运行Set-CcCredential -AccountType VmAdmin，如下所示：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 VmAdmin 密码的密码。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帐户的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本部分适用于云连接器版本 2.0.1 及更高版本。 
  
云连接器服务运行云连接器管理服务。 CceService 帐户在云连接器版本部署期间创建，并存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials"。 \<CurrentUser\>.xml"和"%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml"。
  
为了确保所有设备都可以访问站点目录共享，在站点内部署的所有设备上，CceService 帐户的密码必须相同。 请注意以下几点：
  
- 默认情况下，CceService 帐户配置为"密码永不过期"。 更新密码时，Microsoft 建议保留此配置。
    
- 您应在非高峰使用时段和自动更新时间窗口之外更新密码，以更新位或Windows更新。 更新密码时，设备需要排出并重启，这需要花费一些时间。 重新启动设备将中断自动更新操作。 
    
- 更改 CceService 帐户密码时，将需要指定所有凭据，并在本地存储的文件中更新它们。 
    
对于属于同一 PSTN 站点的每台设备，你将需要指定以下内容： 
  
1. 运行以下命令以检索您将稍后使用的帐户名称和密码：
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. 运行 Enter-CcUpdate cmdlet 以排出设备，将其移动到手动维护模式。
    
3. 更新主机服务器上 CceService 帐户的密码。
    
4. 重新启动主机服务器。
    
5. 运行 Restore-CcCredentials cmdlet，按照说明重新输入密码。 
    
    请确保输入之前为云连接器部署输入的相同密码，CceService 帐户除外。 对于 CceService 帐户，输入新密码。 确保 CceService 帐户的新密码与 PSTN 站点中所有设备的密码相同。
    
6. 默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果步骤 1 中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
    
7. 运行 Set-CcCredential -AccountType DomainAdmin，如下所示：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 DomainAdmin 密码的密码。
    
8. 运行Set-CcCredential -AccountType VmAdmin，如下所示：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 VmAdmin 密码的密码。 
    
9. 运行 Exit-CcUpdate cmdlet 以将设备从手动维护模式中移动。
    
10. 在同一 PSTN 站点的所有设备上完成这些步骤后，删除站点根目录中的以下文件：
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>添加新 SIP 域
<a name="BKMK_UpdatePassword"> </a>

若要将新的 SIP 域 (或多个 SIP) 添加到现有云连接器部署中，请执行下列操作：
  
1. 请确保已完成在域中更新域Microsoft 365 Office 365并能够添加 DNS 记录。 若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域Microsoft 365[或Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. 使用新的 SIP 域更新云连接器配置文件。
    
3. 为云连接器配置中定义的每个 SIP 域请求具有 sip.domain 的其他 SAN 名称的新边缘外部证书。 
    
4. 设置新边缘外部证书的路径，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    按照说明 [修改单个站点的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 配置或修改 [多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。
    
## <a name="modify-the-primary-sip-domain"></a>修改主 SIP 域
<a name="BKMK_UpdatePassword"> </a>

如果需要更改云连接器部署中的主 SIP 域，请执行下列操作：
  
1. 请确保已完成在域中更新域Microsoft 365 Office 365并能够添加 DNS 记录。 若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域Microsoft 365[或Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. 使用新的 SIP 域更新云连接器配置文件。
    
3. 为云连接器配置中定义的每个 SIP 域请求具有 sip.domain 的其他 SAN 名称的新边缘外部证书。 
    
4. 设置新边缘外部证书的路径，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    在云连接器上的管理员 PowerShell 中运行以下 cmdlet，删除站点中每台设备的租户注册：
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    在 Skype for Business PowerShell 中运行以下 cmdlet，删除每个Skype for Business注册：
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    在云连接器上的管理员 PowerShell 中运行以下 cmdlet 卸载每台设备：
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     在云连接器上的管理员 PowerShell 中运行以下 cmdlet 注册每台设备：
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     在云连接器上的管理员 PowerShell 中运行以下 cmdlet，分别安装每台设备：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>将外部边缘证书替换为新证书
<a name="BKMK_UpdatePassword"> </a>

当你需要替换云连接器设备上的外部边缘证书时，你将需要获取新的边缘证书，准备包含私钥和完整证书链的 PFX 文件，然后在每个设备上执行以下操作：
  
1. 使用 cmdlet 将设备置于维护Enter-CcUpdate模式。
    
2. 运行以下命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果新证书的密码与旧证书相同，则导入将成功。 如果密码不同，您将收到密码错误的错误，您需要通过运行带 -Local 参数的 Register-CcAppliance cmdlet，然后重复步骤 2 来重置密码。 
    
4. 使用 Exit -CcUpdate cmdlet 使设备退出维护模式。
