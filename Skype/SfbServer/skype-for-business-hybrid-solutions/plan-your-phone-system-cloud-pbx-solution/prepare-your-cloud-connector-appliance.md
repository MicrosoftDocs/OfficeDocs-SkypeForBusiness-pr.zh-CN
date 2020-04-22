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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 了解如何为 Office 365 （云 PBX）中的电话系统准备部署和使用云连接器设备。
ms.openlocfilehash: 21943dfd8b86bfeabb4cbd28b501b80a3f2b5c45
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779238"
---
# <a name="prepare-your-cloud-connector-appliance"></a>准备云连接器设备

了解如何为 Office 365 （云 PBX）中的电话系统准备部署和使用云连接器设备。

本节介绍如何获取 Skype for Business 云连接器版本安装文件、安装云连接器软件以及准备云连接器设备以进行部署。 完成本节中的所有步骤后，你将准备为单个网站或多个网站部署云连接器。 如果你已有云连接器部署且尚未升级到云连接器版本2.1，请参阅[升级到新版本的云连接器](upgrade-to-a-new-version-of-cloud-connector.md)。

> [!NOTE]
> Microsoft 支持当前版本的云连接器版本2.1。 如果配置了自动更新，云连接器将自动更新。 如果配置了手动更新，则需要在版本60天内将其升级到版本2.1。 Microsoft 将在2.1 发布后的60天内支持早期版本，以允许你进行升级。 

> [!NOTE]
> 对于云连接器版本2.1 及更高版本，主机设备必须安装了 .NET Framework 4.6.1 或更高版本。 

> [!IMPORTANT]
> 若要成功进行部署，运行 cmdlet 以配置 Skype for Business 云连接器版本时，请始终使用与在中启动的相同的控制台会话。 避免在部署和配置过程中切换到不同的会话。 

> [!NOTE]
> 仅对部署中的第一台设备执行一些步骤：为网站目录创建共享，下载 bits，并从 Windows Server ISO 映像准备虚拟硬盘（VHDX）文件。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>下载 Skype for Business 云连接器版本安装程序

1. 在将运行云连接器虚拟机的主机服务器上，下载安装文件： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。 

    > [!IMPORTANT]
    > 在安装云连接器的过程中，主机服务器必须能够访问 Internet，因为在安装过程中会下载其他文件。 

2. 运行安装程序，并在安装过程中接受默认值。

3. 确认安装已成功完成。

## <a name="verify-the-installation-and-configure-the-environment"></a>验证安装并配置环境

1. 以管理员身份打开 PowerShell 控制台，并使用以下 cmdlet 确认是否可以使用 Skype for Business 云连接器版本 cmdlet：

   ```powershell
   Get-Command *-Cc*
   ```

    该命令应返回适用于 Skype for Business 云连接器版本的 cmdlet 的列表。

2. Vhd、SfBBits 和 VersionInfo 文件将存储在**网站目录**中。

    您可以使用以下 cmdlet 找到**网站目录**的位置：

   ```powershell
   Get-CcSiteDirectory
   ```

    该命令应返回文件系统中的某个位置。 该位置可以是本地文件夹或文件共享。 "**网站目录**" 的默认位置是：%USERPROFILE%\CloudConnector\SiteRoot。 应将默认位置更改为在每个站点中创建的第一个设备上的文件共享。

    您选择的位置必须为：

   - 在每个站点中创建的第一个设备上创建。

   - 同一站点中的其他主机服务器（设备）可访问的共享文件夹。

     若要将**网站目录**设置为默认位置以外的位置，请运行以下 cmdlet：

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    如果要为网站部署高可用性（HA），请确保运行 cmdlet 以将**网站目录**设置为站点中每台主机服务器上的相同位置。

    当您登录并在站点中部署每台设备时，请确保您的当前登录帐户具有对**网站目录**的正确访问权限。

