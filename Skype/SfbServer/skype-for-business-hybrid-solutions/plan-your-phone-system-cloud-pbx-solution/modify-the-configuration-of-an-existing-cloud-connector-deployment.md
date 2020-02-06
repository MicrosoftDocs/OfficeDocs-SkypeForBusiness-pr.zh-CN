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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 按照本主题中的步骤修改现有 Skype for Business Cloud Connector Edition 1.4.1 或更高版本的部署配置。
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799432"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modify the configuration of an existing Cloud Connector deployment
 
按照本主题中的步骤修改现有 Skype for Business Cloud Connector Edition 1.4.1 或更高版本的部署配置。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改单个站点的配置
<a name="BKMK_SIngleSite"> </a>

如果站点中仅有一个设备，并且你在部署设备之后想要更改配置设置，你可以修改 CloudConnector.ini 文件并重新开始部署。
  
1. 运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销该设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 更新配置：（此步骤仅适用于版本 2; 对于以前的版本，请跳到下一步。）
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 运行以下 cmdlet 以重新注册该设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 运行以下 cmdlet 以安装 Skype for Business 云连接器版本：
    
   ```powershell
   Install-CcAppliance
   ```

如果站点中有多台设备，则需执行以下步骤：修改 CloudConnector.ini 文件，并逐一重新部署设备。
  
1. 运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机：  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销该设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 更新配置：（此步骤仅适用于版本 2; 对于以前的版本，请跳到下一步。）
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 运行以下 cmdlet 以重新注册该设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：
    
   ```powershell
   Publish-CcAppliance
   ```

7. 运行以下 cmdlet 以在当前设备上重新部署云连接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多个站点的配置
<a name="BKMK_MultipleSites"> </a>

若要在部署中修改多个网站的配置，请按照单个网站的步骤进行操作，一次更新一个网站。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>修改 Office 365 租户的配置以启用自动更新
<a name="BKMK_MultipleSites"> </a>

若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。
  
如果你禁用了操作系统自动更新或 Bits 自动更新，则你的主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器将不会自动升级到新版本。 强烈建议启用自动更新。
  
1. 网站的 EnableAutoUpdate 属性需要设置为 true （默认值）。 运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 为租户创建自动更新时间窗口。
    
    时间窗口可以是每日、每周和每月。所有时间窗口都需要指定开始时间和持续时间。
    
   - 对于每日时间窗口，只需要指定开始时间和持续时间。 
    
   - 对于每周时间窗口，需要指定星期几，可以是一天或多天。
    
   - 对于每月时间窗口，可以是两种类型。第一种类型是指定月中几号，可以是一天。第二种类型是指定月中哪周和星期几，两者都可以是单个项或多个项。
    
   - 最多可为每个租户定义 20 个时间窗口。系统会为新租户创建默认时间窗口以用作操作系统更新和 Bits 更新的默认时间窗口。运行以下 cmdlet 以设置每日、每周或每月时间窗口：
    
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

   - 将更新时间窗口分配给站点。  
    
     位更新时间窗口和操作系统更新时间窗口是单独配置的。 可以为位更新和操作系统更新分配单个或多个时间窗口。 可以将每个时间窗口分配给不同站点和不同用途（位更新和操作系统更新）。 运行以下 cmdlet 为站点设置时间窗口：  
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新专用租户管理员凭据
<a name="BKMK_MultipleSites"> </a>

Office 365 租户 for Cloud Connector 中的管理更改是从具有所需权限的帐户进行的。 在2.0 之前的云连接器版本中，该帐户是专用的全局租户管理员帐户。 在云连接器版本2.0 和更高版本中，该帐户可以是具有 Skype for Business 管理员权限的 Office 365 帐户。
  
如果你的管理员帐户凭据在 Office 365 中发生更改，你还需要通过在你部署的每个云连接器装置上运行以下管理员 PowerShell 命令来更新云连接器中的本地缓存凭据：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主机服务器的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本节仅适用于云连接器 2.0 版和更高版本。 
  
所有云连接器凭据均存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。 当主机服务器上的密码更改时，需要更新本地存储的凭据。
  
若要在云连接器设备上更新本地存储的凭据，请使用[CcCredential](get-cccredential.md)和[CcCredential](set-cccredential.md) cmdlet，然后按照以下步骤操作：
  
1. 运行以下命令，以检索稍后将需要的密码： 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. 在主机服务器上更改帐户的密码。
    
