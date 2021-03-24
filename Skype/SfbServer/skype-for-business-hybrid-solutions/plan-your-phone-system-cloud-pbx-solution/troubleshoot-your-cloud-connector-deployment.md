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
description: 云连接器版本部署疑难解答。
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094820"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>对云连接器部署进行故障排除

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)
 
云连接器版本部署疑难解答。
  
本主题介绍云连接器版本部署常见问题的解决方案。 如果在呼叫公用电话交换网 (PSTN) 时遇到问题，可以按照本主题中所述的解决方案进行调查。
  
云连接器提供自动解决某些问题的内置机制。 自动检测过程会查找云连接器设备的潜在问题，如果可能，采取纠正措施来解决这些问题，而无需管理员干预。 检测过程的工作方式如下：
  
- **检测序列：** 云连接器管理服务每 60 秒运行一个进程，以检测设备是否关闭。 在云连接器 2.0 版和更高版本中，检测过程使用 Skype for Business Corpnet 开关建立与云连接器计算机之间的 PowerShell 连接;对于 2.0 以前的版本，检测过程使用云连接器管理开关。
    
    > [!NOTE]
    > 若要成功进行自动恢复，主机和虚拟机之间必须通过主机网络交换机建立网络连接。 请务必检查网络连接，以确保自动检测和恢复可以成功。 
  
- **监视：** 在云连接器 2.0 版和更高版本中监视以下服务：
    
  - 虚拟机未连接到云连接器公司或 Internet 虚拟交换机
    
  - 虚拟机已保存或已停止状态
    
  - 中央管理服务器服务：REPLICA、MASTER
    
  - 中介服务器服务：REPLICA、RTCSRV 和 MEDSVC
    
  - 边缘服务器服务：REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - 在边缘服务器上为 CS RTCSRV 禁用入站防火墙规则，在中介服务器上禁用 CS RTCMEDSRV
    
    在云连接器版本 1.4.2 中，仅监视以下服务：
    
  - 中介服务器服务：RTCSRV 和 MEDSVC
    
  - 边缘服务器服务：RTCSRV
    
- **恢复过程：** 如果任何受监视的服务关闭，设备将标记为关闭，服务将停止并标记为手动，直到可以解决所有问题。 这将阻止呼叫路由到可能导致呼叫失败的设备。
    
    云连接器管理服务将重试自动恢复，如下所示
    
  - 初始重试间隔是十秒，最大间隔时间为一小时。
    
  - 对于前三次恢复尝试，间隔时间为 10 秒。 从第四次重试开始，间隔时间将增加上一间隔时间两倍。 例如，第四次重试将在 20 秒后发生，第五次重试将在 40 秒后发生，以此类举。 
    
  - 当达到 1 小时的最大间隔时间时，重试将继续每小时一次。
    
  - 恢复成功后，间隔和重试次数将设置为初始值。
    
  - 如果重新启动管理服务，则时间间隔和重试次数将重置为初始值。
    
## <a name="troubleshooting"></a>疑难解答

以下是常见问题的解决方案：
  
- **问题：运行部署脚本时部署失败或停止响应。登录到每个 VM 后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**
    
    **解决方法：** 此问题无法自动解决。 NIC 无法添加到 VM 运行时。 请在 hyper-v 管理器中关闭并删除这些 VM，然后运行以下 cmdlet：
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**
    
    **解决方法：** 若要解决此问题，请执行以下步骤：
    
  - 登录到 Active Directory 服务器并验证域是否创建正确。
    
  - 登录到 CMS/中介服务器，并验证在公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。
    
  - 登录到 CMS/中介服务器，然后打开命令提示符。 确保可以 ping Active Directory 服务器的 FQDN 和 IP 地址。 如果无法，则可能是 IP 地址冲突。 请尝试为 Active Directory 分配新 IP，并相应地更新 CMS/中介服务器的 DNS。
    
- **问题：您收到以下错误消息："Remove-VMSwitch ： Failed while removing virtual Ethernet switch.无法删除虚拟交换机"云连接器管理交换机"，因为它正由运行虚拟机使用或分配给子池。"**
    
    **解决方法：** 部署后未删除"云连接器管理交换机"。 如果发生此错误，请转到 Hyper-v 管理器并验证是否仍有虚拟机仍连接到它。 如果仍有虚拟机连接，请断开它们连接并删除管理开关。 如果仍然无法删除管理交换机，请重新启动主机服务器并重试。
    
