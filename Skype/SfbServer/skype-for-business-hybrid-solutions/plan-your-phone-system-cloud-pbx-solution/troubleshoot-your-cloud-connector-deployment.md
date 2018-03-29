---
title: 云连接器部署故障排除
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 解决您的云连接器版部署。
ms.openlocfilehash: 1fb4f65c0fefd335865c5babb0e69090ab824908
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>云连接器部署故障排除
 
解决您的云连接器版部署。
  
本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。
  
云的连接器提供用于自动解决某些问题的内置机制。 自动检测进程与云接头装置中，寻找潜在的问题，并如有可能，采取纠正措施来解决这些问题，而不需要管理员干预。 检测过程工作方式如下：
  
- **检测序列：**云连接器管理服务运行过程每隔 60 秒来检测装置是否已关闭。 在云连接器 2.0 及更高版本中，检测过程使用 Skype 业务企业网络交换机进行 PowerShell 连接到云接头机;对于 2.0 之前的版本，检测过程使用云连接器管理交换机。
    
    > [!NOTE]
    > 自动恢复为取得成功，必须有虚拟机与主机之间的网络连接主机网络交换机上。 一定要检查网络连接，以确保该自动检测和恢复可能会成功。 
  
- **监控：**在云连接器 2.0 及更高版本中监视以下服务：
    
  - 虚拟机未连接到云连接器公司或 Internet 虚拟交换机
    
  - 虚拟机处于已保存或已停止的状态
    
  - 中央管理服务器服务： 副本、 母版
    
  - 中介服务器服务： 副本、 RTCSRV 和 MEDSVC
    
  - 边缘服务器服务： 副本、 RTCSRV、 RTCDATAPROXY、 RTCMRAUTH、 RTCMEDIARELAY
    
  - 入站的防火墙规则在边缘服务器上，CS RTCMEDSRV 中介服务器上禁用 CS RTCSRV
    
    在云接头 1.4.2 版，监视仅以下服务：
    
  - 中介服务器服务： RTCSRV 和 MEDSVC
    
  - 边缘服务器服务： RTCSRV
    
- **恢复过程：**如果任何被监视的服务下，装置将被标记为关闭，和服务被停止并标记为手动，直到就可以解决所有的问题。 这将会阻止调用路由到装置，可能会导致调用失败。
    
    该云连接器管理服务，如下所示将重试自动恢复
    
  - 初始的重试间隔是每十秒，最大间隔时间为一小时。
    
  - 对于前三个故障恢复尝试的间隔时间为 10 秒。 从第四重试，间隔时间将增加执行前一个时间间隔时间的两倍。 例如，第四重试将在 20 秒钟内，在 40 秒内，第五个发生等等。 
    
  - 达到最大间隔时间在一个小时后，重试将继续每小时一次。
    
  - 成功恢复时，时间间隔，然后重试计数设置为它们的初始值。
    
  - 管理服务重新启动时，如果时间间隔，然后重试计数被重置为其初始值。
    
## <a name="troubleshooting"></a>疑难解答

下面是通常遇到的问题的解决方案：
  
- **问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**
    
    **解决方案：**不能自动解决该问题。 在运行时，无法将 Nic 添加到虚拟机。 请关闭并在超 v 管理器中，删除这些虚拟机，然后运行以下 cmdlet:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **问题： 安装在活动目录服务器和林后，CMS 服务器和/或中介服务器未加入域正确。**
    
    **解决方法：**要解决此问题，请执行以下步骤：
    
  - 登录 Active Directory 服务器并验证是否已正确创建域。
    
  - 登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。
    
  - 登录到 CMS/中介服务器，然后打开一个命令提示符。 请确保您可以 ping 活动目录服务器的 FQDN 和 IP 地址。 如果不能则表明可能存在 IP 地址冲突。 请尝试为 Active Directory 中分配新的 IP，并相应地更新 CMS/中介服务器上的 DNS。
    
