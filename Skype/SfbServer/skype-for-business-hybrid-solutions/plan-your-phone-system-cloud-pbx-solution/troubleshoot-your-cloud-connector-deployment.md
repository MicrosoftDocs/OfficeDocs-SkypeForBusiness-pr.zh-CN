---
title: 对云连接器部署进行故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 对你的云连接器版本部署进行故障排除。
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220222"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>对云连接器部署进行故障排除
 
对你的云连接器版本部署进行故障排除。
  
本主题介绍云连接器版本部署的常见问题的解决方案。 如果在拨打公用电话交换网（PSTN）时遇到问题，可以按照本主题中所述的解决方案进行调查。
  
云连接器提供了用于自动解决某些问题的内置机制。 自动检测过程会查找云连接器设备的潜在问题，如果可能，则会采取纠正措施来解决这些问题，而无需管理员干预。 检测过程按如下方式工作：
  
- **检测序列：** 云连接器管理服务每60秒运行一次进程，以检测设备是否已关闭。 在云连接器版本2.0 及更高版本中，检测过程使用 Skype for Business 公司网络交换机建立到云连接器计算机的 PowerShell 连接;对于2.0 之前的版本，检测过程使用云连接器管理交换机。
    
    > [!NOTE]
    > 若要成功进行自动恢复，主机和虚拟机之间必须有主机网络交换机之间的网络连接。 请务必检查网络连接，以确保自动检测和恢复能够成功。 
  
- **监控：** 在云连接器版本2.0 和更高版本中监视以下服务：
    
  - 虚拟机未连接到云连接器企业或 Internet 虚拟交换机
    
  - 虚拟机处于 "已保存" 或 "已停止" 状态
    
  - 中央管理服务器服务：副本、主机
    
  - 中介服务器服务：副本、RTCSRV 和 MEDSVC
    
  - 边缘服务器服务：副本、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - 在边缘服务器上对 CS RTCSRV 禁用了入站防火墙规则，在中介服务器上的 CS RTCMEDSRV
    
    在云连接器1.4.2 版中，仅监视以下服务：
    
  - 中介服务器服务： RTCSRV 和 MEDSVC
    
  - 边缘服务器服务： RTCSRV
    
- **恢复过程：** 如果任何受监控的服务关闭，则会将设备标为关闭状态，并将其停止并标记为手动，直到解决所有问题。 这将阻止呼叫路由到可能导致呼叫故障的设备。
    
    云连接器管理服务将重试自动恢复，如下所示
    
  - 初始重试间隔为10秒，最长间隔时间为一小时。
    
  - 对于前三次恢复尝试，间隔时间为10秒。 从第四次重试开始，间隔时间将增加上一个间隔时间的两倍。 例如，第四次重试将在20秒内发生，第五次为40秒，依此类推。 
    
  - 当达到一个小时的最长间隔时间时，每小时的重试次数将继续进行一次。
    
  - 恢复成功后，间隔和重试次数将设置为其初始值。
    
  - 如果重新启动管理服务，则会将间隔和重试次数重置为其初始值。
    
## <a name="troubleshooting"></a>疑难解答

以下是经常遇到的问题的解决方案：
  
- **问题：运行部署脚本时，部署失败或停止响应。登录到每个 VM 后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**
    
    **解决方法：** 无法自动解决此问题。 Nic 在运行时无法添加到虚拟机。 请在 hyper-v 管理器中关闭并删除这些虚拟机，然后运行以下 cmdlet：
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**
    
    **解决方法：** 若要解决此问题，请执行以下步骤：
    
  - 登录到 Active Directory 服务器，并验证是否已正确创建域。
    
  - 登录到 CMS/中介服务器，并验证在 "企业网络 NIC" 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。
    
  - 登录到 CMS/中介服务器，打开命令提示符。 请确保您可以 ping Active Directory 服务器的 FQDN 和 IP 地址。 如果不能，则可能存在 IP 地址冲突。 请尝试为 Active Directory 分配新 IP 并相应更新 CMS/中介服务器上的 DNS。
    
- **问题：在删除虚拟以太网交换机时收到以下错误消息 "Remove-VMSwitch：失败"。无法删除虚拟交换机 "云连接器管理交换机"，因为它正在被运行虚拟机或分配到子池。 "**
    
    **解决方法：** 部署后，不会删除 "云连接器管理开关"。 如果遇到此错误，请转到 Hyper-v 管理器，并验证是否仍有虚拟机仍连接到它。 如果仍有虚拟机处于连接状态，请将其断开连接并删除管理交换机。 如果仍无法删除管理交换机，请重新启动主机服务器并重试。
    