3. **设备目录**是 Skype For Business 云连接器版本的本地工作根目录，以及保存外部证书、实例和日志的位置。 默认位置为：%USERPROFILE%\CloudConnector\ApplianceRoot。

    若要查找**设备目录**的位置，请运行以下 cmdlet：

   ```powershell
   Get-CcApplianceDirectory
   ```

    若要将**设备目录**设置为默认位置以外的位置，请运行以下 cmdlet：

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    应将设备目录设置为设备上的本地文件夹。 你应仅在启动 Skype for Business 云连接器版本部署之前设置**设备目录**。 如果在部署后更改它，则需要重新部署主机服务器。

    > [!IMPORTANT]
    > **设备目录**的路径不能包含任何空格。

## <a name="set-the-path-for-the-external-edge-certificate"></a>设置外部边缘证书的路径

- 运行以下 cmdlet 以设置外部边缘证书的路径，包括文件名。 例如： C:\certs\cce\ap.contoso.com.pfx。 证书必须包含私钥。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > 请注意，-Target 参数特定于1.4.2 版和更高版本。 

    指定外部证书的完整路径，包括文件名。 证书可以存储在本地或文件共享中。 如果证书存储在共享文件夹中，则必须在每个站点的第一个设备上创建共享文件夹，并且该共享文件夹必须可供属于同一站点的其他设备访问。 此 cmdlet 可将外部证书复制到**设备目录**。

    > [!IMPORTANT]
    > **如果已更新到云连接器1.4.2 版或更高版本**，请确保准备好的外部证书包含私钥和完整证书链，包括根 ca 证书和中间 ca 证书。 **如果您尚未更新云连接器1.4.2 版**，请确保准备好的外部证书包含私钥。 此外部证书必须由 Windows 默认情况下受 Windows 信任的证书颁发机构颁发。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>设置外部 PSTN 网关/SBC 证书的路径

如果要在中介服务器和 PSTN 网关/SBC 之间使用 TLS，请运行以下 cmdlet，以将路径（包括文件名）设置为网关证书。 例如： C:\certs\cce\sbc.contoso.com.cer。 证书必须包含为分配给网关的证书的根 CA 和中间链：

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> 请注意，-Target 参数特定于1.4.2 版和更高版本。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>在 Hyper-v 管理器中创建虚拟交换机

1. 打开**hyper-v 管理器** > **虚拟交换机管理器**，然后选择 "**新建虚拟交换机管理器**"。

2. 创建外部虚拟交换机并将其绑定到连接到内部网络域的物理网络适配器：

    为此虚拟交换机选择 "**允许管理操作系统共享此网络适配器**"。

3. 创建外部虚拟交换机并将其绑定到路由到 Internet 的物理网络适配器：

    取消选择 "**允许管理操作系统为此虚拟交换机共享此网络适配器**"。

4. 设置将外围网络连接到内部网络域的交换机的名称**SFB CCE 公司网络交换机**。

    设置将外围网络连接到 Internet **SFB CCE Internet 交换机**的交换机的名称。

## <a name="update-the-cloudconnectorini-configuration-file"></a>更新 Cloudconnector.ini 配置文件

使用在[Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)主题中的[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)中收集的信息准备 cloudconnector.ini 文件。

若要更新该文件，请先运行以下 cmdlet 以获取示例模板（Cloudconnector.ini）：

```powershell
Export-CcConfigurationSampleFile
```

示例模板存储在**设备目录**中。

在使用您的环境的值对其进行更新之后，请在**设备目录**中将该文件另存为 cloudconnector.ini。 您可以运行**set-ccappliancedirectory**以确定**设备目录**的路径。

更新 .ini 文件时，请考虑以下事项：

> [!NOTE]
> 并非 .ini 文件的所有值都在此部分中进行讨论，此处仅介绍了那些具有特殊注意事项的值。 有关完整列表，请参阅[Plan For Skype For Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)主题中的 "[确定部署参数](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)" 部分。 有关需要为其他设备或新网站更改的值的详细信息，请参阅在[云连接器中部署多个站点](deploy-multiple-sites-in-cloud-connector.md)中[与多站点部署相比的具有高可用性（HA）的单站点部署](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)。 