- **问题：收到以下错误消息："服务 RTCMRAUTH 无法启动。检查以确保服务未禁用。"**
    
    > [!NOTE]
    > 此问题仅适用于早于 1.4.2 的云连接器版本。 
  
    启动失败还可能是因为此前端服务器之前已故障转移到 (计算机故障转移) 。 如果是这种情况，请使用计算机故障回复 (调用故障回复) 。
    
    **解决方法：** 边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会发生此问题。 即使可以导入外部证书，但证书链断开。 在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。
    
    请手动将外部证书的根 CA 证书和所有中间 CA 证书导入边缘服务器，然后重新启动边缘服务器。 在看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动后，返回到主机服务器，以管理员角色启动 PowerShell 控制台，然后运行以下 cmdlet 以切换到新部署：
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **问题：应用 Windows 更新时主机服务器已重新启动，并且由服务器服务的呼叫失败。**
    
    **解决方法：** 如果部署了高可用性环境，Microsoft 将提供一个 cmdlet 来帮助在手动检查和安装 Windows 更新时将一台主机 (部署实例) 移入或退出当前拓扑。 若要完成此操作，请执行以下步骤：
    
1. 在主机服务器上，以管理员角色启动 PowerShell 控制台，然后运行：
    
   ```powershell
   Enter-CcUpdate
   ```

2. 检查更新并安装任何可用更新。
    
