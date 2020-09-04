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
description: 按照本主题中的步骤修改现有 Skype for Business 云连接器 Edition 1.4.1 或更高版本部署的配置。
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359108"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改现有云连接器部署的配置

> [!Important]
> 云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。 组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。

按照本主题中的步骤修改现有 Skype for Business 云连接器 Edition 1.4.1 或更高版本部署的配置。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改单个网站的配置
<a name="BKMK_SIngleSite"> </a>

如果站点中只有一个设备，则当您要在部署设备后更改配置设置时，可以修改 CloudConnector.ini 文件并重新启动部署。
  
1. 运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳至下一步。 ) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 运行以下 cmdlet 再次注册设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 运行以下 cmdlet 以安装 Skype for Business 云连接器版本：
    
   ```powershell
   Install-CcAppliance
   ```

如果站点中有多个设备，您需要执行以下步骤，修改 CloudConnector.ini 文件，然后逐一重新部署这些设备。
  
1. 运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 运行以下 cmdlet 以注销设备：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳至下一步。 ) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 运行以下 cmdlet 再次注册设备：
    
   ```powershell
   Register-CcAppliance
   ```

6. 在站点中的所有其他设备上运行以下 cmdlet，以获取最新配置：
    
   ```powershell
   Publish-CcAppliance
   ```

7. 运行以下 cmdlet 以在当前设备上重新部署云连接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多个网站的配置
<a name="BKMK_MultipleSites"> </a>

若要修改部署中多个站点的配置，请按照单个站点的步骤操作，一次更新一个站点。
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>修改 Microsoft 365 或 Office 365 组织的配置以启用自动更新
<a name="BKMK_MultipleSites"> </a>

若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。
  
如果您禁用了操作系统自动更新或 Bits 自动更新，则主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器将不会自动升级到新版本。 强烈建议您启用自动更新。
  
1. 需要将网站的 EnableAutoUpdate 属性设置为 true () 默认值。 运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 为租户创建自动更新时间窗口。
    
    时间窗口可以是每天、每周和每月。 所有时间窗口都需要一个开始时间和一个持续时间。
    
   - 对于每日时间窗口，仅需要开始时间和持续时间。 
    
   - 对于每周时间窗口，需要一周天数，可以是一天或多天。
    
   - 对于每月时间窗口，可以有两种类型。 第一种类型是指定月中的某一天，该日期可以是一天。 第二种类型是指定一个月中的周数以及一周中的天数，这两个值可以是单个项目，也可以是多个项目。
    
   - 每个租户都可以定义20个时间窗口。 将为新租户创建默认时间窗口作为操作系统更新和 Bits 更新的默认时间窗口。 运行以下 cmdlet (s) 设置每日、每周或每月时间窗口：
    
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
    
     Bits 更新时间和 OS 更新时间窗口是单独配置的。 可以为它们分配一个或多个时间窗口。 每个时间窗口可分配给不同的网站，不同的用途 (Bits update 和 OS update) 。 运行以下 cmdlet 来设置网站的时间窗口： 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新专用租户管理员凭据
<a name="BKMK_MultipleSites"> </a>

Microsoft 365 或 Office 365 组织中的云连接器的管理更改是从具有所需权限的帐户进行的。 在2.0 之前的云连接器版本中，该帐户是专用的全局租户管理员帐户。 在云连接器版本2.0 及更高版本中，该帐户可以是具有 Skype for Business 管理员权限的 Microsoft 365 或 Office 365 帐户。
  
如果您的管理员帐户凭据在 Microsoft 365 或 Office 365 中发生更改，您还需要在部署的每个云连接器设备上运行以下管理员 PowerShell 命令，以更新云连接器中的本地缓存凭据：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主机服务器的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本节适用于云连接器版本2.0 及更高版本。 
  
所有云连接器凭据都存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "。 当主机服务器上的密码更改时，您将需要更新本地存储的凭据。
  
若要在云连接器设备上更新本地存储的凭据，请使用 [set-cccredential](get-cccredential.md) 和 [set-cccredential](set-cccredential.md) cmdlet，并执行以下步骤：
  
1. 运行以下命令以检索稍后将需要的密码： 
    
   - Set-cccredential-AccountType DomainAdmin-DisplayPassword
    
   - Set-cccredential-AccountType VMAdmin-DisplayPassword
    
   - Set-cccredential-AccountType CceService-DisplayPassword
    
2. 更改您的帐户在主机服务器上的密码。
    
3. 重新启动主机服务器。
    
4. 删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "。
    
5. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。 请确保输入的密码与您在云连接器部署之前输入的密码相同。
    
