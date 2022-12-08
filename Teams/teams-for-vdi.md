---
title: 适用于虚拟化桌面基础结构的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在虚拟化桌面基础结构 (VDI) 环境中运行 Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3193b48559fdfc941181963e493d73668bef52
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307747"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用 Microsoft Teams 的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是虚拟化技术，用于在数据中心的集中式服务器上托管桌面操作系统和应用程序。 这为具有完全安全且合规的集中式源的用户提供了完整且个性化的桌面体验。

虚拟化环境中的 Teams 支持聊天和协作。 此外，Azure 虚拟桌面、Citrix 和 VMware 平台还支持通话和会议功能。

Teams 还支持虚拟环境中的多个配置。 这些模式包括 VDI、专用模式、共享模式、持久模式和非持久性模式。 功能处于持续开发阶段，并定期添加，功能将随着时间的推移而扩展。

在虚拟化环境中使用 Teams 可能与在非虚拟化环境中使用 Teams 稍有不同。 例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。

若要确保获得最佳用户体验，请按照本文中的指南进行操作。

> [!Note]
> 有关不同平台上的 Teams VDI 的详细信息，请参阅 [按平台划分的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 上的 Teams 组件

在虚拟化环境中使用 Teams 需要以下组件。

- **虚拟化代理**：虚拟化提供程序的资源和连接管理器，例如 Azure
- **虚拟桌面**：运行 Teams 的虚拟机 (VM) 堆栈
- **瘦客户端**：用户以物理方式与之交互的设备
- **Teams 桌面应用**：Teams 桌面客户端应用

## <a name="teams-on-vdi-requirements"></a>VDI 上的 Teams 要求

### <a name="virtualization-provider-requirements"></a>虚拟化提供程序要求

Teams 桌面应用已与领先的虚拟化解决方案提供商一起验证。 对于多个市场提供商，我们建议你咨询虚拟化解决方案提供商，以确保满足最低要求。
  
目前，具有音频/视频 (AV) 优化的 VDI 上的 Teams 已通过 Azure 虚拟桌面、Citrix 和 VMware 认证。 查看本部分中的信息，确保满足正确功能的所有要求。

### <a name="platforms-certified-for-teams"></a>Teams 认证的平台

以下平台具有适用于 Teams 的虚拟桌面基础结构解决方案。

|平台|解决方案|
|----|---|
|![表示Microsoft的徽标。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虚拟桌面</a>，<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![表示 Citrix 的徽标。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a> |
|![表示 VMware 的徽标。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虚拟桌面

Azure 虚拟桌面为 VDI 上的 Teams 提供 AV 优化。 若要详细了解要求和安装，请参阅 [在 Azure 虚拟桌面上使用 Teams](/azure/virtual-desktop/teams-on-wvd)。

### <a name="windows-365"></a>Windows 365

Windows 365使用 Azure 虚拟桌面提供的 AV 优化来确保从云电脑获得最佳 Teams 体验。 若要详细了解要求和安装，请参阅 [在云电脑上使用 Teams](/windows-365/enterprise/teams-on-cloud-pc)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虚拟应用和桌面要求

Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的 Teams 提供 AV 优化。 借助 Citrix 虚拟应用和桌面，除了聊天和协作外，VDI 上的 Teams 还支持通话和会议功能。

可以在 Citrix 下载站点下载最新版本的 [Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) 虚拟应用和桌面。  (首先需要登录。) 默认情况下，必要的组件将捆绑到 [Citrix 工作区应用中， (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虚拟传递代理 (VDA) 。 无需在 CWA 或 VDA 上安装任何其他组件或插件。

有关最新的服务器和客户端要求，请参阅 Citrix 网站上的[优化 Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) 一文。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon 工作区和桌面要求

VMware Horizon 是用于跨混合云安全交付虚拟桌面和应用的新式平台。 为了提供出色的最终用户体验，VMware Horizon 为 Teams 提供了媒体优化。 此优化提高了虚拟桌面和应用的整体工作效率，并增强了使用 Teams 进行通话和开会时的用户体验。

可以从 VMware 下载页下载最新版本的 [VMware](https://customerconnect.vmware.com/downloads/#all_products) Horizon。 默认情况下，所需的媒体优化组件是 Horizon 代理和 Horizon 客户端的一部分，无需安装任何其他插件即可使用 Teams 优化功能。

若要获取有关如何为 Teams 配置媒体优化的最新要求和说明，请参阅 VMware 网站上的[为 Microsoft Teams 配置媒体优化](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)一文。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安装或更新 Teams 桌面应用

可以使用每台计算机安装或使用 MSI 包的按用户安装部署适用于 VDI 的 Teams 桌面应用。 决定使用哪种方法取决于是使用持久性设置还是非持久性设置，以及组织的关联功能需求。

对于专用的持久安装，每台计算机和每用户安装都行得当。 但是，对于非持久性设置，Teams 需要按计算机安装才能高效工作。 请参阅 [非持久性设置](#non-persistent-setup) 部分。

对于每台计算机安装，将禁用自动更新。 这意味着，若要更新 Teams 应用，必须卸载当前版本才能更新到较新版本。 通过每用户安装，将启用自动更新。

> [!IMPORTANT]
> 使 VDI 环境中的 Teams 桌面应用保持最新。 不支持发布日期早于 [当前版本的发布日期](/officeupdates/teams-app-versioning) 90 天以上的 Teams 桌面应用版本。 不支持的 Teams 桌面应用版本向用户显示阻止页面，并请求他们更新其应用。

对于大多数 VDI 部署，建议使用每台计算机安装部署 Teams。 若要更新到最新的 Teams 版本，请从卸载过程开始，然后执行最新的 Teams 版本部署。

若要使 VDI 环境中的 Teams AV 优化正常工作，瘦客户端设备必须有权访问 Internet。 如果瘦客户端设备上无法使用 Internet 访问，则优化启动不会成功。 这意味着用户处于非优化的媒体状态。

#### <a name="dedicated-persistent-setup"></a>专用持久设置

在专用持久设置中，用户在注销后会保留用户的本地操作系统更改。 对于持久安装，Teams 支持每用户和每计算机安装。

下面是建议的最低 VM 配置。

|参数  |工作站操作系统  |服务器操作系统  |
|---------|---------|---------|
|vCPU   |    2 核     |  4 核、6 核或 8 核<br>请务必了解基础非统一内存访问 (NUMA) 配置并相应地配置 VM。     |
|RAM     |   4 GB      | 每个用户 512 MB 到 1 GB        |
|存储空间    | 8 GB        | 40 GB 到 60 GB        |

#### <a name="non-persistent-setup"></a>非持久性设置

在非持久性设置中，用户注销后不会保留用户的本地操作系统更改。 此类设置通常是共享的多用户会话。 VM 配置因用户数和可用的物理服务器资源而异。

对于非持久性设置，必须将 Teams 桌面应用按计算机安装到黄金映像。 这可确保在用户会话期间有效启动 Teams 应用。 若要了解详细信息，请参阅 [在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi) 部分。

在非持久设置中使用 Teams 还需要配置文件缓存管理器，以便高效进行 Teams 运行时数据同步。 高效的数据同步可确保在用户会话期间缓存用户的数据、配置文件或设置等用户特定信息)  (。 确保同步这两个文件夹中的数据：<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> 漫游文件夹 (或者，如果使用文件夹重定向，则需要缓存管理器) ，以确保 Teams 应用具有运行应用程序所需的运行时数据和文件。 这是减少网络延迟问题或网络故障所必需的，否则会导致应用程序错误和由于数据和文件不可用而缓慢的体验。

有多种可用的缓存管理器解决方案，例如 [FSLogix](/fslogix/overview)。 有关特定配置说明，请咨询缓存管理器提供程序。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>非持久性设置的 Teams 缓存内容排除列表

从 Teams 缓存文件夹 `%AppData%/Microsoft/Teams`中排除以下内容。 排除这些项有助于减小用户缓存大小，以进一步优化非持久性设置。

- .txt文件
- Media-stack 文件夹
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 企业应用版注意事项

在 VDI 上部署具有Microsoft 365 企业应用版的 Teams 时，请考虑以下事项。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>通过 Microsoft 365 企业应用版 新部署 Teams

在通过 Microsoft 365 企业应用版 部署 Teams 之前，必须先卸载任何预先存在的 Teams 应用（如果这些应用是使用每计算机安装进行部署的）。

通过 Microsoft 365 企业应用版 的 Teams 是按用户安装的。 若要了解详细信息，请参阅 [在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi) 部分。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>通过Microsoft 365 企业应用版更新进行 Teams 部署

还将将 Teams 添加到现有Microsoft 365 企业应用版安装中。 由于 Microsoft 365 企业应用版仅按用户安装 Teams，请参阅[在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)部分。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>使用 Teams 进行每台计算机安装和Microsoft 365 企业应用版

Microsoft 365 企业应用版不支持 Teams 的每台计算机安装。 若要使用每台计算机安装，必须从Microsoft 365 企业应用版中排除 Teams。 请参阅[将 Teams 桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) 和[如何通过Microsoft 365 企业应用版排除 Teams 部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)部分。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何通过Microsoft 365 企业应用版排除 Teams 部署

若要详细了解 Teams 和Microsoft 365 企业应用版，请参阅[如何从新安装的 Microsoft 365 企业应用版 中排除 Teams](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) 和使用[组策略来控制 Teams 的安装](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>将 Teams 桌面应用部署到 VM

⁠1. 使用以下链接之一下载与 VDI VM 操作系统匹配的 Teams MSI 包：
    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)
    > [!NOTE]
    > 对于政府云，请参阅 [使用 Windows Installer (MSI) 批量安装 Teams ](msi-deployment.md) ，获取 MSI 文件的下载链接。

2. 运行以下命令之一，将 MSI 安装到 VDI VM：

    - 按用户安装 (默认) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此过程是默认安装，它将 Teams 安装到 `%AppData%` 用户文件夹。 此时，黄金映像设置已完成。

        > [!IMPORTANT]
        > Teams 在非持久性安装程序上无法正常使用每用户安装。

    - 每台计算机安装

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此过程将所需的注册表项添加到计算机，使 Teams 安装程序知道它是 VDI 实例。  如果没有它，安装程序将出错，指出：“安装失败。  如果未检测到 VDI 环境，则无法为所有用户安装。”

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此过程将 Teams 安装到 `%ProgramFiles(x86)%` 64 位操作系统上的 文件夹和 `%ProgramFiles%` 32 位操作系统上的 文件夹。 此时，黄金映像设置已完成。

        > [!IMPORTANT]
        >  对于非持久性安装，需要按计算机安装 Teams。

        当下一个交互式登录会话启动时，Teams 将启动并要求提供凭据。

        > [!NOTE]
        > 这些示例还使用 `ALLUSERS=1` 参数。 设置此参数时，**Teams Machine-Wide安装程序** 将显示在 **控制面板** 的 **程序和功能** 中，并在 Windows **设置** 中为计算机的所有用户&**功能**。 然后，如果所有用户具有管理员凭据，则可以卸载 Teams。
        >
        > 了解 和 `ALLUSER=1`之间的差异`ALLUSERS=1`非常重要。 参数 `ALLUSERS=1` 可用于非 VDI 和 VDI 环境，而 `ALLUSER=1` 参数仅在 VDI 环境中用于指定每台计算机安装。

3. 从 VDI VM 卸载 MSI。 有两种方法可以卸载 Teams。

    - **PowerShell 脚本**：可以使用 [Teams 部署清理](scripts/powershell-script-deployment-cleanup.md) PowerShell 脚本卸载 Teams 并删除用户的 Teams 文件夹。 为计算机上安装了 Teams 的每个用户配置文件运行脚本。
    - **命令行**：运行以下命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      此过程会从 `%ProgramFiles(x86)%` 文件夹或 `%ProgramFiles%` 文件夹中卸载 Teams，具体取决于操作系统环境。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 上的 Teams 性能注意事项

有多种虚拟化安装配置，每个配置都具有不同的优化重点。 例如，配置可能侧重于用户密度。 规划时，请考虑以下事项，以帮助根据组织的工作负载需求优化设置。

- **最低要求**：某些工作负载可能需要使用高于最低要求的资源进行设置。 例如，使用需要更多计算资源的应用程序的开发人员的工作负载。
- **依赖项**：这包括对 Teams 桌面应用外部的基础结构、工作负载和其他环境注意事项的依赖关系。
- **VDI 上禁用的功能**：Teams 禁用 VDI 的 GPU 密集型功能，这有助于提高暂时性 CPU 利用率。 以下功能处于禁用状态：
    - Teams CSS 动画
    - Giphy 自动启动

## <a name="teams-on-vdi-with-calling-and-meetings"></a>具有通话和会议的 VDI 上的 Teams

除了聊天和协作外，支持虚拟化提供商平台的 VDI 上的 Teams 还提供通话和会议。 支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。 下图概述了体系结构。

![显示 VDI 上的 Teams 体系结构的关系图。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果当前在 VDI 中运行没有 AV 优化的 Teams，并且使用尚不支持优化 (的功能（例如，在应用共享) 时授予和控制），则必须设置虚拟化提供程序策略以关闭 Teams 重定向。 这意味着不会优化 Teams 媒体会话。 有关如何设置策略以关闭 Teams 重定向的步骤，请联系虚拟化提供商。

### <a name="network-requirements"></a>网络要求

建议评估环境，以确定可能影响整个云语音和视频部署的任何风险和要求。 使用[Skype for Business网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试网络是否已准备好使用 Teams。

若要详细了解如何为 Teams 准备网络，请参阅 [为 Teams 准备组织的网络](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>从 VDI 上的Skype for Business迁移到 VDI 上的 Teams

如果要从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams，除了两个应用程序之间的差异外，实现 VDI 时还存在一些差异。 Skype for Business VDI 中的 Teams VDI 中当前不支持的某些功能如下所示：

- 在 VDI 中禁用某些 AV 功能的按平台策略
- 在应用共享时授予并控制
- 没有音频的聊天中的屏幕共享
- 同时视频和屏幕共享发送和接收

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>适用于 VDI 的 Chrome 浏览器上的 Teams 与 Teams 桌面应用

Chrome 上的 Teams 浏览器不提供用于 VDI 的 Teams 桌面应用的替代 AV 优化。 聊天和协作体验按预期工作。 当需要媒体时，某些体验可能无法满足 Chrome 浏览器上的用户期望：

- 音频和视频流式处理体验可能不是最佳的。 用户可能会遇到延迟或质量降低的情况。
- 设备设置在浏览器设置中不可用。
- 设备管理通过浏览器进行处理，需要浏览器站点设置中的多个设置。
- 可能还需要在 Windows 设备管理中设置设备设置。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>VDI 上的 Teams 与聊天和协作

如果组织希望仅使用 Teams 中的聊天和协作功能，则可以设置用户级策略以关闭 Teams 中的通话和会议功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置策略以关闭通话和会议功能

可以使用 Teams 管理中心或 PowerShell 设置策略。 策略更改最多需要几个小时才能传播。 如果未立即看到给定帐户的更改，请在几个小时后重试。

[**呼叫策略**](teams-calling-policy.md)：Teams 包括内置的 **DisallowCalling** 呼叫策略，其中所有呼叫功能都处于关闭状态。 将 **DisallowCalling** 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

[**会议策略**](meeting-policies-overview.md)：Teams 包括内置的 **AllOff** 会议策略，其中所有会议功能都处于关闭状态。 将 **AllOff** 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用 Teams 管理中心分配策略

若要向用户分配 **DisallowCalling** 呼叫策略和 **AllOff** 会议策略，请执行以下操作：

1. 在 Teams 管理中心的左侧导航栏中，转到 **“用户**”。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **“调用策略**”下，单击“ **禁止调用**”。
    2. 在 **“会议策略**”下，单击“ **AllOff**”。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在 Teams 管理中心的左侧导航中，转到 **“用户”**，然后搜索用户或筛选视图以显示所需用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击表顶部 **&#x2713;** (复选标记) 。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在 Teams 管理中心的左侧导航栏中，转到要分配的策略。 例如：
    - 转到 **“语音** > **呼叫策略**”，然后单击“ **禁止调用**”。
    - 转到 **“会议会议** > **策略**”，然后单击“ **AllOff**”。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击“ **保存**”。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 `DisallowCalling` 调用策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理呼叫策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 `AllOff` 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>通过聊天和协作迁移 VDI 上的 Teams，以通过通话和会议优化 Teams

如果你在 VDI 上具有具有聊天和协作的现有 Teams 实现，其中你已设置用户级策略以关闭通话和会议功能，并且你要通过 AV 优化迁移到 Teams，则必须设置策略来为 VDI 用户上的 Teams 启用通话和会议功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>设置策略以启用通话和会议功能

可以使用 Teams 管理中心或 PowerShell 设置呼叫和会议策略并将其分配给用户。 可能需要一些时间 (几个小时) 策略更改才能传播。 如果未立即看到给定帐户的更改，请在几个小时后重试。

[**呼叫策略**](teams-calling-policy.md)：Teams 中的呼叫策略控制用户可用的通话功能。 Teams 包括内置的 **AllowCalling** 呼叫策略，其中所有通话功能都处于打开中。 若要启用所有呼叫功能，请分配 **AllowCalling** 策略。 或者，创建自定义呼叫策略以打开所需的呼叫功能并将其分配给用户。

[**会议策略**](meeting-policies-overview.md)：Teams 中的会议策略控制用户可以创建的会议类型以及组织中用户安排的会议参与者可用的功能。 Teams 包括内置的 **AllOn** 会议策略，其中所有会议功能都处于打开中。 若要启用所有会议功能，请分配 **AllOn** 策略。 或者，创建自定义会议策略以打开所需的会议功能并为其分配用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用 Teams 管理中心分配策略

若要向用户分配 **AllowCalling** 呼叫策略和 **AllOn** 会议策略，请执行以下操作：

1. 在 Teams 管理中心的左侧导航栏中，转到 **“用户**”。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **“呼叫策略**”下，单击“ **允许”“调用**”。
    2. 在 **“会议策略**”下，单击“ **AllOn**”。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在 Teams 管理中心的左侧导航中，转到 **“用户”**，然后搜索用户或筛选视图以显示所需用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击表顶部 **&#x2713;** (复选标记) 。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在 Teams 管理中心的左侧导航栏中，转到要分配的策略。 例如：
    - 转到 **“语音** > **呼叫策略**”，然后单击“ **允许”“呼叫**”。
    - 转到 **“会议会议** > **策略**”，然后单击“ **AllOn**”。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击“ **保存**”。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 `AllowCalling` 调用策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理呼叫策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 `AllOn` 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>在 Teams 中控制回退模式

当用户从不受支持的终结点进行连接时，用户处于回退模式，其中 AV 未优化。 可以通过设置以下注册表 `DWORD` 值之一来禁用或启用回退模式：

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

若要禁用回退模式，请将值设置为 **1**。 若要仅启用音频，请将值设置为 **2**。 如果该值不存在或设置为 **0** (零) ，则启用回退模式。

此功能在 Teams 版本 1.3.00.13565 及更高版本中可用。

## <a name="disable-audio-and-video-settings-for-vdi"></a>禁用 VDI 的音频和视频设置

Teams 模块中提供了 Teams VDI 策略。 这些策略处于活动状态，并在非优化的 VDI 环境中强制实施。

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> 这仅适用于非优化环境。

### <a name="connect-to-microsoft-teams-powershell"></a>连接到 Microsoft Teams PowerShell

按照[安装 Microsoft Teams PowerShell 模块](/Teams/teams-powershell-install.md)中的说明连接到 Microsoft Teams PowerShell 模块。 然后运行以下命令，确认所有 VDI cmdlet 都可用：

```PowerShell
Get-Command -Noun *VDI*
```

### <a name="set-policies-to-limit-calling-features"></a>设置策略以限制呼叫功能

当 VDI 策略设置为`$true`在 VDI `DisableCallsAndMeetings` 上登录 Teams 的用户时，他们无法：

- 拨打电话。
- 加入会议。
- 聊天中的屏幕共享。

应禁用所有类型的调用。

> [!NOTE]
> 这仅适用于非优化环境。

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

当 VDI 策略设置为`$true`登录到 VDI `DisableAudioVideoInCallsAndMeetings` 上的 Teams 的用户时，他们：

- 可以从聊天中共享屏幕。
- 可以加入会议并共享屏幕，并将音频移动到手机。
- 无法从 VDI 进行人对人音频和视频通话。

> [!NOTE]
> 这仅适用于非优化环境。

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>已知问题和限制

### <a name="client-deployment-installation-and-setup"></a>客户端部署、安装和设置

- 对于每台计算机安装，VDI 上的 Teams 不会以非 VDI Teams 客户端的方式自动更新。 必须按照 [在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi) 部分中所述，通过安装新的 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。
- 在 Citrix 环境中，如果用户在运行 Teams 时断开与虚拟机的连接，Teams 更新可能会导致用户在重新连接时处于 AV 的非优化状态。 建议用户在与 Citrix 虚拟机断开连接之前退出 Teams，以避免出现这种情况。
- 应按用户或每台计算机部署 Teams。 不支持针对每个用户和每台计算机的并发部署 Teams。 若要从每台计算机或每个用户迁移到其中一种模式，请按照卸载过程操作并重新部署到任一模式。
- Azure 虚拟桌面目前不支持基于 Linux 的客户端。
- 快速租户切换可能会导致 VDI 上的呼叫相关问题，例如屏幕共享不可用。 重启客户端可缓解这些问题。

### <a name="notifications"></a>通知

- Windows Server 2016主机上不支持 Windows 任务栏上的消息计数通知和状态。

### <a name="calling-and-meetings"></a>通话和会议

不支持以下通话和会议功能：

- 适用于 Citrix 和 VMware 的 Teams 应用和设备之间的 HID 按钮和 LED 控件
- Citrix 和 VMware 的背景模糊和效果
- 广播和直播活动制作人和演示者角色
- Location-Based路由 (LBR) 
- PSTN 呼叫回拨音
- 共享系统音频/计算机声音
- 直接路由的媒体旁路
- 缩放控件

> [!NOTE]
> 我们正在努力添加通话和会议功能，这些功能目前仅在非 VDI 环境中可用。 这些可能包括对质量的更多管理员控制、其他屏幕共享方案和最近添加到 Teams 的高级功能。 请联系 Teams 代表，了解有关即将推出的功能的详细信息。

以下是通话和会议的已知问题和限制：

- 与Skype for Business的互操作性仅限于音频呼叫;没有视频形式。
- 传入和传出视频流分辨率限制为 720p 分辨率。
- 如果设备断开连接，然后重新连接，Teams 不会切换到使用用户选择的最后一个音频设备。
- 实时事件未优化。
- 传出屏幕共享：
  - VMware 和 AVD/W365 不支持应用程序共享。
- 授予控制权并控制：
  - 在应用程序共享会话期间不受支持。

对于与 VDI 无关的 Teams 已知问题，请参阅 [组织中的支持团队](/MicrosoftTeams/troubleshoot/teams-welcome)。

## <a name="troubleshooting"></a>疑难解答

### <a name="troubleshoot-citrix-components"></a>排查 Citrix 组件问题

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams 崩溃或 Teams 登录屏幕为空白

这是 Citrix VDA 版本 1906 和 1909 的已知问题。 若要解决此问题，请添加以下注册表 `DWORD` 值，并将其设置为 `204` (十六进制) 。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

然后，重启 VDA。 若要了解详细信息，请参阅 Citrix 支持文章[故障排除 hdX 优化Microsoft Teams](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相关主题

- [使用 Windows Installer (MSI) 批量安装 Teams ](msi-deployment.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Azure 虚拟桌面上使用 Microsoft Teams](/azure/virtual-desktop/teams-on-wvd)
