---
title: 准备云连接器设备
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 了解有关如何准备部署云接头装置和使用 Office 365 (云 PBX) 中的电话系统。
ms.openlocfilehash: 8dcc15d2feb12516025afb5e60d916f94a81fa57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-your-cloud-connector-appliance"></a>准备云连接器设备
 
了解有关如何准备部署云接头装置和使用 Office 365 (云 PBX) 中的电话系统。
  
本节介绍如何获取 Skype for Business 云连接器版本安装文件、安装云连接器软件以及准备云连接器设备以便进行部署。 完成本节中的所有步骤后，便可为单个站点或多个站点部署云连接器。 如果您有现有的云连接器部署，并且尚未升级到云连接器 2.1 版，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。
  
> [!NOTE]
> Microsoft 支持云连接器版，2.1 版的当前版本。 如果你配置了自动更新，云连接器将自动更新。 如果您配置了手动更新，您需要发布的 60 天内升级到 2.1 版。 Microsoft 将支持早期版本的时间升级 2.1 允许发布后的 60 天。 
  
> [!NOTE]
> 对于云连接器版本 2.1 或更高版本，主机装置必须安装.NET Framework 4.6.1 或更新版本。 
  
> [!IMPORTANT]
> 对于成功部署，运行时配置的商务云连接器版的 Skype 的 cmdlet，总是用作同一控制台会话中启动的一个。 避免在部署和配置期间切换到不同的会话。 
  
> [!NOTE]
> 只需为部署中的第一台设备执行的一些步骤包括：为站点目录创建共享、下载 bits 以及通过 Windows Server ISO 映像准备虚拟硬盘 (VHDX) 文件。 
  
## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>下载 Skype for Business 云连接器版本安装程序

1. 在云接口虚拟机将运行在主机服务器上，将安装文件下载： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。 
    
    > [!IMPORTANT]
    > 在安装云连接器期间，主机服务器必须能够访问 Internet，因为在安装过程中会下载其他文件。 
  
2. 运行安装程序并在安装过程中接受默认值。
    
3. 确认安装已成功完成。
    
## <a name="verify-the-installation-and-configure-the-environment"></a>验证安装并配置环境

1. 打开 PowerShell 控制台以管理员的身份，确认为商务云连接器版 cmdlet Skype 可使用以下 cmdlet:
    
  ```
  Get-Command *-Cc*
  ```

    命令将返回 cmdlet 的为 Skype 业务云连接器版。
    
2. VHD、SfBBits 和 VersionInfo 文件将存储在**网站目录**中。
    
    你可以使用以下 cmdlet 找到**网站目录**的位置：
    
  ```
  Get-CcSiteDirectory
  ```

    此命令会返回文件系统中的某个位置。 该位置可以是本地文件夹或文件共享。 **网站目录**的默认位置为：%USERPROFILE%\CloudConnector\SiteRoot。 默认位置会更改为在每个站点上创建的第一个设备上的文件共享。
    
    所选位置必须满足以下要求：
    
  - 在每个站点中创建的第一个设备上创建。
    
  - 是同一站点中的其他主机服务器（设备）可以访问的共享文件夹。
    
    要将**网站目录**设置为默认位置以外的位置，请运行以下 cmdlet：
    
  ```
  Set-CcSiteDirectory <UNC File path>
  ```

    如果要为站点部署高可用性 (HA)，请确保运行该 cmdlet 将**网站目录**设置为每个站点内的主机服务器上的同一位置。
    
    当您登录并部署站点中的每个设备时，请确保您当前的登录帐户具有适当访问权限**网站目录**。
    
3. **装置的目录**是 Skype 的商务云连接器版和保存外部证书、 实例和日志的位置的本地工作根目录。 默认位置为：%USERPROFILE%\CloudConnector\ApplianceRoot。
    
    要找到**设备目录**的位置，请运行以下 cmdlet：
    
  ```
  Get-CcApplianceDirectory
  ```

    要将**设备目录**设置为默认位置以外的位置，请运行以下 cmdlet：
    
  ```
  Set-CcApplianceDirectory <File path>
  ```

    设备目录应该设置为设备上的本地文件夹。 启动业务云连接器版部署 Skype 之前，只应设置**设备目录**。 如果在部署之后更改了该目录，则需要重新部署主机服务器。
    
    > [!IMPORTANT]
    > **设备目录**的路径中不得包含任何空格。
  
