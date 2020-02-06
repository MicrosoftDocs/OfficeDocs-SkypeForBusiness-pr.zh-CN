---
title: 云连接器部署故障排除
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
description: 对云连接器版本部署进行故障排除。
ms.openlocfilehash: 3a6fd80cc0c4125303021746cdb626d8c5b49a5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814220"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>云连接器部署故障排除
 
对云连接器版本部署进行故障排除。
  
本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。
  
云连接器提供了用于自动解决某些问题的内置机制。 自动检测过程查找云连接器设备的潜在问题，如果可能，请采取纠正措施来解决这些问题，而无需管理员干预。 检测过程工作方式如下：
  
- **检测序列：** 云连接器管理服务每隔60秒运行一次进程，用于检测装置是否已停机。 在云连接器版本2.0 和更高版本中，检测过程使用 Skype for Business 的企业版企业版交换连接到云连接器计算机;对于2.0 之前的版本，检测过程使用云连接器管理开关。
    
    > [!NOTE]
    > 若要自动恢复成功，主机和虚拟机之间必须具有通过主机网络交换机的网络连接。 请确保检查网络连接，以确保自动检测和恢复能够成功。 
  
- **监视：** 在云连接器版本2.0 和更高版本中监视以下服务：
    
  - 虚拟机未连接到云连接器企业或 Internet 虚拟交换机
    
  - 虚拟机处于已保存或已停止状态
    
  - 中央管理服务器服务：副本、主机
    
  - 中介服务器服务：副本、RTCSRV 和 MEDSVC
    
  - 边缘服务器服务：副本、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - 在 Edge 服务器上为 CS RTCSRV 禁用入站防火墙规则，在中介服务器上的 CS RTCMEDSRV
    
    在云连接器版本1.4.2 中，仅监视以下服务：
    
  - 中介服务器服务： RTCSRV 和 MEDSVC
    
  - Edge 服务器服务： RTCSRV
    
- **恢复过程：** 如果任何监视的服务已关闭，则会将设备标记为已关闭，并且服务将停止并标记为手动，直到解决所有问题。 这将阻止呼叫路由到可能导致呼叫失败的装置。
    
    云连接器管理服务将重试自动恢复，如下所示
    
  - 初始重试间隔是每隔十秒，最大间隔时间为一小时。
    
  - 对于前三次恢复尝试，间隔时间为10秒。 从第四个重试开始，间隔时间将增加上一个间隔时间的两倍。 例如，第四次重试将在20秒内发生，第五个在40秒中，依此类推。 
    
  - 当达到一小时的最大间隔时间时，每小时的重试将继续。
    
  - 恢复成功后，"间隔" 和 "重试次数" 将设置为初始值。
    
  - 如果重新启动管理服务，则会将 "间隔" 和 "重试计数" 重置为其初始值。
    
## <a name="troubleshooting"></a>疑难解答

以下是经常遇到的问题的解决方案：
  
- **问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**
    
    **解决方案：** 无法自动解决此问题。 Nic 在运行时不能添加到 Vm。 请在 hyper-v 管理器中关闭并删除这些 Vm，然后运行以下 cmdlet：
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**
    
    **解决方法：** 要解决此问题，请执行以下步骤：
    
  - 登录 Active Directory 服务器并验证是否已正确创建域。
    
  - 登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。
    
  - 登录到 CMS/中介服务器，然后打开命令提示符。 确保可以 ping Active Directory 服务器的 FQDN 和 IP 地址。 如果不可以，则可能存在 IP 地址冲突。 请尝试为 Active Directory 分配新 IP 并相应更新 CMS/中介服务器上的 DNS。
    
- **问题：在删除虚拟以太网交换机时收到以下错误消息 "Remove-VMSwitch：" 失败。无法删除虚拟交换机 "云连接器管理开关"，因为它正被运行虚拟机或分配到子池。 "**
    
    **解决方案：** 部署后，"云连接器管理开关" 未被删除。 如果你遇到此错误，请转到 Hyper-v 管理器并验证是否仍有虚拟机仍连接到它。 如果存在仍连接的虚拟机，请将其断开连接并删除管理交换机。 如果仍然无法删除管理开关，请重新启动主机服务器，然后重试。
    
- **问题：收到以下错误消息： "服务 RTCMRAUTH 无法启动。检查以确保该服务未禁用。 "**
    
    > [!NOTE]
    > 此问题仅适用于1.4.2 以前的云连接器版本。 
  
    无法启动也可能是因为此前端服务器之前经过故障转移（使用计算机故障转移）。如果是这种情况，请调用故障回复（使用计算机故障回复）。
    
    **解决方法：** 当边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会出现此问题。即使可以导入外部证书，但证书链已损坏。在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。
    
    请手动将外部证书的根 CA 证书和所有中间 CA 证书导入到边缘服务器，然后重新启动边缘服务器。看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动之后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以便切换到新部署：
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **问题：应用 Windows 更新时主机服务器重新启动，由此服务器支持的调用失败。**
    
    **解决方法：** 如果你已部署高可用性环境，Microsoft 提供的 cmdlet 可以帮助你在手动检查和安装 Windows 更新时将一台主机（部署实例）移入或移出当前拓扑。要完成此操作，请执行以下步骤：
    