- **问题： 您收到下面的错误消息，"删除 VMSwitch： 在删除虚拟以太网交换机时失败。云连接器管理交换机虚拟交换机无法删除，因为它正由运行的虚拟机或分配给子池。"**
    
    **解决方案：**"云连接器管理开关"在部署后未被删除。 如果遇到此错误，请转到 hyper-v 管理器，并验证是否存在不仍然仍然连接到该虚拟机。 如果有仍然保持连接的虚拟机，请断开它们的连接并删除管理交换机。 如果仍然无法删除管理交换机，请重新启动主机服务器，然后重试。
    
- **问题： 您收到下面的错误消息、"RTCMRAUTH 服务无法启动。请检查以确保未禁用该服务。**
    
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
    
    **解决方案：**如果您部署高可用性环境，Microsoft 提供的 cmdlet 来帮助移动一台宿主机器 （部署实例） 或当前拓扑时检查并手动安装 Windows 更新。 使用以下步骤完成此操作：
    
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
    
    **解决方案：**若要解决此问题，请参阅[配置在线混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**
    
    **解决方案：**启动业务租户管理凭据，使用 Skype 的租户远程 PowerShell 会话，然后运行以下 cmdlet 以检查您的网站的_EnableAutoUpdate_配置：
    
  ```
  Get-CsHybridPSTNSite
  ```

    如果_EnableAutoUpdate_设置为**True**时，可以安全地忽略此警告消息，因为下载和安装 Windows 更新虚拟机及其主机服务器将处理的 CCEManagement 服务。 如果_EnableAutoUpdate_设置为**False**，则运行以下 cmdlet 将其设置为**True**。
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    此外，你还可以手动检查并安装更新。请参阅下节内容。
    
- **问题： 您收到的错误消息： 无法注册装置，因为每个配置当前的输入\<网站名称\>或\<装置名称\>或\<中介服务器 FQDN\>或\<中介服务器的 IP 地址\>现有装置与冲突。删除冲突装置或更新您输入/配置的信息，然后重新注册。运行时注册的 CcAppliance 注册当前装置为联机。**
    
    **解决方案：**值为\<装置名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>必须是唯一的并且只用于一个装置登记。 默认情况下，\<装置名称\>来自主机名。 \<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>配置 ini 文件中定义。
    
    例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。
    
    首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。 您将获得\<网站名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>文件中的值。 \<装置名称\>是您主机的服务器名称。
    
    第二，启动租户远程 PowerShell 您 Skype 用于商业租户管理员凭据，然后运行以下 cmdlet 来检查已注册的装置。
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

- 
    
    **问题： 如果主机上运行的部署的装置，获取 CcRunningVersion cmdlet 返回空值。**
    
    **解决方法：**从 1.3.4 或 1.3.8 升级到 1.4.1 之后，可能会出现此情况。使用 .msi 安装 1.4.1 版之后，必须先运行 `Register-CcAppliance`，才能运行任何其他 cmdlet。`Register-CcAppliance` 会将 module.ini 文件从 %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。如果你没有运行此 cmdlet，将会在 %ProgramData%\CloudConnector 文件夹中创建一个新的 module.ini 文件，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。
    
    比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。 如果有差异，删除在 %ProgramData%\CloudConnector 和重新运行 module.ini 文件`Register-CcAppliance`。 您还可以修改文件手动的正确运行和备份版本。
    
- **问题： 开关 CcVersion 用于切换到旧版本不同于当前的脚本版本，运行后，没有高可用性支持此旧版本。**
    
    **解决方案：**例如，您已从 1.4.1 升级到 1.4.2。 您当前的脚本版本，可以确定通过运行`Get-CcVersion`，和您正在运行的版本，可由运行`Get-CcRunningVersion`是两个 1.4.2。 此时，如果您运行`Switch-CcVersion`回到运行版本 1.4.1，然后会有这个旧的版本没有高可用性支持。
    
    要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。
    
- **问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**
    
    **解决方法：**Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。
    
    > [!NOTE]
    > 在云接头 2.0 及更高版本，更新 CcServerCertificate cmdlet 已更改为更新 CcServerCertificate 并更新 CcCACertificate cmdlet 已更改为更新 CcCACertificate。 
  
    如果内部证书颁发给中央管理存储、 中介服务器和边缘服务器临近到期或泄露，运行更新 CcServerCertificate 或者更新 CcServerCertificate cmdlet 续订证书。
    
    如果证书颁发机构证书过期附近，运行更新 CcCACertificate 或更新 CcCACertificate cmdlet 来续订证书。
    
    **如果证书颁发机构证书也不怕，并且只有一个装置在站点，**请执行以下步骤：
    
1. 运行输入 CcUpdate cmdlet 耗尽服务并将该装置放入维护模式。
    
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

3. 运行启动服务退出 CcUpdate cmdlet 和退出维护模式。
    
4. 的装置中的本地文件上运行导出 CcRootCertificate cmdlet 然后复制并将导出的证书安装到您的 PSTN 网关。
    
    **如果证书颁发机构证书被泄露，有多个装置在站点，**站点中的每个装置上执行以下顺序步骤。
    
    Microsoft 建议您在非高峰使用时间段执行这些步骤。
    
  - 第一个应用装置，在运行用于清理 CA 备份中的文件，然后删除 CcCertificationAuthorityFile \<SiteRoot\>目录。
    
  - 运行输入 CcUpdate 用于数据包服务，每个装置置于维护模式。
    
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

  - 在第一个应用装置，运行以下 cmdlet 来备份 CA 文件\<SiteRoot\>文件夹。 以后，在同一站点中的所有其他装置，重置 CcCACertificate cmdlet 将自动使用 CA 备份文件，装置将使用相同的根证书。
    
  ```
  Backup-CcCertificationAuthority
  ```

  - 运行该退出 CcUpdate cmdlet 以启动服务并退出维护模式。 
    
  - 如果网关和中介服务器之间使用 TLS，则从网站中的任意设备上运行导出 CcRootCertificate cmdlet，然后将导出的证书安装到您的 PSTN 网关。 
    
- **问题： 您在云中连接器管理服务日志"C:\Program Files\Skype 的业务云连接器 Edition\ManagementService\CceManagementService.log"中收到下面的错误消息： 错误 CceService: 0： 意外的异常时向联机报告状态： System.Management.Automation.CmdletInvocationException： 登录失败的用户\<全局租户管理\>。请创建新的凭据对象，并确保使用正确的用户名称和密码。---\>**
    
    **解决方案：**因为云接头装置已注册 Office 365 全局租户管理员凭据已更改。 要更新云接头装置上本地存储的凭据，请运行以下命令从管理员 PowerShell 主机设备上：
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- 
    
    **问题： 您更改用来部署主机服务器帐户的密码后，您收到以下错误消息:"ConvertTo SecureString： 指定用于无效的键状态。"在 %ProgramFiles%\Skype 业务云连接器Edition\ManagementService\CceManagementService.log 或同时运行 Get CcCredential cmdlet。**
    
    **解决方案：**所有的云连接器凭据存储在下列文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。 在主机服务器上的密码更改时，您将需要更新本地存储的凭据。
    
    **如果您正在运行云连接器版本 1.4.2，**再生云连接器的所有密码通过执行以下步骤：
    
1. 重新启动主机服务器。
    
2. 删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。
    
3. 启动作为管理员，PowerShell 控制台，然后运行"登记 CcAppliance-本地"以重新输入描述的密码。 输入云连接器部署之前输入的相同密码。
    
    **如果您正在运行云连接器 2.0 版或更高版本，**请按照下面的步骤再生云连接器的所有密码：
    
1. 重新启动主机服务器。
    
2. 删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。
    
3. 启动作为管理员，PowerShell 控制台，然后运行"登记 CcAppliance-本地"以重新输入描述的密码。 
    
    如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。
    
    如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：
    
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
    如果缓存的密码文件生成云接头 2.0 版或更高版本中，默认情况下，VmAdmin 和 DomainAdmin CceService 为使用相同的密码。 如果您更改了 DomainAdmin 和 VMAdmin 的密码，您必须执行以下步骤：
    
1. 按如下所述运行 Set-CcCredential -AccountType DomainAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。
    
2. 按如下所述运行 Set-CcCredential -AccountType VmAdmin：
    
1. 当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。
    
2. 当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。 
    
- 
    
    **问题： 云接口版本 2.1 或更高版本，装置，运行注册 CcAppliance 或其他 cmdlet 时您会收到一条错误消息如:"为每个对象: '公共' 找不到该对象的属性。验证该属性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 字符： 14"**
    
    **解决方案：**云的连接器 2.1 和以后需要.NET Framework 4.6.1 或更高版本。 请更新至版本 4.6.1 装置上的.NET Framework 或更高版本，然后再次运行 cmdlet(s)。
    
- **问题： 您收到下面的错误消息"卸除 WindowsImage： 卸除 WindowsImage 失败。错误代码 = 0xc1550115"安装或升级云连接器版时。**
    
    **解决方案：**启动 PowerShell 控制台，请以管理员身份运行"DISM-清理-Wim'"。 这将清除所有故障的图像。 再次运行安装 CcAppliance 或等待的位自动升级。
    
- **问题： 高可用性环境中的第一个云接头装置部署失败**
    
    **解决方案：**所采取的步骤取决于部署失败的原因：
    
  - 如果第一个云接头装置出现故障，无法确定失败的原因，必须重新安装设备之前部署成功，并再安装其他设备。
    
  - 如果第一个云接头装置失败，出现小问题，如外部证书问题，您可能能够解决问题，而无需重新安装设备。 您可以使用租户远程 PowerShell 如下标记为成功的部署。 （还可以使用以下步骤如果在首次部署成功，但由于某种原因，云连接器无法报告为成功部署。）
    
  - 若要获取第一个云接口装置的标识 (GUID)，运行 Get CsHybridPSTNAppliance cmdlet。
    
  - 若要标记为已成功部署设备，请按如下所示运行一组 CsCceApplianceDeploymentStatus:
    
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
    
    **问题： 当云接头更新到新版本时，云连接器 cmdlet 都不更新。** 只有 PowerShell 窗口处于打开状态时自动更新发生时，有时会出现此问题。
    
    **解决方案：**若要加载更新后的 cmdlet，可以执行以下步骤之一：
    
  - 对云连接器的装置，关闭 PowerShell，然后重新打开 PowerShell。
    
  - 或者，您可以运行导入模块 CloudConnector 的力。 
    
## <a name="install-windows-updates-manually"></a>手动安装 Windows 更新

如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。 检查并安装 Windows 更新可能需要重新启动服务器。 当主机服务器正在重新启动时，用户不能使用云连接器发送或接收传呼。 你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。
  
要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。 选择**系统和安全\>Windows 更新**，然后管理更新程序和服务器重启为适合于您的环境。
  
- 如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。 选择**系统和安全\>Windows 更新**，然后将更新的配置，并根据需要重新启动服务器。
    
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
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在云连接器宿主计算机上安装防病毒软件时的提示

如果您需要在云连接器宿主计算机上安装防病毒软件，您需要添加以下排除项：
  
- 每台计算机上的本地设备目录。
    
- 每台计算机上的远程站点目录。
    
- 本地计算机上的站点目录承载共享的站点根文件夹。
    
- 商务云连接器版的 %ProgramFiles%\Skype
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Microsoft.Rtc.CCE.ManagementService.exe 过程。
    