## <a name="set-the-path-for-the-external-edge-certificate"></a>设置外部边缘证书的路径

- 运行以下 cmdlet 以设置外部边缘证书的路径，包括文件名。例如：C:\certs\cce\ap.contoso.com.pfx。证书必须包含私钥。
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > 请注意：-Target 参数是 1.4.2 版及更高版本特定的。 
  
    指定外部证书的完整路径，包括文件名。 证书可以存储在本地或文件共享中。 如果证书存储在共享文件夹中，该共享文件夹必须创建在每个站点的第一个设备上，且必须可由属于同一站点的其他设备访问。 此 cmdlet 将外部证书复制到**设备目录**。
    
    > [!IMPORTANT]
    > **如果已经更新到云接口版本 1.4.2 或更高版本**，请确保准备好外部证书包含私钥和 CA 根证书和中间 CA 证书。 包括整个证书链 > **，如果您有尚未更新到云连接器 1.4.2 版**，请确保您已准备好外部证书包含私钥。 默认情况下，此外部证书必须由 Windows 信任的证书颁发机构颁发。
  
## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>设置外部 PSTN 网关/SBC 证书的路径

如果你要在中介服务器与 PSTN 网关/SBC 之间使用 TLS，请运行以下 cmdlet 来设置网关证书的路径（包括文件名）。 例如： C:\certs\cce\sbc.contoso.com.cer。 证书必须包含分配给网关的证书的根 CA 和中间链。
  
```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 

```

> [!NOTE]
> 请注意：-Target 参数是 1.4.2 版及更高版本特定的。 
  
## <a name="create-virtual-switches-in-hyper-v-manager"></a>在 Hyper-V 管理器中创建虚拟交换机

1. 打开**Hyper-V 管理器** > **虚拟交换机管理器**，并选择**新的虚拟交换机管理**。
    
2. 创建外部虚拟交换机并将其绑定到与你的内部网络域连接的物理网络适配器：
    
    为该虚拟交换机选择“**允许管理操作系统共享此网络适配器**”。
    
3. 创建外部虚拟交换机并将其绑定到被路由到 Internet 的物理网络适配器：
    
    取消选择此虚拟开关**允许管理操作系统共享此网络适配器**。
    
4. 设置将您的外围网络连接到内部网络域**SfB CCE Corpnet 切换**开关的名称。
    
    设置将您的外围网络连接到互联网， **SfB CCE 互联网切换**开关的名称。
    
## <a name="update-the-cloudconnectorini-configuration-file"></a>更新 CloudConnector.ini 配置文件

准备使用[Skype 业务云连接器版规划](plan-skype-for-business-cloud-connector-edition.md)主题[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)中收集的信息的 CloudConnector.ini 文件。
  
要更新文件，应首先运行以下 cmdlet 以获取示例模板 (CloudConnector.Sample.ini)：
  
```
Export-CcConfigurationSampleFile
```

示例模板存储在**设备目录**中。
  
使用环境的值更新文件后，在**设备目录**中将其另存为 CloudConnector.ini。 您可以运行**Get CcApplianceDirectory**来确定**装置的目录**的路径。
  
更新 .ini 文件时，请考虑以下内容：
  
> [!NOTE]
> 本节并未讨论 .ini 文件中的所有值，只涵盖了需要特别注意的值。 有关完整列表，请参阅[规划业务云连接器版 Skype](plan-skype-for-business-cloud-connector-edition.md)主题。 的[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)部分 > 值需要更改为其他装置或新网站的详细信息，请参见[单个站点的高可用性 (HA) 与多站点部署](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)[部署云连接器中的多个网站](deploy-multiple-sites-in-cloud-connector.md)的主题中。 
  
