---
title: 修改现有云连接器部署的配置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 按照本主题来修改现有 Skype 业务云连接器版本 1.4.1 或更高版本的部署配置中的步骤。
ms.openlocfilehash: 8a47cf74226294e273a3887d010d4fe21aeb5e12
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改现有云连接器部署的配置
 
按照本主题来修改现有 Skype 业务云连接器版本 1.4.1 或更高版本的部署配置中的步骤。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改单个站点的配置
<a name="BKMK_SIngleSite"> </a>

如果站点中仅有一个设备，并且你在部署设备之后想要更改配置设置，你可以修改 CloudConnector.ini 文件并重新开始部署。
  
1. 运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机： 
    
  ```
  Uninstall-CcAppliance
  ```

2. 运行以下 cmdlet 以注销该设备：
    
  ```
  Unregister-CcAppliance
  ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 以更新配置: （此步骤才适用第 2 版; 以前的版本，请跳到下一步）。
    
  ```
   Import-CcConfiguration 
  ```

5. 运行以下 cmdlet 以重新注册该设备：
    
  ```
  Register-CcAppliance
  ```

6. 运行以下 cmdlet 以安装 Skype for Business 云连接器版本：
    
  ```
  Install-CcAppliance
  ```

如果站点中有多台设备，则需执行以下步骤：修改 CloudConnector.ini 文件，并逐一重新部署设备。
  
1. 运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机： 
    
  ```
  Uninstall-CcAppliance
  ```

2. 运行以下 cmdlet 以注销该设备：
    
  ```
  Unregister-CcAppliance
  ```

3. 更新设备目录中的 CloudConnector.ini 文件。
    
4. 运行以下 cmdlet 以更新配置: （此步骤才适用第 2 版; 以前的版本，请跳到下一步）。
    
  ```
   Import-CcConfiguration 
  ```

5. 运行以下 cmdlet 以重新注册该设备：
    
  ```
  Register-CcAppliance
  ```

6. 对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：
    
  ```
  Publish-CcAppliance
  ```

7. 运行以下 cmdlet 当前装置上重新部署云连接器：
    
  ```
  Install-CcAppliance
  ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多个站点的配置
<a name="BKMK_MultipleSites"> </a>

要修改多个站点部署中的配置，请按照为单个网站，一次更新一个站点的步骤。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>修改 Office 365 租户的配置以启用自动更新
<a name="BKMK_MultipleSites"> </a>

若要启用操作系统的自动更新和位自动更新，必须使用 Skype 的商业租户管理帐户的在线管理和使用，如下所示租户远程 PowerShell。
  
如果您禁用操作系统自动更新或位自动更新，您的主机和虚拟机可能会错过重要 Windows 更新，和云连接器不会自动升级到最新版本。 强烈建议启用自动更新。
  
1. 该站点的 EnableAutoUpdate 属性必须设置为 true （默认值）。 运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：
    
  ```
  Get-CsHybridPSTNSite -Identity <SiteName>
  ```

2. 为租户创建自动更新时间窗口。
    
    时间窗口可以是每日、每周和每月。所有时间窗口都需要指定开始时间和持续时间。
    
  - 对于每日时间窗口，只需要指定开始时间和持续时间。 
    
  - 对于每周时间窗口，需要指定星期几，可以是一天或多天。
    
  - 对于每月时间窗口，可以是两种类型。第一种类型是指定月中几号，可以是一天。第二种类型是指定月中哪周和星期几，两者都可以是单个项或多个项。
    
  - 最多可为每个租户定义 20 个时间窗口。系统会为新租户创建默认时间窗口以用作操作系统更新和 Bits 更新的默认时间窗口。运行以下 cmdlet 以设置每日、每周或每月时间窗口：
    
  ```
  New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
  ```

  - 将更新时间窗口分配给站点。 
    
    位更新时间窗口和操作系统更新时间窗口是单独配置的。 可以为位更新和操作系统更新分配单个或多个时间窗口。 可以将每个时间窗口分配给不同站点和不同用途（位更新和操作系统更新）。 运行以下 cmdlet 为站点设置时间窗口： 
    
  ```
  Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
  ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新专用租户管理员凭据
<a name="BKMK_MultipleSites"> </a>

从具有所需权限的帐户进行 Office 365 租户云连接器中的管理更改。 在云连接器 2.0 之前的版本中，该帐户是专用的全局租户管理员帐户。 在云连接器 2.0 及更高版本中，该帐户可以是 Office 365 Skype 与业务管理员权限的帐户。
  
如果您的管理员帐户凭据更改 Office 365 中的还需要通过在部署每个云接头装置上运行以下管理员 PowerShell 命令更新中云连接器的本地缓存的凭据：
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主机服务器的密码
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本节仅适用于云连接器 2.0 版和更高版本。 
  
所有的云连接器凭据存储在下列文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。 在主机服务器上的密码更改时，您将需要更新本地存储的凭据。
  
若要更新云接头装置上的本地存储的凭据，使用[Get CcCredential](get-cccredential.md)和[一组 CcCredential](set-cccredential.md) cmdlet，然后执行以下步骤：
  
1. 运行以下命令，以检索稍后将需要的密码： 
    
  - 获得 CcCredential-AccountType DomainAdmin-DisplayPassword
    
  - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
  - 获得 CcCredential-AccountType CceService-DisplayPassword
    
2. 在主机服务器上更改帐户的密码。
    
3. 重新启动主机服务器。
    
4. 删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。
    
5. 启动作为管理员，PowerShell 控制台，然后运行"登记 CcAppliance-本地"以重新输入描述的密码。 请确保您输入相同的密码之前输入连接器云部署。
    
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
> 这一节是适用于云连接器 2.0.1 版及更高版本。 
  
云的连接器服务运行的云连接器管理服务。 CceService 帐户是云连接器版部署期间创建，存储在下列文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"和"%systemdrive%\programdata\cloudconnector\credentials.CceService.xml"。
  
若要确保所有装置可都访问网站目录共享，CceService 帐户的密码必须是部署站点内的所有装置相同。 注意以下几项：
  
- 默认情况下，CceService 帐户被配置为"密码永不过期"。 更新密码时，Microsoft 建议保留此配置。
    
- 在非高峰使用时段和外部位或 Windows 更新自动更新的时间窗口，则应更新密码。 更新密码时，本装置需要排放并重新启动，这需要一些时间。 重新启动装置将中断自动更新操作。 
    
- CceService 帐户密码更改时，您将需要指定所有的凭据并存储在本地文件中对其进行更新。 
    
对于属于相同的 PSTN 站点每个装置，需要指定以下项： 
  
1. 运行下列命令以检索帐户名和密码，以后将：
    
  ```
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