- **SiteName：** 默认值为**Site1**。 您必须在部署云连接器之前对其进行更新，因为在运行**register-ccappliance**将设备注册到现有或新网站时，cmdlet 将使用**SiteName**确定要注册的网站。

     如果要将设备注册到新网站， **SiteName**的值必须是唯一的，并且不同于现有网站。 如果要将设备注册到现有站点，则 .ini 文件中的**SiteName**的值必须与在 Office 365 组织配置中定义的名称相匹配。 如果要将配置文件从一个网站复制到另一个网站，请确保相应地为每个网站更新**SiteName**的值。

- **ServerName：** 服务器名称不应包含域名，且不应超过15个字符。

- **HardwareType：** 如果不设置或将值保留为 null，则将使用默认值**Normal** 。 如果您计划部署更大版本的云连接器以支持按[plan For Skype for Business 云连接器版本](plan-skype-for-business-cloud-connector-edition.md)中所述，每台主机同时支持500并发呼叫，请使用**Normal** 。 对支持同时调用50的较小部署使用**最小值**。

- **Internet/公司网络/管理虚拟交换机：**：添加已创建的虚拟交换机的名称。 对于管理虚拟交换机，保留默认值。 部署脚本将在部署开始时创建管理虚拟交换机，并在部署完成后将其删除。

- **ManagementIPPrefix：**"网络" 部分中的 ManagementIPPrefix 必须是其他内部 Ip 的不同子网。 例如，默认值为 ManagementIPPrefix 为192.168.213.0，而 AD IPAddress 为192.168.0.238。

    部署脚本在每个虚拟机上创建一个管理网络适配器，分配一个管理 IP，并将其连接到管理虚拟交换机。 这使主机服务器可以通过此管理网络连接并管理每个虚拟机。 部署完成后，将删除管理虚拟交换机。

- **基本虚拟机特定配置：** 必须为**convert-ccisotovhdx** cmdlet 配置本节中的设置。

    在基本 VM 映像准备期间，基本虚拟机将连接到内部网络交换机。 若要使 VM 能够访问 Internet，以下设置至关重要：

  - 共BaseVMIP：要分配给基本虚拟机的企业网络 IP 地址。

  - NetworkCorpnetDefaultGateway：要分配给基本虚拟机的默认网关。

  - NetworkCorpnetDNSIPAddress：要分配给基本虚拟机的 DNS IP 地址。

  - NetworkWSUSServer： Windows Server Update Service 的 IP 地址。

  - NetworkWSUSStatusServer： Windows Server Update Service 状态服务器的 IP 地址。

  - NetworkEnableReferSupport：此操作将定义是否在 IP/PBX 的中继配置上启用或禁用 SIP。

- **内部 Ip：**

  - 请确保子网掩码 CorpnetIPPrefixLength 正确无误。

  - 请确保这些内部 Ip 没有 IP 冲突。

- **外部 Ip：**

  - 对于尊敬的公共 IP，请为非 NAT 或 ExternalMRPublicIPs 指定 ExternalMRIPs for NAT。

  - ExternalSIPIPs 和 ExternalMRIPs 可以相同。

  - 请确保子网掩码 InternetIPPrefixLength 正确无误。

  - 请确保这些外部 Ip 没有 IP 冲突。

- **版**

  - 如果只有一个网关，请删除辅助网关的部分。 如果您有两个以上的网关，请通过复制并粘贴现有分区并将其更新来创建其他分区。

  - 请确保网关的 IP 地址和端口正确无误。

  - 若要支持 PSTN 网关级别 HA，请保留辅助网关，然后添加将使用的任何其他网关。 您可以复制并粘贴现有条目，然后对其进行更新。

- （可选）您可以更新 LocalRoute 值以限制出站呼叫号码。

## <a name="download-the-bits-to-the-site-directory"></a>将 bits 下载到网站目录

运行以下 cmdlet 以将 bits 和版本信息文件下载到**网站目录**：

```powershell
Start-CcDownload
```

> [!NOTE]
> 只需为第一台设备执行此步骤。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>从下载的 ISO 文件准备基本虚拟磁盘（VHDX）

