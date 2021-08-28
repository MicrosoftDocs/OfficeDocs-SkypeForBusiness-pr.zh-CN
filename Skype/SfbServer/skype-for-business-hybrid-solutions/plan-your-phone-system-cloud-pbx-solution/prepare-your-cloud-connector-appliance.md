---
title: 准备云连接器设备
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
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 了解如何准备云连接器设备进行部署，以及如何与 电话系统 (PBX) 。
ms.openlocfilehash: 255b276ebb0d192f876d07e318cf94ccf3698a1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589996"
---
# <a name="prepare-your-cloud-connector-appliance"></a>准备云连接器设备

> [!Important]
> 云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。 一旦组织升级到 Teams，了解如何使用直接路由将本地电话Teams[连接到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

了解如何准备云连接器设备进行部署，以及如何与 电话系统 (PBX) 。

本部分介绍如何获取云Skype for Business 云连接器版本文件、安装云连接器软件以及准备云连接器设备进行部署。 完成本节的所有步骤后，即可为单个站点或多个站点部署云连接器。 如果你有现有的云连接器部署，并且尚未升级到云连接器版本 2.1，请参阅升级到云连接器 [的新版本](upgrade-to-a-new-version-of-cloud-connector.md)。

> [!NOTE]
> Microsoft 支持云连接器版本 2.1 版当前版本。 如果配置了自动更新，云连接器将自动更新。 如果配置了手动更新，则需要在版本 2.1 发布后 60 天内升级到版本 2.1。 Microsoft 将在 2.1 版发布后的 60 天内支持以前的版本，以便你有时间进行升级。 

> [!NOTE]
> 对于云连接器版本 2.1 及更高版本，主机设备必须.NET Framework 4.6.1 或更高版本。 

> [!IMPORTANT]
> 若要成功部署，在运行 cmdlet 以配置Skype for Business 云连接器版本，请始终使用与启动会话相同的控制台会话。 避免在部署和配置期间切换到不同的会话。 

> [!NOTE]
> 仅对部署中的第一个设备执行一些步骤：为站点目录创建共享、下载位以及从 Windows Server ISO 映像准备虚拟硬盘 (VHDX) 文件。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>下载Skype for Business 云连接器版本安装程序

1. 在将运行云连接器 VM 的主机服务器上，下载安装文件 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) ：。 

    > [!IMPORTANT]
    > 在安装云连接器期间，主机服务器必须能够访问 Internet，因为在安装过程中会下载其他文件。 

2. 在安装过程中运行安装程序并接受默认值。

3. 确认安装成功完成。

## <a name="verify-the-installation-and-configure-the-environment"></a>验证安装并配置环境

1. 以管理员角色打开 PowerShell 控制台，并确认Skype for Business 云连接器版本 cmdlet 可用：

   ```powershell
   Get-Command *-Cc*
   ```

    该命令应返回一个 cmdlet 列表Skype for Business 云连接器版本。

2. VHD、SfBBits 和 VersionInfo 文件将存储在站点 **目录中**。

    可以通过以下 cmdlet 查找 **站点** 目录的位置：

   ```powershell
   Get-CcSiteDirectory
   ```

    该命令应返回文件系统中的位置。 该位置可以是本地文件夹或文件共享。 站点目录的默认位置 **是** ：%USERPROFILE%\CloudConnector\SiteRoot。 默认位置应更改为在每个站点中创建的第一个设备的文件共享。

    你选择的位置必须是：

   - 在每个站点中创建的第一个设备上创建。

   - 由其他主机服务器访问的共享文件夹 (一) 设备。

     若要将 **网站目录** 设置为默认位置，请运行以下 cmdlet：

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    如果要为站点部署高可用性 (HA) ，请确保运行 cmdlet 将站点 **目录** 设置为站点内每台主机服务器上相同的位置。

    登录并部署站点中的每台设备时，请确保你的当前登录帐户对站点目录具有正确的 **访问权限**。