2. 运行输入 CcUpdate cmdlet 排出装置并将其移动到手动维护模式。
    
3. 更新主机服务器上的 CceService 帐户的密码。
    
4. 重新启动主机服务器。
    
5. 运行恢复 CcCredentials cmdlet 以重新输入描述的密码。 
    
    请确保您输入相同的密码为 CceService 帐户除云连接器部署输入之前。 该 CceService 帐户，请输入您的新密码。 请确保 CceService 帐户的新密码是相同的 PSTN 站点中的所有装置。
    
6. 默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：
    
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
  - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
  - 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。
    
2. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
  - 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
  - 当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。 
    
7. 运行退出 CcUpdate 用于移动装置出手动维护模式。
    
8. 完成上述步骤相同的 PSTN 站点中的所有装置后，删除站点根目录中的下列文件：
    
  - CcLockFile
    
  - Site_\<边缘外部 Sip 池的 fqdn\>
    
  - Tenant_\<边缘外部 Sip 池的 fqdn\>
    
  - TenantConfigLock_\<边缘外部 Sip 池的 fqdn\>
    
## <a name="add-a-new-sip-domain"></a>添加新 SIP 域 
<a name="BKMK_UpdatePassword"> </a>

若要向现有云连接器部署一个新的 SIP 域 （或多个 SIP 域），请执行以下操作：
  
1. 确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。 有关如何设置您在 Office 365 中的域的详细信息，请参阅视频[设置您在 Office 365 中的域](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
2. 用新的 SIP 域或域中更新云连接器配置文件。
    
3. 申请新边缘外部证书与其他 SAN sip.domain 云连接器配置中定义的每个 SIP 域的名称。 
    
4. 按如下所述设置新边缘外部证书的路径：
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    按照说明[修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)或[修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。
    
## <a name="modify-the-primary-sip-domain"></a>输入主 SIP 域
<a name="BKMK_UpdatePassword"> </a>

如果您需要更改连接器云部署中的主 SIP 域，请执行以下操作：
  
1. 确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。 有关如何设置您在 Office 365 中的域的详细信息，请参阅视频[设置您在 Office 365 中的域](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US)。
    
2. 用新的 SIP 域更新云连接器配置文件。
    
3. 申请新边缘外部证书与其他 SAN sip.domain 云连接器配置中定义的每个 SIP 域的名称。 
    
4. 按如下所述设置新边缘外部证书的路径：
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    通过运行以下 cmdlet 管理员 PowerShell 云连接器上删除站点中的每个装置的租户注册：
    
  ```
  Unregister-CcAppliance
  ```

6. 
    
    通过运行以下 cmdlet 在 Skype 业务在线 PowerShell 删除每个站点的站点注册：
    
  ```
  Remove-CsHybridPSTNSite
  ```

7. 
    
    通过运行以下 cmdlet 管理员 PowerShell 云连接器上卸载每个应用装置：
    
  ```
  Uninstall-CcAppliance
  ```

8. 
    
     通过运行以下 cmdlet 管理员 PowerShell 云连接器上注册每个应用装置：
    
  ```
  Register-ccAppliance
  ```

9. 
    
     安装每个设备，一个一个地，通过运行以下 cmdlet 管理员 PowerShell 云接头：
    
  ```
  Install-CcAppliance
  ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部边缘证书替换为一个新的证书
<a name="BKMK_UpdatePassword"> </a>

当您需要替换上云接口装置的外部边缘证书时，您需要获取新的边缘证书，准备包含私有密钥和整个证书链的 PFX 文件，然后执行下列每个装置上：
  
1. 通过使用 enter 键 CcUpdate cmdlet 装置置于维护模式。
    
2. 运行以下命令： 
    
  ```
  Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
  ```

3. 
    
    如果新证书的密码与旧相同，则导入将会成功。 如果密码不同，您将收到一个错误密码有误，并且您将需要重置密码，通过运行注册 CcAppliance cmdlet-本地参数，然后重复步骤 2。 
    
4. 使用退出 CcUpdate cmdlet 拍摄装置退出维护模式。
    