- **SiteName：**默认值为 **Site1**。你必须在部署云连接器之前更新该值，因为当通过运行 **Register-CcAppliance** 将设备注册到现有站点或新站点时，该 cmdlet 将使用 **SiteName** 来确定要注册到的站点。
    
     如果要将设备注册到新站点，**SiteName** 值必须唯一，并且与现有站点不同。 如果您想要注册装置向现有站点，**站点名**.ini 文件中的值必须与 Office 365 租户配置中定义的名称匹配。 如果要将配置文件从一个站点复制到另一个站点，请确保相应地更新每个站点的 **SiteName** 值。
    
- **ServerName：**服务器名称不应包含域名，且不应超过 15 个字符。
    
- **HardwareType:**如果未设置，或将值保留为空，将使用**标准**的默认值。 如果您打算部署云接头，可支持 500 个呼叫每个主机机[商务云连接器版的 Skype 的计划](plan-skype-for-business-cloud-connector-edition.md)中所述的较大版本，请使用**普通**。 用于支持 50 个呼叫小部署**最小值**。
    
- **Internet/公司网络/管理虚拟交换机**：添加已创建的虚拟交换机的名称。 对于管理虚拟交换机，只需保留默认值即可。 部署脚本将在部署开始时创建管理虚拟交换机，在部署结束时将其删除。
    
- **ManagementIPPrefix：**“网络”部分中的 ManagementIPPrefix 必须是不同于其他内部 IP 的子网。例如，如默认值所示，ManagementIPPrefix 为 192.168.213.0，而 AD IP 地址为 192.168.0.238。
    
    部署脚本会在每台虚拟机上创建管理网络适配器，分配管理 IP，并将其连接到管理虚拟交换机。这样可使主机服务器通过此管理网络连接到每台虚拟机并对其进行管理。部署结束时，会删除管理虚拟交换机。
    
- **基 VM 特定配置：**必须为**转换 CcIsoToVhdx** cmdlet 配置本部分中的设置。
    
    在准备基本虚拟机映像期间，基本虚拟机将连接到内部网络交换机。为使虚拟机能够访问 Internet，以下设置至关重要：
    
  - [Common]BaseVMIP：要分配给基本虚拟机的公司网络 IP 地址。
    
  - [Network]CorpnetDefaultGateway：要分配给基本虚拟机的默认网关。
    
  - [Network]CorpnetDNSIPAddress：要分配给基本虚拟机的 DNS IP 地址。
    
  - [Network]WSUSServer：Windows Server Update Service 的 IP 地址。
    
  - [Network]WSUSStatusServer：Windows Server Update Service 状态服务器的 IP 地址。
    
  - [Network]EnableReferSupport：用于定义在 IP/PBX 的中继配置上是启用还是禁用 SIP REFER 支持。
    
- **内部 IP：**
    
  - 请确保子网掩码 CorpnetIPPrefixLength 是正确的。
    
  - 请确保没有为这些内部的 Ip IP 冲突。
    
- **外部 IP：**
    
  - MR 公用 ip： 指定为非 NAT ExternalMRIPs 或 ExternalMRPublicIPs 的 nat。
    
  - ExternalSIPIPs 和 ExternalMRIPs 可以是相同的。
    
  - 请确保子网掩码 InternetIPPrefixLength 是正确的。
    
  - 请确保没有为这些外部 Ip IP 冲突。
    
- **网关：**
    
  - 如果只有一个网关，请删除辅助网关的部分。如果网关超过两个，请通过复制并粘贴现有部分、再进行更新来创建其他部分。
    
  - 请确保网关的 IP 地址和端口正确无误。
    
  - 要支持 PSTN 网关级别高可用性，请保留辅助网关，然后添加将使用的任何其他网关。 您可以复制和粘贴现有条目，然后更新该。
    
- （可选） 您可以更新的 LocalRoute 值来限制出站呼叫电话号码。
    
## <a name="download-the-bits-to-the-site-directory"></a>将 bits 下载到“网站目录”

运行以下 cmdlet，将 bits 和版本信息文件下载到**站点目录**：
  
```
Start-CcDownload
```

> [!NOTE]
> 只需对第一台设备执行此步骤。 
  
## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>通过下载的 ISO 文件准备基本虚拟磁盘 (VHDX)