3. 设备 **目录** 是证书的本地工作根目录Skype for Business 云连接器版本，以及保存外部证书、实例和日志的位置。 默认位置为：%USERPROFILE%\CloudConnector\ApplianceRoot。

    若要查找设备目录 **的位置，** 请运行以下 cmdlet：

   ```powershell
   Get-CcApplianceDirectory
   ```

    若要将 **设备目录** 设置为默认位置，请运行以下 cmdlet：

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    设备目录应设置为设备上的本地文件夹。 应仅在开始部署 **设备目录** 之前设置Skype for Business 云连接器版本目录。 如果在部署后更改它，则需要重新部署主机服务器。

    > [!IMPORTANT]
    > 设备目录 **的路径不得** 包含任何空格。

## <a name="set-the-path-for-the-external-edge-certificate"></a>设置外部边缘证书的路径

- 运行以下 cmdlet 以设置外部边缘证书的路径（包括文件名）。 例如：C：\certs\cce\ap.contoso.com.pfx。 证书必须包含私钥。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > 请注意，-Target 参数特定于版本 1.4.2 及更高版本。 

    指定外部证书的完整路径，包括文件名。 证书可以存储在本地或文件共享中。 如果证书存储在共享文件夹中，则必须在每个站点的第一个设备中创建共享文件夹，并且该共享文件夹必须可由属于同一站点的其他设备访问。 此 cmdlet 将外部证书复制到 **设备目录**。

    > [!IMPORTANT]
    > **如果已更新到云连接器版本 1.4.2** 或更高版本，请确保准备好的外部证书包含私钥和完整证书链，包括根 CA 证书和中间 CA 证书。 **如果你尚未更新到云连接器版本 1.4.2，** 请确保准备好的外部证书包含私钥。 默认情况下，此外部证书必须由证书颁发机构Windows信任。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>设置外部 PSTN 网关/SBC 证书的路径

如果在中介服务器和 PSTN 网关/SBC 之间使用 TLS，请运行以下 cmdlet 来设置网关证书的路径（包括文件名）。 例如：C：\certs\cce\sbc.contoso.com.cer。 证书必须包含分配给网关的证书的根 CA 和中间链：

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> 请注意，-Target 参数特定于版本 1.4.2 及更高版本。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>在 Hyper-V 管理器中创建虚拟交换机

1. 打开 **Hyper-V管理器**  >  **虚拟交换机管理器"，** 然后选择"**新建虚拟交换机管理器"。**

2. 创建外部虚拟交换机，并绑定到连接到内部网络域的物理网络适配器：

    选择 **"允许管理操作系统为此虚拟交换机共享** 此网络适配器"。

3. 创建外部虚拟交换机，并绑定到路由到 Internet 的物理网络适配器：

    取消选择 **"允许管理操作系统为此虚拟交换机共享** 此网络适配器"。

4. 设置将外围网络连接到内部网络域 **SfB CCE Corpnet 交换机的交换机的名称**。

    设置将外围网络连接到 Internet **SfB CCE Internet 交换机的交换机的名称**。

## <a name="update-the-cloudconnectorini-configuration-file"></a>更新CloudConnector.ini配置文件

使用CloudConnector.ini规划部署参数主题[中](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)收集的信息准备部署[Skype for Business 云连接器版本文件。](plan-skype-for-business-cloud-connector-edition.md)

若要更新文件，请首先运行以下 cmdlet，获取示例 (CloudConnector.Sample.ini) ：

```powershell
Export-CcConfigurationSampleFile
```

示例模板存储在设备 **目录中**。

使用环境的值更新该文件后，将文件CloudConnector.ini设备 **目录中**。 你可以运行 **Get-CcApplianceDirectory** 来确定设备 **目录的路径**。

在更新.ini文件时，请考虑以下事项：

