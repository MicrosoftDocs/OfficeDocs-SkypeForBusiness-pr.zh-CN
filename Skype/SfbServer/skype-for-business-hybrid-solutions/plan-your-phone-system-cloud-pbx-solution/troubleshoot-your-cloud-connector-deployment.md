---
title: 云连接器部署故障排除
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 解决云连接器 Edition 部署。
ms.openlocfilehash: 2e4f0d2a258e48e4c953fb8ea4175c64b585b91f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>云连接器部署故障排除
 
解决云连接器 Edition 部署。
  
本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。
  
云连接器提供用于自动解决某些问题的内置机制。 自动检测过程与云连接器 appliance，查找潜在问题，如果可能，请采取纠正操作解决这些问题，无需管理员干预。 检测过程工作方式如下：
  
- **检测序列：**云连接器管理服务过程每 60 秒运行用于检测装置是否已关闭。 在云连接器 2.0 及更高版本，检测过程使用 Skype 业务 Corpnet 开关进行 PowerShell 连接到云连接器机中;对于 2.0 之前的版本，检测过程使用云连接器管理开关。
    
    > [!NOTE]
    > 自动恢复，若要成功执行，必须有主机和虚拟机之间的网络连接通过主机网络交换机。 一定要检查网络连接，以确保该自动检测并恢复才能成功。 
  
- **监控：**云 Connector 2.0 及更高版本中监视以下服务：
    
  - 虚拟机未连接到云连接器公司或 Internet 虚拟交换机
    
  - 虚拟机处于保存还是已停止的状态
    
  - 中央管理服务器服务： 副本、 主控形状
    
  - 中介服务器服务： 副本、 RTCSRV 和 MEDSVC
    
  - 边缘服务器服务： 副本、 RTCSRV、 RTCDATAPROXY、 RTCMRAUTH、 RTCMEDIARELAY
    
  - 对于边缘服务器，中介服务器上的 CS RTCMEDSRV CS RTCSRV 禁用规则的防火墙的入站邮件
    
    在云连接器版本 1.4.2，监视仅以下服务：
    
  - 中介服务器服务： RTCSRV 和 MEDSVC
    
  - 边缘服务器服务： RTCSRV
    
- **恢复过程：**如果任何监控的服务不可用，装置标记下，并已停止并可以解决所有问题之前标记手动服务。 这将防止路由至装置可能会导致呼叫失败的呼叫。
    
    云连接器管理服务，如下所示将重试自动恢复
    
  - 初始重试间隔为最大的间隔时间为一小时每个十秒。
    
  - 前三个恢复尝试时，间隔时间为 10 秒。 从第四个重试，由两次以前间隔时间增加的间隔时间。 例如，第四个重试将出现在 20 秒内，以 40 秒为单位，为第五个，依此类推。 
    
  - 达到一小时的最大的间隔时间后，重试次数将继续每小时一次。
    
  - 成功恢复时，为其初始值设置间隔，然后重试计数。
    
  - 如果重新启动管理服务，则的时间间隔，然后重试的计数将重置为其初始的值。
    
## <a name="troubleshooting"></a>疑难解答

以下是常见的问题的解决方案：
  
- **问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**
    
    **解决方法：**无法自动解决此问题。 在运行时，无法将 Nic 添加到虚拟机。 请关闭和删除 hyper-v 管理器中的这些虚拟机，然后运行以下 cmdlet:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **问题： 安装在 Active Directory 服务器和林之后，CMS 服务器和/或中介服务器未加入域正确。**
    
    **解决方法：**要解决此问题，请执行以下步骤：
    
  - 登录 Active Directory 服务器并验证是否已正确创建域。
    
  - 登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。
    
  - 登录到 CMS/中介服务器，并打开命令提示符。 请确保您可以 ping Active Directory 服务器的 FQDN 和 IP 地址。 如果您不能可能有冲突的 IP 地址。 请尝试将一个新的 IP 分配 Active directory 并相应地更新 DNS CMS/中介服务器上。
    
- **问题： 您将收到以下错误消息，"删除 VMSwitch： 移除虚拟以太网开关时失败。云连接器管理切换在虚拟交换机无法删除因为它正在由运行虚拟机或分配给子池。"**
    
    **解决方法：**"云连接器管理开关"未在部署后删除。 如果遇到此错误，请转到 hyper-v 管理器，并验证是否存在不仍仍为连接到该虚拟机。 如果有仍为连接状态的虚拟机，在断开连接，并删除管理开关。 如果仍然不能删除管理开关，重新启动的主机服务器，然后重试。
    