1. 在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：
    
   ```powershell
   Enter-CcUpdate
   ```

2. 检查更新并安装所有可用更新。
    
3. 在 PowerShell 控制台中，运行以下 cmdlet：
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**
    
    **解决方案：** 若要解决此问题，请参阅[配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**
    
    **解决方案：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 检查网站的_EnableAutoUpdate_配置：
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    如果_EnableAutoUpdate_设置为**True**，则可以安全地忽略此警告消息，因为 CCEManagement 服务将为虚拟机和主机服务器处理下载和安装 Windows 更新。 如果_EnableAutoUpdate_设置为**False**，请运行以下 cmdlet 以将其设置为**True**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    此外，你还可以手动检查并安装更新。 请参阅下节内容。
    
- **问题：收到一条错误消息：无法注册装置，因为当前输入/配置\<SiteName\>或\<ApplianceName\>或\<中介服务器 FQDN\>或\<中介服务器 IP 地址\>与现有装置相冲突。删除冲突装置或更新输入/配置信息，然后再次注册。' 当运行 Register-CcAppliance 将当前装置注册到联机时。**
    
    **解决方案：**\<\>ApplianceName、 \<中介服务器\> FQDN 和\<中介服务器 IP 地址\>的值必须是唯一的，并且仅用于一个装置注册。 默认情况下\<，\> ApplianceName 来自主机名。 \<在配置 ini\>文件\<中定义的中介\>服务器 FQDN 和中介服务器 IP 地址。
    
    例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。
    
    首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。 你将获得\<文件\>中\<的 SiteName、\>中介\<服务器 FQDN 和中介\>服务器 IP 地址值。 \<ApplianceName\>是你的主机服务器名称。
    
    其次，使用您的 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 以检查已注册的装置。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **问题：如果在主机上运行了已部署的装置，则 CcRunningVersion cmdlet 将返回空值。**
    
  **解决方案：** 从1.3.4 或1.3.8 升级到1.4.1 时，可能会发生这种情况。 在安装1.4.1 版本的版本后，必须在运行任何其他`Register-CcAppliance` cmdlet 之前运行。 `Register-CcAppliance`会将%UserProfile%\CloudConnector 文件从迁移到%ProgramData%\CloudConnector。 如果错过了它，将在%ProgramData%\CloudConnector 文件夹中创建新的 module .ini，并替换1.3.4 或1.3.8 的运行/备份版本信息。
    
  比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。 如果存在差异，请在%ProgramData%\CloudConnector 中删除 module 文件，然后重新运行`Register-CcAppliance`。 您也可以将文件手动修改为正确运行和备份的版本。
    
- **问题：运行 CcVersion cmdlet 以切换到不同于当前脚本版本的旧版本时，此旧版本不提供任何高可用性支持。**
    
    **解决方案：** 例如，您已从1.4.1 升级到1.4.2。 你的当前脚本版本（可以通过运行`Get-CcVersion`）和运行版本（这两个版本都`Get-CcRunningVersion`是1.4.2）确定。 此时，如果你运行`Switch-CcVersion`以将运行版本切换回1.4.1，则此旧版本不提供任何高可用性支持。
    
    要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。
    
- **问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**
    
    **解决方法：** Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。
    
    > [!NOTE]
    > 在云连接器版本2.0 和更高版本中，CcServerCertificate cmdlet 已更改为更新-CcServerCertificate，续订 CcCACertificate cmdlet 已更改为 "更新-CcCACertificate"。 
  
    如果向中央管理存储、中介服务器和边缘服务器颁发的内部证书即将到期或遭到破坏，请运行 CcServerCertificate 或 CcServerCertificate cmdlet 续订你的证书。
    
    如果证书颁发机构证书即将到期，请运行 CcCACertificate 或 CcCACertificate cmdlet 续订你的证书。
    
    **如果证书颁发机构证书遭到破坏，并且站点中只有一个装置，请**执行以下步骤：
    
1. 运行 Enter-CcUpdate cmdlet 以排出服务并将该设备置于维护模式。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：
    
    对于在2.0 之前的云连接器版本：
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    或者对于云连接器版本2.0 和更高版本，请执行以下操作：
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 如果在网关和中介服务器之间使用 TLS，请从设备运行 CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 您可能还需要重新签发您的网关的证书。

   ```powershell
   Export-CcRootCertificate
   ```

4. 运行 CcUpdate cmdlet 以启动服务并退出维护模式。

   ```powershell
   Exit-CcUpdate
   ```


    **如果证书颁发机构证书遭到破坏，并且站点中有多个装置，请**在站点中的每个设备上执行以下顺序步骤。
    
    Microsoft 建议你在非高峰使用时间内执行这些步骤。
    
1. 在第一个设备上，运行 CcCertificationAuthorityFile cmdlet 以清理\<SiteRoot\>目录中的 CA 备份文件。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 运行 CcUpdate cmdlet 以排出服务并将每台装置置于维护模式。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 在第一个设备上，运行以下 cmdlet 以重置和创建新的证书颁发机构证书和所有内部服务器证书：
    
     对于在2.0 之前的云连接器版本：
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     或者对于云连接器版本2.0 和更高版本，请执行以下操作：
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 在第一个设备上，运行以下 cmdlet 以将 CA 文件备份到\<SiteRoot\>文件夹。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 在同一网站中的所有其他设备上，运行以下命令以使用 CA 备份文件，以便所有设备都使用相同的根证书，然后请求新的证书。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 如果在网关和中介服务器之间使用 TLS，请从网站中的任何设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 您可能还需要重新签发您的网关的证书。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 运行 CcUpdate cmdlet 以启动服务并退出维护模式。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **问题：在云连接器管理服务日志中收到以下错误消息： "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService 错误：0：将状态报告为 online 时出现意外异常：：为用户\<全局租户管理员\>登录失败。请创建一个新的凭据对象，确保您使用了正确的用户名和密码。---\>**
    
    **解决方案：** Office 365 全局租户管理员凭据在注册云连接器设备后已更改。 若要在云连接器装置上更新本地存储的凭据，请在主机设备上从管理员 PowerShell 中运行以下操作：
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **问题：更改用于部署的主机服务器帐户的密码后，收到以下错误消息： "ConvertTo-SecureString： Key 不适合在指定状态下使用。" 在%ProgramFiles%\Skype for Business Cloud Connector 中使用Edition\ManagementService\CceManagementService.log 或运行 CcCredential cmdlet 时运行。**
    
    **解决方案：** 所有云连接器凭据均存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。 当主机服务器上的密码更改时，需要更新本地存储的凭据。
    
    **如果你运行的是云连接器 1.4.2 版，** 请通过执行以下步骤来重新生成所有云连接器密码：
    
  1. 重新启动主机服务器。
    
  2. 删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。
    
  3. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。 输入之前输入的用于云连接器部署的相同密码。
    
     **如果你运行的是云连接器版本2.0 或更高版本，请**按照以下步骤重新生成所有云连接器密码：
    
  4. 重新启动主机服务器。
    
  5. 删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。
    
  6. 以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。 
    
     如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。
    
     如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：
    
  7. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
  8. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
  9. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
     如果缓存的密码文件是使用云连接器版本2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：
    
  10. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
       1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
       2. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
  11. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
       1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
       2. 当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。 
    
- **问题：使用云连接器版本2.1 和更高版本时，在设备上运行 Register-CcAppliance 或其他 cmdlet 时，将收到一条错误消息，如： "对于每个对象：在此对象上找不到属性" Common "。验证该属性是否存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**
    
    **解决方案：** 云连接器2.1 及更高版本需要 .NET Framework 4.6.1 或更高版本。 请将设备上的 .NET Framework 更新到版本4.6.1 或更高版本，然后再次运行 cmdlet。

- **问题：使用云连接器 Edition 2.1 时，你将收到一条错误消息，如下所示： "未能安装新实例，出现错误：无法设置" State "，因为只有字符串可以用作值来设置 XmlNode 属性"**

   **解决方案：** 在 Cloudconnector 中的 "[Common]" 部分下，请添加 "State" config，如下所示： CountryCode = US State = WA 市 = Redmond

   不强制 "State" 行具有值，但无法从 Cloudconnector 文件中删除 "State" 行。

- **问题：收到以下错误消息 "卸载-WindowsImage：卸载-WindowsImage 失败。安装或升级云连接器版本时出现错误代码 = 0xc1550115 "错误代码 ="。**
    
    **解决方案：** 以管理员身份启动 PowerShell 控制台，请运行 "DISM 清理-Wim"。 这将清理所有 troubled 图像。 再次运行安装-CcAppliance 或等待 bits 自动升级。
    
- **问题：在 HA 环境中部署第一个云连接器设备失败**
    
    **解决方案：** 所采取的步骤取决于部署失败的原因：
    
  - 如果第一个云连接器装置出现故障，而你无法确定失败的原因，则必须再次安装该装置，直到部署成功，然后再安装其他设备。
    
  - 如果第一个云连接器设备在出现小问题（如外部证书问题）时失败，则可以在不重新安装设备的情况下修复该问题。 然后，你可以使用租户远程 PowerShell 将部署标记为成功，如下所示。 （如果第一个部署成功，但由于某些原因，云连接器无法将部署报告为成功，也可以使用以下步骤。）
    
  - 若要获取第一个云连接器设备的标识（GUID），请运行 CsHybridPSTNAppliance cmdlet。
    
  - 要将设备标记为已成功部署，请按如下方式运行 CsCceApplianceDeploymentStatus：
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**
    
   **解决方法：** 建议你利用 Skype for Business 云连接器版本提供的操作系统自动更新。当设备经过注册以实现联机管理并且启用了操作系统自动更新之后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查并安装 Windows 更新。
    
   如果你需要手动检查并安装 Windows 更新，请按照本节提供的适用于你的部署类型的步骤操作。你需要同时规划主机服务器及其上运行的虚拟机的更新，以便尽可能降低更新所需要的总停机时间。
    
   如果你愿意，可以使用 Windows Server 更新服务 (WSUS) 服务器向云连接器服务器提供更新。只需确保将 Windows 更新配置为**不要**自动安装即可。
    
   有关如何手动更新云连接器部署的信息，请参阅下节。
    
- **问题：当云连接器更新新版本时，不会更新云连接器 cmdlet。** 如果在自动更新发生时，PowerShell 窗口保持打开，有时会发生这种情况。
    
  **解决方案：** 若要加载更新的 cmdlet，可以执行以下任一步骤：
    
   - 在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。
    
     - 或者，你可以运行 Import-Module CloudConnector。 
 
-   **问题： "无法将术语" Stop-CsWindowsService "识别为 cmdlet、函数、脚本文件或可运行程序的名称。尝试运行 CcUpdate cmdlet 时出错。**

    **解决方案：** 删除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。
PowerShell 将此文件创建为它所发现的模块中的 cmdlet 的缓存，这样就不必每次重新分析所有模块，因为这样做会非常慢。 在从该缓存中读取时，很可能是出现了一些文件损坏，可向 PowerShell 提供误导性结果。

-   **问题： "Import-Module CloudConnector" 生成错误 "Import-模块：未加载指定的模块" CloudConnector "，因为在任何模块目录中都找不到有效的模块文件"**

    **解决方法：**
    - 验证在 c:\Program Files\WindowsPowerShell\Modules 下确实存在 CloudConnector 模块
    
    - 验证 CloudConnector 模块存在于此位置下后，可以更改存储模块位置的 PSModulePath 环境变量：
    
     a. 临时更改：以管理员身份启动 Powershell，并运行以下命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 对于永久更改，以管理员身份启动 PowerShell，并逐个运行以下命令： $CurrentValue = [环境]：： GetEnvironmentVariable （"PSModulePath"、"Machine"） SetEnvironmentVariable （"PSModulePath"，"Machine"）（""，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine "）

    
## <a name="install-windows-updates-manually"></a>手动安装 Windows 更新

如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。 检查并安装 Windows 更新可能需要重新启动服务器。 当主机服务器重新启动时，用户将无法使用云连接器进行呼叫或接收呼叫。 你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。
  
要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。 选择 "**系统和\>安全 Windows 更新**"，然后根据你的环境相应地管理更新和服务器重启。
  
- 如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。 选择 "**系统和\>安全 Windows 更新**"，然后根据需要配置更新和服务器重启。
    
- 如果站点中有多个设备，更新期间用户将无法访问正在更新和重新启动的实例。用户将连接到部署中的其他实例，直到更新完成后所有虚拟机及虚拟机上的所有 Skype for Business 服务启动为止。为避免任何潜在的服务中断，可以在应用更新时从 HA 删除实例，然后在完成后将其还原。为此：
    
1. 在每台主机服务器上，以管理员身份打开 PowerShell 控制台。
    
2. 使用以下 cmdlet 从 HA 删除实例：
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    按照适用于单个实例的步骤，手动应用更新并重新启动虚拟机。
    
4. 使用以下 cmdlet 将实例重新设置为 HA：
    
   ```powershell
   Exit-CcUpdate
   ```

对于多站点部署，请为部署中的每个站点执行适用于单个站点的步骤，每次向一个站点应用更新。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在云连接器主机计算机上安装防病毒软件时的提示

如果需要在云连接器主机上安装防病毒软件，您需要添加以下排除项：
  
- 每台计算机上的本地装置目录。
    
- 每台计算机上的远程网站目录。
    
- 计算机上的本地网站目录托管了共享网站根文件夹。
    
- %ProgramFiles%\Skype for Business 云连接器版
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 进程 Microsoft .aspx. ManagementService。