此步骤将从 Windows Server 2012 ISO 映像准备虚拟硬盘（VHDX）文件。 VHDX 将用于在部署过程中创建虚拟机。 将创建一个临时虚拟机（基本虚拟机），并从 ISO 文件安装 Windows Server 2012。 创建虚拟机后，将会安装一些必要的组件，并将应用最新的 Windows 更新。 最终，基本虚拟机将进行一般化（sysprep）和清理，仅留下生成的虚拟磁盘文件。

> [!NOTE]
> 只需为第一台设备执行此步骤。 

在继续执行此步骤之前，请确保已创建公司网络交换机。 此外，请确认 Cloudconnector.ini 文件中正确配置了以下设置：

- NetworkCorpnetSwitchName

- 共BaseVMIP

- NetworkCorpnetIPPrefixLength

- NetworkCorpnetDefaultGateway

- NetworkCorpnetDNSIPAddress

以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以将 ISO 映像转换为虚拟硬盘（VHD）：

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

指定 ISO 映像的完整路径，包括文件名。 例如： C:\ISO\WindowsServer2012R2.iso。

创建的 VHD 文件存储在 "**网站目录**" \Bits\VHD 文件夹中。 您可以通过运行**get-ccsitedirectory**获取**网站目录**的路径。

> [!IMPORTANT]
> 默认情况下，不会在基本虚拟机上配置代理设置。 如果网络环境中需要代理通过 Windows 更新来更新 VM，则应在运行 "Convert-ccisotovhdx" 时添加-PauseBeforeUpdate 开关。 脚本将在 Windows 更新之前暂停，并且你将有机会在 VM 上手动设置代理。 在设置代理且 VM 可以访问 Internet 后，可以恢复脚本以完成其余步骤。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>为多站点部署创建 Vhd

这是一个仅适用于多站点部署的可选步骤。

如果要部署多站点部署，则无需将 ISO 转换为每个站点的 VHD。 您可以将为第一个站点创建的 VHDX 复制到第二个站点的主机服务器。

 将该文件复制到主机服务器上的相同文件位置（**网站目录**\Bits\VHD 文件夹），并使用相同的文件名在其他站点的主机服务器上。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>将 PowerShell 执行策略设置为 RemoteSigned

提供的 PowerShell 脚本要求将执行策略设置为 RemoteSigned。 若要查看当前设置，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：

```powershell
Get-ExecutionPolicy
```

如果未设置为 "RemoteSigned"，请运行以下 cmdlet 来更改它：

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>更改主机上的本地组策略（版本1.4.1 和更早版本）

> [!NOTE]
> 云连接器版本1.4.2 和更高版本不需要执行此任务。 

在 Skype for Business 云连接器版本部署过程中，将创建 CceService 帐户。 它运行云连接器管理服务，并需要具有卸载 cloudconnector.ini 的权限。 您必须更改云连接器主机上的组策略设置，以指定用户注销时不应卸载用户注册表。 请按照以下步骤操作：

### <a name="to-change-the-group-policy-setting"></a>更改组策略设置

1. 通过运行 gpedit.msc 打开**组策略编辑器**。

2. 在 "**组策略编辑器**" 中，导航到 "管理模板" > System > UserProfile > 不要在用户注销时强制卸载用户注册表。 

3. 将其值设置为 "**启用**"。

## <a name="set-up-your-office-365-organization"></a>设置 Office 365 组织

需要具有 Office 365 中的 Skype for Business Online 和电话系统的 Office 365 组织。 在尝试使用云连接器之前，请确保已设置并配置租户。

某些 Office 365 安装步骤要求使用租户远程 PowerShell （TRPS）配置 Office 365 组织。 **此项应安装在主机服务器上。** 您可以从： [skype For Business online、Windows PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)下载适用于 PowerShell 的 skype For business online 模块： Skype For business online。

为云连接器在线管理创建专用的 Skype for Business 管理员帐户，例如 CceOnlineManagmentAdministrator。 设备将使用此帐户添加或删除设备、启用或禁用自动 OS 更新、启用或禁用自动二进制更新。 将此帐户的密码设置为永不过期，这样就无需在每次过期时为其更改服务。