- **问题： 您将收到以下错误消息，"RTCMRAUTH 服务未能启动。检查以确保不禁用该服务。"**
    
    > [!NOTE]
    > 此问题仅适用于云连接器版本早于 1.4.2。 
  
    无法启动也可能是因为此前端服务器之前经过故障转移（使用计算机故障转移）。如果是这种情况，请调用故障回复（使用计算机故障回复）。
    
    **解决方法：**当边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会出现此问题。即使可以导入外部证书，但证书链已损坏。在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。
    
    请手动将外部证书的根 CA 证书和所有中间 CA 证书导入到边缘服务器，然后重新启动边缘服务器。看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动之后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以便切换到新部署：
    
  ```
  Switch-CcVersion
  ```

- 
    
    **问题：应用 Windows 更新时主机服务器重新启动，由此服务器支持的调用失败。**
    
    **解决方法：**如果您部署的高可用性环境，Microsoft 提供的 cmdlet 来帮助移动一个主机 （部署实例） 迁入或迁出当前拓扑时检查和手动安装 Windows update。 使用以下步骤实现这一点：
    
1. 在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：
    
  ```
  Enter-CcUpdate
  ```

2. 检查更新并安装所有可用更新。
    
3. 在 PowerShell 控制台中，运行以下 cmdlet：
    
  ```
  Exit-CcUpdate
  ```