此步骤将通过 Windows Server 2012 ISO 映像准备虚拟硬盘 (VHDX) 文件。 在部署期间，将使用 VHDX 创建虚拟机。 将创建一个临时的虚拟机 (VM 基) 和 Windows Server 2012 将安装的 ISO 文件。 创建虚拟机后，将安装一些必要组件，并应用最新的 Windows 更新。 最后，集中 (sysprep) 并清理基本虚拟机，仅保留生成的虚拟磁盘文件。
  
> [!NOTE]
> 只需对第一台设备执行此步骤。 
  
继续执行此步骤前，请确保已创建公司网络交换机。另外，请确认在 CloudConnector.ini 文件中正确配置以下设置：
  
- [网络]CorpnetSwitchName
    
- [公共]BaseVMIP
    
- [网络]CorpnetIPPrefixLength
    
- [网络]CorpnetDefaultGateway
    
- [网络]CorpnetDNSIPAddress
    
以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以将 ISO 映像转换为虚拟硬盘 (VHD)：
  
```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

指定 ISO 映像的完整路径，包括文件名。例如：C:\ISO\WindowsServer2012R2.iso。
  
创建的 VHD 文件存储在**网站目录**的 \Bits\VHD 文件夹中。 可以通过运行 **Get-CcSiteDirectory** 获取**网站目录**的路径。
  
> [!IMPORTANT]
> 默认情况下，不在基本虚拟机上配置代理设置。 如果代理服务器在您的网络环境中需要更新通过 Windows Update VM，则应添加-PauseBeforeUpdate 开关时运行"转换-CcIsoToVhdx"。 该脚本将暂停之前 Windows 更新，您将有机会来手动设置虚拟机上的代理。 在设置代理并且虚拟机可以访问 Internet 后，可恢复脚本以完成剩余的步骤。 
  
### <a name="create-vhds-for-a-multi-site-deployment"></a>为多站点部署创建 VHD

这是一个可选步骤，仅适用于多站点部署。
  
如果要部署多站点部署，不需要为每个站点将 ISO 转换的 VHD。你可以将为第一个站点创建的 VHDX 复制到第二个站点的主机服务器。
  
 将该文件复制到相同的文件位置 （**网站目录**\Bits\VHD 文件夹），并与其他网站的宿主服务器上相同的文件名。
  
## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>将 PowerShell 执行策略设置为 RemoteSigned

提供的 PowerShell 脚本要求将执行策略设置为 RemoteSigned。要查看当前设置，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：
  
```
Get-ExecutionPolicy
```

如果执行策略未设置为“RemoteSigned”，则运行以下 cmdlet 进行更改：
  
```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>更改主机上的本地组策略（1.4.1 版及更低版本）

> [!NOTE]
> 对于云连接器 1.4.2 版及更高版本，不需要执行此任务。 
  
在部署 Skype for Business 云连接器版本时已创建 CceService 帐户。 它运行云连接器管理服务，并要求卸载 cloudconnector.msi 的权限。 你必须更改云连接器主机上的组策略设置，指定用户注销时不会卸载用户注册表。 请执行以下步骤：
  
### <a name="to-change-the-group-policy-setting"></a>更改组策略设置

1. 通过运行 gpedit.msc 打开**组策略编辑器**。
    
2. 在“**组策略编辑器**”中，导航到“管理模板”>“系统”>“用户配置文件”>“在用户注销时不强制卸载用户注册表”。 
    
3. 将其值设置为**启用**。
    
## <a name="set-up-your-office-365-tenant"></a>设置你的 Office 365 租户

Office 365 租户与 Skype 的在线业务和 Office 365 中的电话系统是必需的。 请确保设置，然后再尝试使用云连接器配置您的租户。
  
一些 Office 365 安装步骤要求您使用远程 PowerShell 租户 (TRPS) 来配置 Office 365 租户。 **它应安装在主机服务器上。** 您也可以下载 Skype 的在线业务模块从 PowerShell:[Skype 业务在线，Windows PowerShell 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。
  
创建专用的 Skype 的业务管理员帐户的云连接器在线管理，例如 CceOnlineManagmentAdministrator。 设备将使用该帐户添加或删除设备、启用或禁用操作系统自动更新、启用或禁用二进制文件自动更新。 请将该帐户的密码设置为永不过期，从而无需在每次过期时为服务更改密码。
  