3. 重新启动主机服务器。
    
4. 删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。
    
5. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。 请务必输入之前输入的用于云连接器部署的相同密码。
    
默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
  
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。
    
2. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帐户的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 此部分适用于云连接器版本2.0.1 及更高版本。 
  
云连接器服务运行云连接器管理服务。 CceService 帐户在云连接器版本部署期间创建并存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>和%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService "。
  
若要确保所有设备都可以访问网站目录共享，CceService 帐户的密码在网站中部署的所有设备上必须是相同的。 注意以下几项：
  
- 默认情况下，CceService 帐户配置为 "密码永不过期"。 更新密码时，Microsoft 建议保留此配置。
    
- 你应该在非高峰使用期和自动更新时间窗口（bits 或 Windows 更新）外更新密码。 更新密码时，设备需要排出并重新启动，这需要一些时间。 重新启动装置将中断自动更新操作。 
    
- 更改 CceService 帐户密码时，你需要指定所有凭据并在本地存储的文件中更新它们。 
    
对于属于同一 PSTN 站点的每个装置，您将需要指定以下内容： 
  
1. 运行以下命令以检索稍后将使用的帐户名称和密码：
    
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

2. 运行 CcUpdate cmdlet 以耗尽装置并将其移动到手动维护模式。
    
3. 更新主服务器上的 CceService 帐户密码。
    
4. 重新启动主机服务器。
    
5. 运行 CcCredentials cmdlet 以在描述之后重新输入密码。 
    
    请确保输入的密码与你在云连接器部署之前输入的密码相同，但 CceService 帐户除外。 对于 CceService 帐户，请输入您的新密码。 请确保 CceService 帐户的新密码对于 PSTN 站点中的所有设备都是相同的。
    
6. 默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
    
7. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。
    
8. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。 
    
9. 运行 CcUpdate cmdlet，将设备移出手动维护模式。
    
10. 在同一 PSTN 站点中的所有装置上完成这些步骤后，在 "网站根目录" 中删除以下文件：
    
    - CcLockFile
    
    - Site_\<Edge 外部 Sip 池 fqdn\>
    
    - Tenant_\<Edge 外部 Sip 池 fqdn\>
    
    - TenantConfigLock_\<Edge 外部 Sip 池 fqdn\>
    
## <a name="add-a-new-sip-domain"></a>添加新 SIP 域 
<a name="BKMK_UpdatePassword"> </a>

若要向现有云连接器部署添加新的 SIP 域（或多个 SIP 域），请执行以下操作：
  
1. 确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。 有关如何在 Office 365 中设置域的详细信息，请参阅[将域添加到 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 用新的 SIP 域或域更新云连接器配置文件。
    
3. 使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。适用于你的云连接器配置中定义的每个 SIP 域的域。 
    
4. 按如下所述设置新边缘外部证书的路径：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    按照说明[修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)或[修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。
    
## <a name="modify-the-primary-sip-domain"></a>输入主 SIP 域
<a name="BKMK_UpdatePassword"> </a>

如果需要在云连接器部署中更改主要 SIP 域，请执行以下操作：
  
1. 确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。 有关如何在 Office 365 中设置域的详细信息，请参阅[将域添加到 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 用新的 SIP 域更新云连接器配置文件。
    
3. 使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。适用于你的云连接器配置中定义的每个 SIP 域的域。 
    
4. 按如下所述设置新边缘外部证书的路径：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来删除网站中每个设备的租户注册：
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    通过在 Skype for Business Online PowerShell 中运行以下 cmdlet 来删除每个网站的网站注册：
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来卸载每个装置：
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来注册每个设备：
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，逐个安装每个装置：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>将外部边缘证书替换为新证书
<a name="BKMK_UpdatePassword"> </a>

当你需要替换云连接器装置上的外部边缘证书时，你需要获取新的边缘证书，准备包含私钥和完整证书链的 PFX 文件，然后在每个设备上执行以下操作：
  
1. 通过使用 CcUpdate cmdlet 将设备置于维护模式。
    
2. 运行以下命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果新证书的密码与旧证书的密码相同，则导入将成功。 如果密码不同，你将收到错误，指出密码错误，你将需要通过运行带有-Local 参数的 CcAppliance cmdlet 来重置密码，然后重复步骤2。 
    
4. 通过使用 CcUpdate cmdlet 使设备退出维护模式。
    