> [!NOTE]
> 本节并未讨论.ini文件的所有值，此处仅介绍有特别注意事项的值。 有关完整列表，请参阅 Plan [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) [for Skype for Business 云连接器版本](plan-skype-for-business-cloud-connector-edition.md)一节。 有关需要为其他设备或新站点更改哪些值的详细信息，请参阅主题部署云连接器中的多个站点中的高可用性[ (HA) ](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)与多站点部署相比的单站点。 [](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName：** 默认值为 **Site1**。 在部署云连接器之前，必须更新它，因为在运行 **Register-CcAppliance** 以将设备注册到现有或新站点时，该 cmdlet 将使用 **SiteName** 确定要注册的站点。

     如果要将设备注册到新站点 **，SiteName** 的值必须唯一且不同于现有站点。 如果要将设备注册到现有站点，.ini 文件中 **SiteName** 的值必须与 Microsoft 365 或 Office 365 配置中定义的名称相匹配。 如果要将配置文件从一个站点复制到另一个站点，请确保相应地更新每个 **站点的 SiteName** 的值。

- **ServerName：** 服务器名称不应包含域名，且应限制为 15 个字符。

- **HardwareType：** 如果未将此值设置为或保留为 null，则使用 **Normal** 的默认值。 如果你计划部署云连接器的较大版本以支持每个主机 500 个并发呼叫，请使用 **Normal，** 如 Plan [for Skype for Business 云连接器版本 中所述](plan-skype-for-business-cloud-connector-edition.md)。 对于 **支持** 50 个并发呼叫的较小部署，请使用 Minimum。

- **Internet/公司网络/管理虚拟交换机：** 添加已创建的虚拟交换机的名称。 对于管理虚拟交换机，保留默认值。 部署脚本将在部署开始时创建管理虚拟交换机，部署完成后将其删除。

- **ManagementIPPrefix：** "网络"部分中的 ManagementIPPrefix 必须是与其他内部 IP 不同的子网。 例如，如默认值所示，ManagementIPPrefix 为 192.168.213.0，而 AD IPAddress 为 192.168.0.238。

    部署脚本在每个虚拟机上创建管理网络适配器，分配管理 IP，并将其连接到管理虚拟交换机。 这使主机服务器可以通过此管理网络连接到和管理每台虚拟机。 部署完成后，将删除管理虚拟交换机。

- **基本虚拟机特定配置：设置** 为 **Convert-CcIsoToVhdx** cmdlet 配置本节中的配置。

    在基本 VM 映像准备过程中，基本 VM 将连接到内部网络交换机。 以下设置对于 VM 能够访问 Internet 至关重要：

  - [常见]BaseVMIP：要分配给基本虚拟机的公司网络 IP 地址。

  - [网络]CorpnetDefaultGateway：要分配给基本 VM 的默认网关。

  - [网络]CorpnetDNSIPAddress：要分配给基本虚拟机的 DNS IP 地址。

  - [网络]WSUSServer：Windows服务器的 IP 地址。

  - [网络]WSUSStatusServer：Windows服务器更新服务状态服务器的 IP 地址。

  - [网络]EnableReferSupport：这将定义在 IP/PBX 的中继配置上是启用还是禁用 SIP REFER 支持。

- **内部 IP：**

  - 确保子网掩码 CorpnetIPPrefixLength 正确。

  - 确保这些内部 IP 没有 IP 冲突。

- **外部 IP：**

  - 对于 MR 公共 IP：为非 NAT 指定 ExternalMRIPs，为 NAT 指定 ExternalMRPublicIPs。

  - ExternalSIPIPs 和 ExternalMRIPs 可以相同。

  - 确保子网掩码 InternetIPPrefixLength 正确。

  - 确保这些外部 IP 没有 IP 冲突。

- **网关：**

  - 如果只有一个网关，请删除辅助网关的部分。 如果网关超过两个，请通过复制并粘贴现有部分，然后更新来创建其他部分。

  - 确保网关网关的 IP 地址 (端口) 正确。

  - 要支持 PSTN 网关级别 HA，请离开辅助网关，并添加将使用的其他任何网关。 您可以复制并粘贴现有条目，然后更新它。

- （可选）您可以更新 LocalRoute 值以限制出站呼叫号码。

## <a name="download-the-bits-to-the-site-directory"></a>将位下载到网站目录

运行以下 cmdlet 以将 bits 和 version 信息文件下载到 **网站目录**：

```powershell
Start-CcDownload
```

> [!NOTE]
> 只需为第一个设备执行此步骤。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>从下载的 ISO (VHDX) 准备基本虚拟磁盘

此步骤准备虚拟硬盘 (ISO 映像) VHDX Windows Server 2012文件。 VHDX 将用于在部署期间创建虚拟机。 将创建一个 (虚拟机) 虚拟机，Windows Server 2012 ISO 文件安装该虚拟机。 创建 VM 后，将安装一些必要的组件，并应用Windows更新。 最后，将在 sysprep (基本虚拟机) 并清理，仅保留生成的虚拟磁盘文件。

> [!NOTE]
> 只需为第一个设备执行此步骤。 

在继续此步骤之前，请确保已创建公司网络交换机。 此外，确认以下设置已正确配置在CloudConnector.ini文件中：

- [网络]CorpnetSwitchName

- [常见]BaseVMIP

- [网络]CorpnetIPPrefixLength

- [网络]CorpnetDefaultGateway

- [网络]CorpnetDNSIPAddress

以管理员角色启动 PowerShell 控制台并运行以下 cmdlet，以将 ISO 映像转换为 VHD (虚拟) ：

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

指定 ISO 映像的完整路径（包括文件名）。 例如：C：\ISO\WindowsServer2012R2.iso。

创建的 VHD 文件存储在站点目录\Bits\VHD 文件夹中。 可以通过运行 **Get-CcSiteDirectory** 获取站点目录的路径。 

> [!IMPORTANT]
> 默认情况下，不会在基本 VM 上配置代理设置。 如果网络环境中需要代理才能通过 Windows Update 更新 VM，应在运行"Convert-CcIsoToVhdx"时添加 -PauseBeforeUpdate 开关。 脚本将在更新Windows暂停，并且你将有机会在 VM 上手动设置代理。 设置代理并且 VM 可以访问 Internet 后，可以恢复脚本以完成其余步骤。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>为多站点部署创建 VHD

这是一个仅适用于多站点部署的可选步骤。

如果要部署多站点部署，则无需将每个站点的 ISO 转换为 VHD。 可以将为第一个站点创建的 VHDX 复制到第二个站点的主机服务器。

 将文件复制到主机服务器上 (站点目录 \Bits\VHD 文件夹) ，并使用相同的文件名复制到其他站点的相同文件位置。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>将 PowerShell 执行策略设置为 RemoteSigned

提供的 PowerShell 脚本要求将执行策略设置为 RemoteSigned。 To see the current setting， open a PowerShell console as administrator and then run the following cmdlet：

```powershell
Get-ExecutionPolicy
```

如果未设置为"RemoteSigned"，请运行以下 cmdlet 来更改它：

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>更改 1.4.1 (1.4.1 版主机上的本地组策略) 

> [!NOTE]
> 云连接器版本 1.4.2 和更高版本不需要此任务。 

CceService 帐户是在部署期间Skype for Business 云连接器版本帐户。 它运行云连接器管理服务，并且需要卸载cloudconnector.msi。 您必须更改云连接器主机上的组策略设置，以指定用户注销时不应卸载用户注册表。 请按照以下步骤操作：

### <a name="to-change-the-group-policy-setting"></a>更改组策略设置

1. 通过运行 gpedit.msc 打开组策略编辑器。

2. 在 **组策略编辑器** 中，导航到"> System > UserProfile >在用户注销时不强制卸载用户注册表。 

3. 将它的值设置为 **Enabled**。

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>设置组织Microsoft 365或Office 365组织

需要Microsoft 365 Office 365 Online Skype for Business 电话系统组织。 在尝试使用云连接器之前，请确保已设置和配置租户。

某些Microsoft 365和Office 365设置步骤要求使用租户远程 PowerShell (TRPS) 配置 Microsoft 365 或 Office 365 组织。 **这应安装在主机服务器上。** 可以从以下版本下载 Skype for Business Online 模块[：Skype for Business Online，Windows PowerShell模块](https://www.microsoft.com/download/details.aspx?id=39366)。

创建一个Skype for Business管理员帐户进行云连接器联机管理，例如 CceOnlineManagmentAdministrator。 设备将将此帐户用于添加或删除设备、启用或禁用自动更新操作系统、启用或禁用二进制自动更新。 将该帐户的密码设置为永不过期，这样一来，你无需每次过期时都为服务更改密码。