- **问题：收到以下错误消息： "服务 RTCMRAUTH 无法启动。请进行检查以确保该服务未被禁用。**
    
    > [!NOTE]
    > 此问题仅适用于1.4.2 之前的云连接器版本。 
  
    启动失败也可能是因为此前端服务器以前故障转移（使用计算机故障转移）。 如果是这种情况，请调用故障回复（使用计算机故障回复）。
    
    **解决方法：** 如果边缘服务器不信任根 CA 证书或中间 CA 证书，则会在边缘服务器上发生此问题。 即使可以导入外部证书，但证书链已断开。 在此情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。
    
    请手动将外部证书的根 CA 证书和所有中间 CA 证书导入边缘服务器，然后重新启动边缘服务器。 在边缘服务器上看到 RTCMRAUTH 和 RTCSRV 服务启动后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以切换到新部署：
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **问题：应用 Windows 更新时主机服务器重新启动，并且由服务器提供服务的呼叫失败。**
    
    **解决方法：** 如果您部署了高可用性环境，Microsoft 将提供一个 cmdlet，以便在您手动检查和安装 Windows 更新时帮助将一台主机（部署实例）移入或移出当前拓扑。 使用以下步骤来实现此目的：
    
1. 在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：
    
   ```powershell
   Enter-CcUpdate
   ```

2. 检查并安装可用的更新程序。
    