- 
    
    **问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**
    
    **解决方法：**若要解决此问题，请参阅[配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**
    
    **解决方法：**启动租户远程 PowerShell 会话 Skype 用于业务租户管理员凭据，然后运行以下 cmdlet 以检查您的网站的_EnableAutoUpdate_配置：
    
  ```
  Get-CsHybridPSTNSite
  ```

    _EnableAutoUpdate_设置为**True**，如果可以安全地忽略此警告消息，因为 CCEManagement 服务将处理下载并安装 Windows 更新的虚拟机和主服务器。 如果_EnableAutoUpdate_设置为**False**，则运行以下 cmdlet 以将其设置为**True**。
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    此外，你还可以手动检查并安装更新。请参阅下节内容。
    
- **问题： 您将收到一条错误消息： 无法注册 appliance，因为每个配置当前的输入\<SiteName\>或\<装置名称\>或\<中介服务器 FQDN\>或\<中介服务器的 IP 地址\>与现有装置冲突。删除冲突装置或更新您的输入/配置信息，然后再次注册。注册-CcAppliance 注册到 online 当前装置运行时。**
    
    **解决方法：**值\<装置名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>必须是唯一的并且仅用于一个 appliance 注册。 默认情况下，\<装置名称\>来自的主机名称。 \<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>配置 ini 文件中定义。
    
    例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。
    
    首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。 您将收到\<SiteName\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>文件中的值。 \<装置名称\>是主机服务器名称。
    
    其次，启动租户远程 PowerShell 您 Skype 用于业务租户管理员凭据，然后运行以下 cmdlet 以检查注册的装置。
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

- 
    
    **问题： 运行在主机上部署的设备时，获取 CcRunningVersion cmdlet 返回一个空值。**
    
    **解决方法：**从 1.3.4 或 1.3.8 升级到 1.4.1 之后，可能会出现此情况。使用 .msi 安装 1.4.1 版之后，必须先运行 `Register-CcAppliance`，才能运行任何其他 cmdlet。`Register-CcAppliance` 会将 module.ini 文件从 %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。如果你没有运行此 cmdlet，将会在 %ProgramData%\CloudConnector 文件夹中创建一个新的 module.ini 文件，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。
    
    比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。 如果有区别，删除 %ProgramData%\CloudConnector 并重新运行中的 module.ini 文件`Register-CcAppliance`。 您还可以修改手动向正确运行和备份版本的文件。
    
- **问题： 运行开关 CcVersion cmdlet 以切换到从中当前脚本版本不同的旧版本后，没有高可用性支持此旧版本。**
    
    **解决方法：**例如，已从 1.4.1 升级到 1.4.2。 您当前的脚本版本，可以通过运行确定`Get-CcVersion`，并且您运行的版本，可以通过运行确定`Get-CcRunningVersion`是这两个 1.4.2。 此时，如果您运行`Switch-CcVersion`来切换回 1.4.1 运行的版本，然后将有此旧版本不高可用性支持。
    
    要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。
    
- **问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**
    
    **解决方法：**Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。
    
    > [!NOTE]
    > 在云连接器 2.0 及更高版本，续订 CcServerCertificate cmdlet 已更改为更新 CcServerCertificate 和续订 CcCACertificate cmdlet 已更改为更新 CcCACertificate。 
  
    如果颁发给的中央管理存储、 中介服务器和边缘服务器内部证书临近过期或威胁，运行要续订证书的续订 CcServerCertificate 或更新 CcServerCertificate cmdlet。
    
    如果证书颁发机构证书过期附近，运行续订 CcCACertificate 或更新 CcCACertificate cmdlet 续订您的证书。
    
    **如果证书颁发机构证书受到威胁，并且只有一个装置的站点中，**执行以下步骤：
    
1. 运行排出服务和装置置于维护模式下 Enter CcUpdate cmdlet。
    
2. 运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：
    
    对于云连接器 2.0 之前的版本：
    
  ```
  Reset-CcCACertificate 
Renew-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

    或云连接器版本 2.0 及更高版本：
    
  ```
  Reset-CcCACertificate 
Update-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

3. 运行退出 CcUpdate cmdlet 启动的服务和退出维护模式。
    
4. 运行导出 CcRootCertificate cmdlet 上的本地文件中设备，然后复制并将导出的证书安装到 PSTN 网关。
    
    **如果证书颁发机构证书受到威胁，并且有多个装置的站点中，**执行以下顺序步骤在网站中每个设备上。
    
    Microsoft 建议您在非高峰使用时间段执行这些步骤。
    
  - 第一台设备上运行删除 CcCertificationAuthorityFile cmdlet CA 清理备份文件\<SiteRoot\>目录。
    
  - 运行 Enter CcUpdate cmdlet 排出服务并将每个装置放在维护模式。
    
  - 运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：
    
    对于云连接器 2.0 之前的版本：
    
  ```
  Reset-CcCACertificate
Renew-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

    或云连接器版本 2.0 及更高版本：
    
  ```
  Reset-CcCACertificate
Update-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

  - 在第一个设备，运行以下 cmdlet，以备份到的 CA 文件\<SiteRoot\>文件夹。 更高版本，在同一站点中的所有其他设备，重置 CcCACertificate cmdlet 将自动使用 CA 备份文件，设备将使用相同的根证书。
    
  ```
  Backup-CcCertificationAuthority
  ```

  - 运行退出 CcUpdate cmdlet 启动服务并退出维护模式。 
    
  - 如果网关和中介服务器之间使用 TLS，则从网站中的任意设备运行导出 CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。 
    
- **问题： 您在云中连接器管理服务日志"C:\Program Files\Skype 的业务云连接器 Edition\ManagementService\CceManagementService.log"中收到以下错误消息： CceService 错误： 0： 意外的异常时向联机报告状态： System.Management.Automation.CmdletInvocationException: 用户登录失败\<全局租户管理员\>。请创建一个新的凭据对象，并确保您已经使用正确的用户名和密码。---\>**
    
    **解决方法：**由于注册云连接器装置已更改的 Office 365 全局租户管理员凭据。 若要更新云连接器装置上本地存储的凭据，运行以下命令从管理员 PowerShell 主机装置上：
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- 
    
    **问题： 更改用于部署的主机服务器帐户的密码后，您收到以下错误消息:"ConvertTo SecureString： 密钥无效用于指定状态。"中的商业云连接器 %ProgramFiles%\SkypeEdition\ManagementService\CceManagementService.log 或同时运行 Get CcCredential cmdlet。**
    
    **解决方法：**所有云连接器凭据都存储在以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。 当主机服务器上的密码更改时，您将需要更新本地存储的凭据。
    
    **如果您运行的云连接器版本 1.4.2，**重新生成所有云连接器密码，按照以下步骤：
    
1. 重新启动主机服务器。
    
2. 删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。
    
3. 启动作为管理员，PowerShell 控制台，然后运行"注册 CcAppliance-本地"以重新输入以下说明的密码。 输入您之前输入云连接器部署的同一密码。
    
    **如果您运行的云连接器版本 2.0 或更高版本，**重新生成所有云连接器密码，按照以下步骤：
    
1. 重新启动主机服务器。
    
2. 删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。
    
3. 启动作为管理员，PowerShell 控制台，然后运行"注册 CcAppliance-本地"以重新输入以下说明的密码。 
    
    如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。
    
    如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：
    
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
    如果缓存的密码文件生成使用云连接器版本 2.0 或更高版本，默认情况下，VmAdmin 和 DomainAdmin 作为 CceService 使用相同的密码。 如果您已经更改 DomainAdmin 和 VMAdmin 密码，您必须执行以下步骤：
    
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
2. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。 
    
- 
    
    **问题： 云连接器 2.1 及更高版本，设备上运行注册 CcAppliance 或其他 cmdlet 时您会收到一条错误消息如:"为每个对象: 常用找不到此对象的属性。验证属性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 字符： 14"**
    
    **解决方法：**云连接器 2.1 和更高版本需要.NET Framework 4.6.1 或更高版本。 请.NET Framework 更新至版本 4.6.1 设备上或更高版本，然后再次运行 cmdlet(s)。
    
- **问题： 您将收到以下错误消息"卸除 WindowsImage： 卸除 WindowsImage 失败。错误代码 = 0xc1550115"安装或升级云连接器 Edition 时。**
    
    **解决方法：**启动 PowerShell 控制台，请以管理员身份运行"DISM-清理-Wim'"。 这将清除所有故障的图像。 再次运行安装 CcAppliance 或等待的位自动升级。
    
- **问题： HA 环境中的第一个云连接器装置的部署失败**
    
    **解决方法：**您采取的步骤取决于部署失败的原因：
    
  - 如果第一个云连接器装置失败，并且无法确定失败的原因，您必须部署成功，直到重新安装设备，然后安装其他设备。
    
  - 如果第一个云连接器装置操作失败，次要问题，例如外部证书问题，您可能能够解决问题，但不重新安装设备。 您还可以然后使用租户远程 PowerShell，可以将标记为成功部署，如下所示。 （您可以使用以下步骤在首次部署已成功，但由于某种原因，云连接器失败时报告为成功部署如果。）
    
  - 若要获取的第一个云连接器装置标识 (GUID)，请运行 Get CsHybridPSTNAppliance cmdlet。
    
  - 要将标记为已成功部署设备，请运行设置 CsCceApplianceDeploymentStatus，如下所示：
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- 
    
    **问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**
    
    **解决方法：**建议你利用 Skype for Business 云连接器版本提供的操作系统自动更新。当设备经过注册以实现联机管理并且启用了操作系统自动更新之后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查并安装 Windows 更新。
    
    如果你需要手动检查并安装 Windows 更新，请按照本节提供的适用于你的部署类型的步骤操作。你需要同时规划主机服务器及其上运行的虚拟机的更新，以便尽可能降低更新所需要的总停机时间。
    
    如果你愿意，可以使用 Windows Server 更新服务 (WSUS) 服务器向云连接器服务器提供更新。只需确保将 Windows 更新配置为**不要**自动安装即可。
    
    有关如何手动更新云连接器部署的信息，请参阅下节。
    
- 
    
    **问题： 当云连接器更新为新版本时，云连接器 cmdlet 不会更新。** 只有在 PowerShell 窗口处于打开状态时自动更新，发生此事件时，有时会出现此问题。
    
    **解决方法：**若要加载的更新的 cmdlet，可以执行以下步骤操作：
    
  - 云连接器装置上, 关闭 PowerShell，然后重新打开 PowerShell。
    
  - 或者，您可以运行导入模块 CloudConnector-Force。 
    
## <a name="install-windows-updates-manually"></a>手动安装 Windows 更新

如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。 检查并安装 Windows 更新可能需要重新启动服务器。 时重新启动的主服务器，用户不能使用云连接器来发出或接收呼叫。 你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。
  
要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。 选中**系统和安全\>Windows Update**，然后管理的更新和服务器重新启动，适用于您的环境。
  
- 如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。 选中**系统和安全\>Windows Update**，然后配置更新，并根据需要重新启动服务器。
    
- 如果站点中有多个设备，更新期间用户将无法访问正在更新和重新启动的实例。用户将连接到部署中的其他实例，直到更新完成后所有虚拟机及虚拟机上的所有 Skype for Business 服务启动为止。为避免任何潜在的服务中断，可以在应用更新时从 HA 删除实例，然后在完成后将其还原。为此：
    
1. 在每台主机服务器上，以管理员身份打开 PowerShell 控制台。
    
2. 使用以下 cmdlet 从 HA 删除实例：
    
  ```
  Enter-CcUpdate
  ```

3. 
    
    按照适用于单个实例的步骤，手动应用更新并重新启动虚拟机。
    
4. 使用以下 cmdlet 将实例重新设置为 HA：
    
  ```
  Exit-CcUpdate
  ```

对于多站点部署，请为部署中的每个站点执行适用于单个站点的步骤，每次向一个站点应用更新。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>云连接器主机计算机上安装防病毒软件时的提示

如果您需要在云连接器主机计算机上安装防病毒软件，您需要添加以下排除：
  
- 每台计算机上的本地装置目录。
    
- 每台计算机上的远程网站目录。
    
- 在计算机上的本地网站目录承载共享的网站根文件夹。
    
- 对于业务云连接器 Edition %ProgramFiles%\Skype
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Microsoft.Rtc.CCE.ManagementService.exe 过程。
    