默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果在步骤1中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
  
1. 运行 Set-cccredential-AccountType DomainAdmin，如下所示：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入第1步中返回的 DomainAdmin 密码的密码。
    
2. 运行 Set-cccredential-AccountType VmAdmin，如下所示：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入第1步中返回的 VmAdmin 密码的密码。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帐户的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本节适用于云连接器2.0.1 和更高版本。 
  
云连接器服务运行云连接器管理服务。 在云连接器版本部署过程中创建 CceService 帐户，并将其存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "和"% 系统驱动器% \Programdata\Cloudconnector\credentials..CceService.xml "。
  
若要确保所有设备都能访问网站目录共享，CceService 帐户的密码必须在网站中部署的所有设备上都相同。 请注意下列事项：
  
- 默认情况下，CceService 帐户配置为 "密码永不过期"。 更新密码时，Microsoft 建议保留此配置。
    
- 应在非高峰使用期和自动更新时间窗口之外的 bits 或 Windows 更新中更新密码。 当您更新密码时，设备需要耗尽并重新启动，这需要一些时间。 重新启动设备将会中断自动更新操作。 
    
- 当您更改 CceService 帐户密码时，您需要指定所有凭据并在本地存储的文件中进行更新。 
    
对于属于同一个 PSTN 站点的每个设备，您需要指定以下各项： 
  
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

2. 运行 Enter-ccupdate cmdlet 以耗尽设备并将其移动到手动维护模式。
    
3. 更新主机服务器上的 CceService 帐户的密码。
    
4. 重新启动主机服务器。
    
5. 运行 CcCredentials cmdlet，以在说明后面重新输入密码。 
    
    请确保输入的密码与您在云连接器部署之前输入的密码相同（CceService 帐户除外）。 对于 CceService 帐户，请输入新密码。 确保 PSTN 站点中所有设备的 CceService 帐户的新密码是相同的。
    
6. 默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果在步骤1中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
    
7. 运行 Set-cccredential-AccountType DomainAdmin，如下所示：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入第1步中返回的 DomainAdmin 密码的密码。
    
8. 运行 Set-cccredential-AccountType VmAdmin，如下所示：
    
   - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
   - 当系统提示输入新帐户凭据时，请输入第1步中返回的 VmAdmin 密码的密码。 
    
9. 运行 Enter-ccupdate cmdlet 以将设备移出手动维护模式。
    
10. 在同一 PSTN 站点中的所有设备上完成这些步骤后，请删除站点根目录中的以下文件：
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>添加新的 SIP 域
<a name="BKMK_UpdatePassword"> </a>

若要将新的 SIP 域 (或多个 SIP 域添加) 到现有云连接器部署中，请执行以下操作：
  
1. 请确保已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。 有关如何在 Microsoft 365 或 Office 365 中设置域的详细信息，请参阅 [将域添加到 microsoft 365 或 office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 域或域更新云连接器配置文件。
    
3. 使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。在你的云连接器配置中定义的每个 SIP 域的域。 
    
4. 设置新的边缘外部证书的路径，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    按照说明 [修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 或 [修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。
    
## <a name="modify-the-primary-sip-domain"></a>修改主要 SIP 域
<a name="BKMK_UpdatePassword"> </a>

如果您需要在云连接器部署中更改主要 SIP 域，请执行以下操作：
  
1. 请确保已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。 有关如何在 Microsoft 365 或 Office 365 中设置域的详细信息，请参阅 [将域添加到 microsoft 365 或 office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 域更新云连接器配置文件。
    
3. 使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。在你的云连接器配置中定义的每个 SIP 域的域。 
    
4. 设置新的边缘外部证书的路径，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，删除网站中每个设备的租户注册：
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    通过在 Skype for Business Online PowerShell 中运行以下 cmdlet 来删除每个网站的网站注册：
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 卸载每个设备：
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 注册每个设备：
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，逐一安装每个设备：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>将外部边缘证书替换为新证书
<a name="BKMK_UpdatePassword"> </a>

当您需要替换云连接器设备上的外部边缘证书时，您需要获取新的边缘证书，准备 PFX 文件，其中包含私钥和完整证书链，然后在每台设备上执行以下操作：
  
1. 使用 Enter-ccupdate cmdlet 将设备置于维护模式。
    
2. 运行以下命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果新证书的密码与旧证书的密码相同，则导入将成功。 如果密码不同，您将收到错误消息，指出密码错误，您需要通过运行带有-Local 参数的 Register-ccappliance cmdlet 来重置密码，然后重复步骤2。 
    
4. 使用 Enter-ccupdate cmdlet 使设备退出维护模式。
    