3. 在 PowerShell 控制台中，运行以下 cmdlet：
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**
    
    **解决方法：** 若要解决此问题，请参阅[配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **问题：安装 Active Directory 服务器时显示有关 Windows 更新的警告消息-"未启用 Windows 自动更新。若要确保新安装的角色或功能自动更新，请打开 Windows Update。**
    
    **解决方法：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 以检查网站的_EnableAutoUpdate_配置：
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    如果将_EnableAutoUpdate_设置为**True**，则可以安全地忽略此警告消息，因为 CCEManagement 服务将处理为虚拟机和主机服务器下载和安装 Windows 更新。 如果_EnableAutoUpdate_设置为**False**，则运行以下 cmdlet 以将其设置为**True**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    或者，您也可以手动检查并安装更新。 请参阅下一部分。
    
- **问题：收到一条错误消息：无法注册设备，因为当前的输入/配置 \< SiteName \> 或 \< ApplianceName \> 或 \< 中介服务器 FQDN 或中介服务器 \> \< IP 地址 \> 与现有设备冲突。删除冲突设备或更新输入/配置信息，然后重新注册。' 在运行 Register-ccappliance 注册当前设备以供联机时。**
    
    **解决方法：**\<ApplianceName \> 、 \< 中介服务器 FQDN \> 和 \< 中介服务器 IP 地址的值 \> 必须是唯一的，并且仅用于一个设备注册。 默认情况下， \< ApplianceName 来自 \> 主机名称。 \<\> \< \> 在配置 ini 文件中定义的中介服务器 FQDN 和中介服务器 IP 地址。
    
    例如，使用（ApplianceName = MyserverNew，中介服务器 FQDN = 10.10.10.10，中介服务器 IP 地址 =）注册到 SiteName = 我的 SiteName，但如果有已注册的装置（ApplianceName = Myserver，中介服务器 FQDN =，中介服务器 IP 地址 = 10.10.10.10），则会发生冲突。
    
    首先，请检查 "ApplianceRoot 目录" 部分中的 "Cloudconnector.ini" 文件。 您将获得 \< \> 文件中的 SiteName、 \< 中介服务器 FQDN \> 和 \< 中介服务器 IP 地址 \> 值。 \<ApplianceName \> 是您的主机服务器名称。
    
    其次，使用你的 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 以检查注册的设备。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    在确定任何冲突之后，可以使用与注册设备匹配的信息更新 Cloudconnector.ini 文件，或注销现有设备以解决冲突。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **问题：如果在主机上运行已部署的设备，Get-ccrunningversion cmdlet 将返回空值。**
    
  **解决方法：** 从1.3.4 或1.3.8 升级到1.4.1 时，可能会发生这种情况。 在使用 .msi 安装版本1.4.1 之后，您必须 `Register-CcAppliance` 先运行任何其他 cmdlet，然后才能运行。 `Register-CcAppliance`会将%UserProfile%\CloudConnector 文件从迁移到%ProgramData%\CloudConnector。 如果你错过了它，将在%ProgramData%\CloudConnector 文件夹中创建一个新的 module，并替换1.3.4 或1.3.8 的运行/备份版本信息。
    
  比较%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 文件夹中的模块 .ini 文件。 如果存在差异，请删除%ProgramData%\CloudConnector 中的模块 .ini 文件，然后重新运行 `Register-CcAppliance` 。 您还可以手动将文件修改为正确的运行和备份版本。
    
- **问题：在运行 Switch-ccversion cmdlet 以切换到不同于当前脚本版本的旧版本之后，此旧版本不提供高可用性支持。**
    
    **解决方法：** 例如，您已从1.4.1 升级到1.4.2。 您的当前脚本版本（可通过运行 `Get-CcVersion` ）和运行版本（这两个版本都可以确定） `Get-CcRunningVersion` 。 此时，如果您运行以将 `Switch-CcVersion` 正在运行的版本切换回1.4.1，则此旧版本将不提供高可用性支持。
    
    若要获取完整的高可用性支持，请切换回1.4.2，以便运行版本和脚本版本相同。 如果您在1.4.2 部署中遇到问题，请尽快卸载并重新安装它。
    
- **问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已泄露。**
    
    **解决方法：** Skype for Business 证书颁发机构证书有效期为五年。 颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为两年。
    
    > [!NOTE]
    > 在云连接器版本2.0 及更高版本中，Renew-ccservercertificate cmdlet 已更改为 Renew-ccservercertificate，并且 Renew-cccacertificate cmdlet 已更改为更新-Renew-cccacertificate。 
  
    如果颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏，请运行 Renew-ccservercertificate 或 Renew-ccservercertificate cmdlet 来续订证书。
    
    如果证书颁发机构证书即将过期，请运行 Renew-cccacertificate 或 Renew-cccacertificate cmdlet 来续订证书。
    
    **如果证书颁发机构证书已损坏，并且站点中只有一台设备，请**执行以下步骤：
    
1. 运行 Enter-ccupdate cmdlet 以排出服务并将设备置于维护模式。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 运行以下 cmdlet 以重置并创建新的证书颁发机构证书和所有内部服务器证书：
    
    对于在2.0 之前的云连接器版本：
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    或云连接器版本2.0 及更高版本：
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 如果在网关和中介服务器之间使用 TLS，请从设备运行 Export-ccrootcertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 你可能还需要在你的网关上重新颁发证书。

   ```powershell
   Export-CcRootCertificate
   ```

4. 运行 Enter-ccupdate cmdlet 以启动服务并退出维护模式。

   ```powershell
   Exit-CcUpdate
   ```


    **如果证书颁发机构证书已损坏，并且站点中有多个设备，请**在站点中的每台设备上执行以下连续步骤。
    
    Microsoft 建议您在非高峰使用时间执行这些步骤。
    
1. 在第一个设备上，运行 Remove-cccertificationauthorityfile cmdlet 以清除 SiteRoot 目录中的 CA 备份文件 \< \> 。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 运行 Enter-ccupdate cmdlet 以排出服务并将每个设备置于维护模式。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 在第一个设备上，运行以下 cmdlet 以重置并创建新的证书颁发机构证书和所有内部服务器证书：
    
     对于在2.0 之前的云连接器版本：
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     或云连接器版本2.0 及更高版本：
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 在第一个设备上，运行以下 cmdlet 以将 CA 文件备份到 \< SiteRoot \> 文件夹。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 在同一站点中的所有其他设备上，运行以下命令以使用 CA 备份文件，这样设备将使用相同的根证书，然后请求新的证书。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 如果在网关和中介服务器之间使用 TLS，请在站点中的任何设备上运行 Export-ccrootcertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 你可能还需要在你的网关上重新颁发证书。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 运行 Enter-ccupdate cmdlet 以启动服务并退出维护模式。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **问题：在云连接器管理服务日志中收到以下错误消息： "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService 错误：0：将状态报告给 online 时出现意外异常：：用户 \< 全局租户管理员登录失败 \> 。请创建一个新的 credential 对象，确保您使用了正确的用户名和密码。---\>**
    
    **解决方法：** Microsoft 365 或 Office 365 全局租户管理员凭据在云连接器设备注册后进行了更改。 若要在云连接器设备上更新本地存储的凭据，请从主机设备上的管理员 PowerShell 中运行以下命令：
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **问题：在您更改用于部署的主机服务器帐户的密码之后，您会收到以下错误消息： "ConvertTo-SecureString：密钥在指定状态下使用时无效。" 在%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log 或运行 Set-cccredential cmdlet 时使用。**
    
    **解决方法：** 所有云连接器凭据都存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml \<CurrentUser \> "。 当主机服务器上的密码更改时，您将需要更新本地存储的凭据。
    
    **如果您运行的是云连接器1.4.2 版，请**通过执行以下步骤来重新生成所有云连接器密码：
    
  1. 重新启动主机服务器。
    
  2. 删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml \<CurrentUser \> "。
    
  3. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。 输入您在云连接器部署之前输入的相同密码。
    
     **如果您运行的是云连接器版本2.0 或更高版本，请**通过执行以下步骤来重新生成所有云连接器密码：
    
  4. 重新启动主机服务器。
    
  5. 删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml \<CurrentUser \> "。
    
  6. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。 
    
     如果缓存的密码文件是使用云连接器1.4.2 版生成的，则在收到提示时，请使用 CceService 密码的 VMAdmin 密码。 输入您在云连接器部署之前为所有其他帐户输入的相同密码。
    
     如果缓存的密码文件是使用云连接器1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：
    
  7. 运行 Set-cccredential-AccountType DomainAdmin，如下所示：
    
  8. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
  9. 当系统提示输入新帐户凭据时，请输入您之前使用的 DomainAdmin 密码的密码。
    
     如果缓存的密码文件是使用云连接器版本2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：
    
  10. 运行 Set-cccredential-AccountType DomainAdmin，如下所示：
    
       1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据
    
       2. 当系统提示输入新帐户凭据时，请输入您之前使用的 DomainAdmin 密码的密码。
    
  11. 运行 Set-cccredential-AccountType VmAdmin，如下所示：
    
       1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据
    
       2. 当系统提示输入新帐户凭据时，请输入您之前使用的 VmAdmin 密码的密码。 
    
- **问题：在云连接器版本2.1 及更高版本中，在设备上运行 Register-ccappliance 或其他 cmdlet 时，会收到一条错误消息，例如： "对于每个对象：在此对象上找不到属性 ' Common '。验证该属性是否存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**
    
    **解决方法：** 云连接器2.1 及更高版本需要 .NET Framework 4.6.1 或更高版本。 请将设备上的 .NET Framework 更新为版本4.6.1 或更高版本，然后再次运行 cmdlet。

- **问题：使用云连接器版本2.1 时，在运行 Register-ccappliance 时，您会收到一条错误消息，例如： "未能安装新实例，出现错误：无法设置" State "，因为只有字符串可用作值来设置 XmlNode 属性"**

   **解决方法：** 在 Cloudconnector.ini 中的 [Common] 部分下，请添加 "State" config，如下所示： CountryCode = US State = WA City = Redmond

   "State" 行不是必需的，但不能从 Cloudconnector.ini 文件中删除 "State" 行。

- **问题：收到以下错误消息 "Dismount-windowsimage：卸载-Dismount-windowsimage 失败。错误代码 = 0xc1550115 "安装或升级云连接器版本时"。**
    
    **解决方法：** 以管理员身份启动 PowerShell 控制台，请运行 "DISM-清理-Wim" "。 这将清除所有 troubled 图像。 再次运行安装-Register-ccappliance 或等待 bits 自动升级。
    
- **问题：在 HA 环境中部署第一个云连接器设备失败**
    
    **解决方法：** 您执行的步骤取决于部署失败的原因：
    
  - 如果第一个云连接器设备出现故障，并且您无法确定故障原因，则必须重新安装该设备，直到部署成功，然后再安装其他设备。
    
  - 如果第一个云连接器设备出现问题，如外部证书问题，则可能能够在不重新安装设备的情况下解决问题。 然后，可以使用租户远程 PowerShell 将部署标记为成功，如下所示。 （如果首次部署成功，则也可以使用以下步骤，但出于某种原因，云连接器无法报告部署成功。）
    
  - 若要获取第一个云连接器设备的标识（GUID），请运行 CsHybridPSTNAppliance cmdlet。
    
  - 若要将设备标记为已成功部署，请运行 CsCceApplianceDeploymentStatus，如下所示：
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**
    
   **解决方法：** 我们建议您利用由 Skype for Business 云连接器版本提供的自动 OS 更新。 在为联机管理注册设备并启用自动 OS 更新之后，主机服务器和虚拟机将根据 OS update time window 设置自动检查并安装 Windows 更新。
    
   如果你需要手动检查并安装 Windows 更新，请按照本节中适用于你的部署类型的步骤进行操作。 您应规划同时更新主机服务器和同时在其上运行的虚拟机，以最大限度地减少更新所需的停机时间量。
    
   如果你愿意，可以使用 Windows Server Update Services （WSUS）服务器来提供云连接器服务器的更新。 只需确保将 Windows 更新配置为**不**自动安装。
    
   有关如何手动更新云连接器部署的信息，请参阅下一节。
    
- **问题：当云连接器更新新版本时，将不会更新云连接器 cmdlet。** 如果在自动更新发生时，PowerShell 窗口保持打开，有时会发生这种情况。
    
  **解决方法：** 若要加载更新的 cmdlet，您可以执行以下任一步骤：
    
   - 在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。
    
     - 或者，您可以运行导入模块 Cloudconnector.ini。 
 
-   **问题： "无法将术语" Start-cswindowsservice "识别为 cmdlet、函数、脚本文件或可运行程序的名称。尝试运行 Enter-ccupdate cmdlet 时出错。**

    **解决方法：** 删除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。
PowerShell 将此文件创建为它所发现的模块中的 cmdlet 的缓存，以便无需每次都重新分析所有模块，因为这样做会导致某些事情变得非常慢。 大多数情况下，在从缓存中读取时，会有一些文件损坏向 PowerShell 提供误导性结果。

-   **问题： "Import-Module Cloudconnector.ini" 生成错误 "Import-Module：未加载指定的模块" Cloudconnector.ini "，因为在任何模块目录中都找不到有效的模块文件"**

    **解决方案：**
    - 验证 Cloudconnector.ini 模块是否确实存在于 c:\Program Files\WindowsPowerShell\Modules 下。
    
    - 在验证 Cloudconnector.ini 模块位于此位置下后，可以更改存储模块位置的 PSModulePath 环境变量：
    
     a. 临时更改：以管理员身份启动 Powershell 并运行以下命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 对于 "永久更改"，以管理员身份启动 PowerShell 并运行以下命令之一： $CurrentValue = [环境]：： GetEnvironmentVariable （"PSModulePath"，"Machine"） SetEnvironmentVariable （"PSModulePath"，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine "）

    
## <a name="install-windows-updates-manually"></a>手动安装 Windows 更新

如果您不想在您的环境中使用自动更新，请按照以下步骤手动检查并应用 Windows 更新。 检查并安装 Windows 更新可能需要重新启动服务器。 当主机服务器重新启动时，用户将无法使用云连接器发出或接收呼叫。 您可以手动检查并安装更新，以控制更新发生的时间，然后根据需要在选择的时间内重新启动计算机，以避免服务中断。
  
若要手动检查更新，请连接到每台主机服务器并打开 "**控制面板"**。 选择 "**系统和安全" " \> Windows 更新**"，然后根据您的环境相应地管理更新和服务器重新启动。
  
- 如果站点中只有一个设备，请连接到每个虚拟机，然后打开 "**控制面板"**。 选择 "**系统和安全" " \> Windows 更新**"，然后根据需要配置更新和服务器重新启动。
    
- 如果站点中有多个设备，则在更新过程中用户无法访问正在更新和重新启动的实例。 在更新完成后，用户将连接到部署中的其他实例，直到所有虚拟机和所有 Skype for Business 服务在虚拟机上启动。 为避免任何潜在的服务中断，可以在应用更新时从 HA 中删除该实例，然后在完成后将其还原。 为此，请执行以下操作：
    
1. 在每台主机服务器上，以管理员身份打开 PowerShell 控制台。
    
2. 使用以下 cmdlet 从 HA 中删除实例：
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    按照单个实例的步骤操作，手动应用更新并重新启动虚拟机。
    
4. 使用以下 cmdlet 将实例设置回 HA：
    
   ```powershell
   Exit-CcUpdate
   ```

对于多站点部署，请遵循部署中每个站点的单个站点的步骤，同时将更新应用到一个站点。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在云连接器主机计算机上安装防病毒软件的提示

如果需要在云连接器主机上安装防病毒软件，则需要添加以下排除项：
  
- 每台计算机上的本地设备目录。
    
- 每台计算机上的远程网站目录。
    
- 计算机上的本地网站目录承载共享网站根文件夹。
    
- 适用于商业云连接器版本的%ProgramFiles%\Skype
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- "处理管理" 中。