3. 在 PowerShell 控制台中，运行以下 cmdlet：
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **问题：使用 PSTN 号码从 Skype for Business 客户端发出呼叫时，无法通过邀请其他 PSTN 号码将呼叫提升为会议。**
    
    **解决方法：** 若要解决此问题，请参阅配置 [联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **问题：安装 Active Directory 服务器时，会显示有关 Windows 更新的警告消息 -"未启用 Windows 自动更新。若要确保新安装的角色或功能自动更新，请打开 Windows 更新。"**
    
    **解决方法：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 检查站点的 _EnableAutoUpdate_ 配置：
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    如果  _EnableAutoUpdate_ 设置为 **True，** 可以安全地忽略此警告消息，因为 CCEManagement 服务将同时为虚拟机和主机服务器处理 Windows 更新的下载和安装。 如果  _EnableAutoUpdate_ 设置为 **False**，请运行以下 cmdlet 以将设置为 **True**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    或者，可以手动检查并安装更新。 请参阅下一部分。
    
- **问题：收到错误消息：无法注册设备，因为当前输入/配置或与设备 \<SiteName\> (\<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 冲突) 。删除冲突设备或更新输入/配置信息，然后重新注册。在运行 Register-CcAppliance将当前设备注册到联机时。**
    
    **解决方法：**\<ApplianceName\>和 的值 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 必须是唯一的，并且仅用于一个设备注册。 默认情况下， \<ApplianceName\> 来自主机名。 \<Mediation Server FQDN\> 和 \<Mediation Server IP Address\> 在配置 ini 文件中定义。
    
    例如，使用 (ApplianceName= MyserverNew、中介服务器 FQDN=ms.contoso.com、 要注册到 SiteName=MySite 的中介服务器 IP Address=10.10.10.10) ，但如果存在注册设备 (ApplianceName= Myserver、中介服务器 FQDN=ms.contoso.com、中介服务器 IP Address=10.10.10.10) ，则存在冲突。
    
    首先，请检查 ApplianceRoot CloudConnector.ini部分中的文件。 你将在 \<SiteName\> \<Mediation Server FQDN\> 文件中 \<Mediation Server IP Address\> 获取 和 值。 \<ApplianceName\> 是主机服务器名称。
    
    其次，使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 检查注册 (设备) 。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    识别任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或者注销现有设备以解决冲突。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **问题：如果Get-CcRunningVersion已部署的设备，则此 cmdlet 将返回空值。**
    
  **解决方法：** 从 1.3.4 或 1.3.8 升级到 1.4.1 时，可能会发生这种情况。 使用 .msi 安装版本 1.4.1 后，必须先运行 ，然后才能运行任何其他 `Register-CcAppliance` cmdlet。 `Register-CcAppliance` 将文件module.ini %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。 如果你错过它，将在 %ProgramData%\CloudConnector 文件夹中module.ini一个新的数据库，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。
    
  比较module.ini %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的文件。 如果存在差异，请删除 %ProgramData%\CloudConnector module.ini文件，然后重新运行  `Register-CcAppliance` 。 您还可以手动将该文件修改为正确的运行和备份版本。
    
- **问题：运行 Switch-CcVersion cmdlet 以切换到与当前脚本版本不同的旧版本后，此旧版本没有高可用性支持。**
    
    **解决方法：** 例如，您从 1.4.1 升级到 1.4.2。 当前脚本版本（可通过运行 确定）和正在运行的版本（可通过运行确定） `Get-CcVersion`  `Get-CcRunningVersion` 都是 1.4.2。 此时，如果运行 以将正在运行的版本切换回 `Switch-CcVersion` 1.4.1，则此旧版本将没有高可用性支持。
    
    若要获得完整的高可用性支持，请切换回 1.4.2，以便运行的版本和脚本版本相同。 如果 1.4.2 部署出现问题，请尽快卸载并重新安装。
    
- **问题：颁发给中央管理存储、中介服务器和边缘服务器的证书颁发机构证书或内部证书即将过期或受到威胁。**
    
    **解决方法：** Skype for Business 证书颁发机构证书的有效期为五年。 颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为两年。
    
    > [!NOTE]
    > 在云连接器 2.0 版和更高版本中，Renew-CcServerCertificate cmdlet 已更改为 Update-CcServerCertificate 并且 Renew-CcCACertificate cmdlet 已更改为 Update-CcCACertificate。 
  
    如果颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或受到威胁，请运行 Renew-CcServerCertificate 或 Update-CcServerCertificate cmdlet 来续订证书。
    
    如果证书颁发机构证书即将过期，请运行 Renew-CcCACertificate 或 Update-CcCACertificate cmdlet 来续订证书。
    
    **如果证书颁发机构证书受到威胁，并且** 站点中只有一个设备，请执行以下步骤：
    
1. 运行 Enter-CcUpdate cmdlet 以排出服务，将设备置于维护模式。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 运行以下 cmdlet 以重置并创建新的证书颁发机构证书以及所有内部服务器证书：
    
    对于 2.0 之前发布的云连接器：
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    或者对于云连接器 2.0 版和更高版本：
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 如果在网关和中介服务器之间使用了 TLS，请从设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 您可能还需要在网关上重新颁发证书。

   ```powershell
   Export-CcRootCertificate
   ```

4. 运行 Exit-CcUpdate cmdlet 以启动服务并退出维护模式。

   ```powershell
   Exit-CcUpdate
   ```


    **如果证书颁发机构证书受到威胁** ，并且站点中有多个设备，请对站点中的每个设备执行以下顺序步骤。
    
    Microsoft 建议您在非高峰使用时段执行这些步骤。
    
1. 第一个设备运行 Remove-CcCertificationAuthorityFile cmdlet 以清理目录中的 CA 备份 \<SiteRoot\> 文件。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 运行 Enter-CcUpdate cmdlet 以排出服务，将每台设备置于维护模式。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 在首个设备中，运行以下 cmdlet 以重置并创建新的证书颁发机构证书以及所有内部服务器证书：
    
     对于 2.0 之前发布的云连接器：
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     或者对于云连接器 2.0 版和更高版本：
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 在首个设备中，运行以下 cmdlet 将 CA 文件备份到 \<SiteRoot\> 文件夹。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 在同一站点中的所有其他设备中，运行以下命令以使用 CA 备份文件，以便设备全部使用相同的根证书，然后请求新证书。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 如果在网关和中介服务器之间使用 TLS，请从站点中任何设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 您可能还需要在网关上重新颁发证书。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 运行 Exit-CcUpdate cmdlet 以启动服务并退出维护模式。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **问题：在云连接器管理服务日志中收到以下错误消息"C：\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService Error： 0 ： Unexpected exception when reporting status to online： System.Management.Automation.CmdletInvocationException： Logon failed for the user \<Global Tenant Admin\> .请创建新的凭据对象，确保已使用正确的用户名和密码。---\>**
    
    **解决方法：** 自云连接器设备注册后，Microsoft 365 或 Office 365 全局租户管理员凭据已更改。 若要更新云连接器设备本地存储的凭据，请从主机上的管理员 PowerShell 运行以下代码：
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **问题：更改用于部署的主机服务器帐户的密码后，在 %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log 中或在运行 Get-CcCredential cmdlet 时收到以下错误消息："ConvertTo-SecureString： Key 无效 for use in specified state"。**
    
    **解决方法：** 所有云连接器凭据都存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。 当主机服务器上密码更改时，您需要更新本地存储的凭据。
    
    **如果运行的是云连接器版本 1.4.2，** 请执行以下步骤重新生成所有云连接器密码：
    
  1. 重新启动主机服务器。
    
  2. 删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。
    
  3. 以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。 输入之前为云连接器部署输入的相同密码。
    
     **如果运行的是云连接器 2.0** 版或更高版本，请执行以下步骤重新生成所有云连接器密码：
    
  4. 重新启动主机服务器。
    
  5. 删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml" .
    
  6. 以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。 
    
     如果缓存的密码文件是使用云连接器版本 1.4.2 生成的，则当系统提示时，请使用 CceService 密码的 VMAdmin 密码。 输入之前为所有其他帐户的云连接器部署输入的相同密码。
    
     如果缓存的密码文件是使用云连接器版本 1.4.2 生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：
    
  7. 运行 Set-CcCredential -AccountType DomainAdmin，如下所示：
    
  8. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
  9. 当系统提示输入新帐户凭据时，请输入之前使用的 DomainAdmin 密码的密码。
    
     如果缓存的密码文件是使用云连接器版本 2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。 如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：
    
  10. 运行 Set-CcCredential -AccountType DomainAdmin，如下所示：
    
       1. 当系统提示输入旧帐户凭据时，输入用于 CceService 密码的凭据
    
       2. 当系统提示输入新帐户凭据时，请输入之前使用的 DomainAdmin 密码的密码。
    
  11. 运行 Set-CcCredential -AccountType VmAdmin，如下所示：
    
       1. 当系统提示输入旧帐户凭据时，输入用于 CceService 密码的凭据
    
       2. 当系统提示输入新帐户凭据时，请输入之前使用的 VmAdmin 密码的密码。 
    
- **问题：对于云连接器版本 2.1 及更高版本，当在设备中运行 Register-CcAppliance 或其他 cmdlet 时，将收到错误消息，例如："对于 Each-Object ：在此对象上找不到属性"Common"。验证属性是否存在。在 C：\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1：681 char：14"**
    
    **解决方法：** 云连接器 2.1 及更高版本.NET Framework 4.6.1 或更高版本。 Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet (s) again.

- **问题：在云连接器版本 2.1 中，运行 Install-CcAppliance 时，会收到一条错误消息，例如："安装新实例失败，出现错误：无法设置"状态"，因为只能将字符串用作设置 XmlNode 属性的值"**

   **解决方法：** In Cloudconnector.ini， under the [Common] section， please add the "State" config as below： CountryCode=US State=WA City=Redmond

   "State"行不一定必须具有值，但不能从"State"Cloudconnector.ini中删除。

- **问题：收到以下错误消息"Dismount-WindowsImage ： Dismount-WindowsImage失败。安装或0xc1550115云连接器版本时，错误代码 = 0xc1550115"。**
    
    **解决方法：** 以管理员角色启动 PowerShell 控制台，运行"DISM -Cleanup-Wim'"。 这将清理所有有问题的图像。 再次Install-CcAppliance或等待位自动升级。
    
- **问题：HA 环境中第一个云连接器设备的部署失败**
    
    **解决方法：** 您执行的步骤取决于部署失败的原因：
    
  - 如果第一个云连接器设备出现故障，并且无法确定故障原因，则必须在部署成功之前再次安装该设备，然后安装其他设备。
    
  - 如果第一个云连接器设备出现故障，出现一个小问题（如外部证书问题）时，你可能能够在不重新安装该设备的情况下解决该问题。 然后，可以使用租户远程 PowerShell 将部署标记为成功，如下所示。  (如果第一次部署成功，您也可以使用以下步骤，但出于某种原因，云连接器无法将部署报告为成功。) 
    
  - 若要获取第一 (设备的 IDENTITY) GUID，请运行 Get-CsHybridPSTNAppliance cmdlet。
    
  - 若要将设备标记为已成功部署，请Set-CsCceApplianceDeploymentStatus如下所示：
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **问题：需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**
    
   **解决方法：** 我们建议你利用 Skype for Business 云连接器版本提供的自动操作系统更新。 注册设备进行联机管理并启用自动更新操作系统后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查和安装 Windows 更新。
    
   如果需要手动检查并安装 Windows 更新，请按照本节中适用于你的部署类型的步骤操作。 应计划同时更新主机服务器及其上运行的虚拟机，以最大限度地减少更新所需的停机时间。
    
   如果愿意，可以使用 WSUS (Windows Server Update Services) 向云连接器服务器提供更新。 只需确保将 Windows 更新配置为 **不自动** 安装。
    
   若要了解如何手动更新云连接器部署，请参阅以下部分。
    
- **问题：当云连接器更新到新内部版本时，不会更新云连接器 cmdlet。** 当发生自动更新时，如果 PowerShell 窗口为打开状态，则有时会出现此情况。
    
  **解决方法：** 若要加载更新的 cmdlet，可以执行以下步骤之一：
    
   - 关闭云连接器设备的 PowerShell，然后重新打开 PowerShell。
    
     - 或者，你可以运行 Import-Module -Force。 
 
-   **问题："The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet， function， script file， or operable program." error when attempting to run Enter-CcUpdate cmdlet.**

    **解决方法：** 删除 $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。
PowerShell 将此文件创建为它找到的模块中的 cmdlet 缓存，这样它就不必每次重新分析所有模块，因为这样做会使操作变得很慢。 很可能存在一些文件损坏，导致 PowerShell 在从该缓存中回读时产生令人误解的结果。

-   **问题："Import-Module CloudConnector"生成错误"Import-Module： 未加载指定的模块"CloudConnector"，因为在任何模块目录中都未找到有效的模块文件"**

    **解决办法：**
    - 验证 CloudConnector 模块是否确实位于 c：\Program Files\WindowsPowerShell\Modules 下
    
    - 在验证 CloudConnector 模块是否存在在此位置之后，可以更改存储模块位置路径的 PSModulePath 环境变量：
    
     a. 临时更改：以管理员角色启动 Powershell 并运行以下命令：$env：PSModulePath = $env：PSModulePath + ";C：\Program Files\WindowsPowerShell\Modules\"
        
     b. 对于永久性更改，请以管理员角色启动 PowerShell 并一一运行以下命令：$CurrentValue = [Environment]：：GetEnvironmentVariable ("PSModulePath"， "Machine") SetEnvironmentVariable ("PSModulePath"， $CurrentValue + ";C：\Program Files\WindowsPowerShell\Modules"， "Machine") 

    
## <a name="install-windows-updates-manually"></a>手动安装 Windows 更新

如果你不希望在你的环境中使用自动更新，请按照以下步骤手动检查并应用 Windows 更新。 检查并安装 Windows 更新可能需要重新启动服务器。 当主机服务器重新启动时，用户将不能使用云连接器拨打或接听呼叫。 你可以手动检查并安装更新，以控制更新发生的时间，然后在选择的时间根据需要重新启动计算机以避免服务中断。
  
若要手动检查更新，请连接到每台主机服务器并打开 **控制面板**。 选择 **"系统和安全 \> Windows 更新**"，然后根据你的环境管理更新和服务器重新启动。
  
- 如果站点中只有一个设备，请连接到每台虚拟机并打开 **控制面板**。 选择 **"系统和安全 \> Windows 更新"，** 然后根据情况配置更新和服务器重新启动。
    
- 如果站点中存在多个设备，则更新期间用户无法访问正在更新和重新启动的实例。 更新完成后，用户将连接到部署中的其他实例，直到所有虚拟机和所有 Skype for Business 服务在虚拟机上启动。 为避免任何潜在的服务中断，可以在应用更新时从 HA 中删除实例，然后在完成后还原它。 为此，请执行以下操作：
    
1. 在每台主机服务器上，以管理员角色打开 PowerShell 控制台。
    
2. 通过以下 cmdlet 从 HA 中删除实例：
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    按照单个实例的步骤手动应用更新并重新启动虚拟机。
    
4. 通过以下 cmdlet 将实例设置回 HA：
    
   ```powershell
   Exit-CcUpdate
   ```

对于多站点部署，请按照部署中每个站点的单个站点的步骤操作，一次将更新应用到一个站点。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在云连接器主机计算机上安装防病毒软件的提示

如果需要在云连接器主机计算机上安装防病毒软件，需要添加以下排除项：
  
- 每台计算机的本地设备目录。
    
- 每台计算机上都有远程站点目录。
    
- 计算机上本地网站目录托管共享网站根文件夹。
    
- %ProgramFiles%\Skype for Business 云连接器版本
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 此过程Microsoft.Rtc.CCE.ManagementService.exe。