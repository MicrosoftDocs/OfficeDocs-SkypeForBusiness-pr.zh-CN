---
title: 适用于虚拟化桌面基础结构的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在虚拟化桌面基础结构 (VDI) 环境中运行Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b85befa685458f5460ab21bb962af3f0df4f004
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681583"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用Microsoft Teams的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是虚拟化技术，可在数据中心的集中式服务器上托管桌面操作系统和应用程序。 这为具有完全安全且合规的集中源的用户提供了完整且个性化的桌面体验。

虚拟化环境中的Teams支持聊天和协作。 此外，还支持使用 Azure 虚拟桌面、Citrix 和 VMware 平台，同时支持通话和会议功能。

Teams还支持虚拟环境中的多个配置。 这些模式包括 VDI、专用模式、共享模式、持久模式和非持久模式。 功能正在持续开发中，并且会定期添加，并且功能会随时间推移而扩展。

在虚拟化环境中使用Teams可能与在非虚拟化环境中使用Teams略有不同。 例如，某些高级功能可能在虚拟化环境中不可用，视频解析可能有所不同。

若要确保最佳用户体验，请遵循本文中的指导。

> [!Note]
> 有关在不同平台上Teams VDI 的详细信息，请参阅[按平台Teams功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 组件上的Teams

在虚拟化环境中使用Teams需要以下组件。

- **虚拟化代理**：虚拟化提供程序的资源和连接管理器，例如 Azure
- **虚拟桌面**：运行Teams的虚拟机 (VM) 堆栈
- **精简客户端**：用户物理接口的设备
- **Teams桌面应用**：Teams桌面客户端应用

## <a name="teams-on-vdi-requirements"></a>有关 VDI 要求的Teams

### <a name="virtualization-provider-requirements"></a>虚拟化提供程序要求

Teams桌面应用已通过领先的虚拟化解决方案提供程序进行验证。 对于多个市场提供商，建议咨询虚拟化解决方案提供商，以确保满足最低要求。
  
目前，使用音频/视频 (AV) 优化的 VDI 上的Teams已通过 Azure 虚拟桌面、Citrix 和 VMware 进行认证。 查看本部分中的信息，确保满足所有有关适当功能的要求。

### <a name="platforms-certified-for-teams"></a>Teams认证的平台

以下平台具有用于Teams的虚拟桌面基础结构解决方案。

|平台|解决方案|
|----|---|
|![表示 Microsoft 的徽标。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虚拟桌面</a>，<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![表示 Citrix 的徽标。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a> |
|![表示 VMware 的徽标。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虚拟桌面

Azure 虚拟桌面为 VDI 上的Teams提供 AV 优化。 若要了解有关要求和安装的详细信息，请参阅 [Azure 虚拟桌面上的“使用Teams](/azure/virtual-desktop/teams-on-wvd)”。

### <a name="windows-365"></a>Windows 365

Windows 365使用 Azure 虚拟桌面提供的 AV 优化来确保云电脑的最佳Teams体验。 若要了解有关要求和安装的详细信息，请参阅 [Cloud PC 上的“使用Teams](/windows-365/enterprise/teams-on-cloud-pc)”。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虚拟应用和桌面要求

Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的Teams提供 AV 优化。 借助 Citrix 虚拟应用和桌面，VDI 上的Teams除了聊天和协作外，还支持通话和会议功能。

可以在 [Citrix 下载站点](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下载最新版本的 Citrix 虚拟应用和桌面。  (需要先登录。) 默认情况下，必要的组件将捆绑到 [CWA) 和虚拟交付代理 (Citrix 工作区应用 ](https://www.citrix.com/downloads/workspace-app/) (VDA) 。 无需在 CWA 或 VDA 上安装任何其他组件或插件。

有关最新的服务器和客户端要求，请参阅 Citrix 网站上[的Microsoft Teams优化](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)文章。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon 工作区和桌面要求

VMware Horizon 是一种新式平台，用于跨混合云安全交付虚拟桌面和应用。 为了提供出色的最终用户体验，VMware Horizon 为Teams提供媒体优化。 此优化可提高虚拟桌面和应用的总体工作效率，并增强使用Teams进行通话和会议时的用户体验。

可以从 [VMware 下载](https://customerconnect.vmware.com/downloads/#all_products) 页面下载最新版本的 VMware Horizon。 默认情况下，所需的媒体优化组件是 Horizon 代理和 Horizon 客户端的一部分，无需安装任何其他插件即可使用优化功能进行Teams。

若要获取有关如何为Teams配置媒体优化的最新要求和说明，请参阅 VMware 网站上[的“为Microsoft Teams配置媒体优化](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)”一文。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安装或更新Teams桌面应用

可以使用每台计算机安装或使用 MSI 包按用户安装来部署用于 VDI 的Teams桌面应用。 决定使用哪种方法取决于是使用持久设置还是非永久性设置，以及组织相关联的功能需求。

对于专用的永久性安装，每台计算机和每用户安装都将有效。 但是，对于非持久性设置，Teams需要每台计算机安装才能高效工作。 请参阅 [“非永久性设置”](#non-persistent-setup) 部分。

使用每台计算机安装时，会禁用自动更新。 这意味着，若要更新Teams应用，必须卸载当前版本才能更新到较新的版本。 通过按用户安装，将启用自动更新。

> [!IMPORTANT]
> 使 VDI 环境中的Teams桌面应用保持最新状态。 不支持发布日期比[当前版本的发布日期](/officeupdates/teams-app-versioning)早 90 天以上的Teams桌面应用版本。 不受支持的Teams桌面应用版本会向用户显示阻止页面，并要求用户更新其应用。

对于大多数 VDI 部署，建议使用每台计算机安装部署Teams。 若要更新到最新Teams版本，请从卸载过程开始，后跟最新的Teams版本部署。

若要使 VDI 环境中的Teams AV 优化正常工作，精简客户端设备必须有权访问 Internet。 如果精简客户端设备无法访问 Internet，优化启动将不会成功。 这意味着用户处于非优化媒体状态。

#### <a name="dedicated-persistent-setup"></a>专用永久性设置

在专用的永久性设置中，用户注销后会保留用户的本地操作系统更改。 对于持久性设置，Teams支持每用户和每台计算机安装。

下面是建议的最小 VM 配置。

|参数  |工作站操作系统  |服务器操作系统  |
|---------|---------|---------|
|vCPU   |    2 个核心     |  4、6 或 8 个内核<br>请务必了解 NUMA) 配置的基础非统一内存访问 (并相应地配置 VM。     |
|RAM     |   4 GB      | 每个用户 512 MB 到 1 GB        |
|存储    | 8 GB        | 40 GB 到 60 GB        |

#### <a name="non-persistent-setup"></a>非永久性设置

在非永久性设置中，用户注销后不会保留用户的本地操作系统更改。 此类设置通常是共享的多用户会话。 VM 配置因用户数和可用物理服务器资源而异。

对于非永久性设置，必须将每台计算机的Teams桌面应用安装到黄金映像。 这可确保在用户会话期间高效启动Teams应用。 若要了解详细信息，请参阅“[在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)”部分。

在非持久性设置中使用Teams还需要配置文件缓存管理器来高效Teams运行时数据同步。 高效的数据同步可确保在用户会话期间缓存适当的用户特定信息 (，例如用户的数据、配置文件或设置) 。 确保同步这两个文件夹中的数据：<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> 漫游文件夹 (或者，如果使用文件夹重定向，则需要一个缓存管理器) ，以确保Teams应用具有运行应用程序所需的运行时数据和文件。 这是缓解网络延迟问题或网络故障所必需的，否则会导致应用程序错误和由于数据和文件不可用而导致体验缓慢。

有各种可用的缓存管理器解决方案，例如 [FSLogix](/fslogix/overview)。 有关特定配置说明，请咨询缓存管理器提供程序。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams非永久性设置的缓存内容排除列表

从Teams缓存文件夹`%AppData%/Microsoft/Teams`中排除以下内容。 排除这些项有助于减小用户缓存大小，以进一步优化非永久性设置。

- .txt文件
- 媒体堆栈文件夹
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 企业应用版注意事项

在 VDI 上使用Microsoft 365 企业应用版部署Teams时，请考虑以下事项。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>通过Microsoft 365 企业应用版新部署Teams

在通过Microsoft 365 企业应用版部署Teams之前，必须先卸载任何预先存在的Teams应用（如果这些应用是使用每台计算机安装部署的）。

Teams Microsoft 365 企业应用版按用户安装。 若要了解详细信息，请参阅“[在 VDI 上安装或更新 Teams 桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)”部分。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>通过Microsoft 365 企业应用版更新Teams部署

Teams也正在添加到现有安装的Microsoft 365 企业应用版。 由于Microsoft 365 企业应用版仅按用户安装Teams，请参阅 [VDI 部分上的“安装或更新Teams桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)”。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>将Teams用于每台计算机的安装和Microsoft 365 企业应用版

Microsoft 365 企业应用版不支持每台计算机安装Teams。 若要使用每台计算机安装，必须从Microsoft 365 企业应用版中排除Teams。 请参阅[将Teams桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) 以及[如何通过Microsoft 365 企业应用版部分排除Teams部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何通过Microsoft 365 企业应用版排除Teams部署

若要详细了解Teams和Microsoft 365 企业应用版，请参阅[如何从新安装的Microsoft 365 企业应用版中排除Teams](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)，并[使用组策略控制Teams的安装](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>将Teams桌面应用部署到 VM

1. 使用以下链接之一下载与 VDI VM 操作系统匹配的Teams MSI 包：

    - [32 位版本](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [64 位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > 有关政府云，请参阅[使用 Windows Installer (MSI) 进行批量安装Teams](msi-deployment.md)，以获取 MSI 文件的下载链接。

    所需的Teams桌面应用的最小版本是版本 1.3.00.4461。 早期版本不支持 PSTN 保留。

2. 运行以下命令之一，将 MSI 安装到 VDI VM：

    - 按用户安装 (默认) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此过程是默认安装，用于将Teams安装到`%AppData%`用户文件夹。 此时，黄金图像设置已完成。

        > [!IMPORTANT]
        > Teams无法在非永久性设置上正常处理每个用户的安装。

    - 每台计算机安装

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此过程将所需的注册表项添加到计算机，让Teams安装程序知道它是 VDI 实例。  如果没有它，安装程序将出错，指出：“安装已失败。  如果未检测到 VDI 环境，则无法为所有用户安装。”

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此过程将Teams安装到 `%ProgramFiles(x86)%` 64 位操作系统上的文件夹和 `%ProgramFiles%` 32 位操作系统上的文件夹。 此时，黄金图像设置已完成。

        > [!IMPORTANT]
        >  对于非持久性设置，需要每台计算机安装Teams。

        下一个交互式登录会话启动时，Teams启动并请求凭据。

        > [!NOTE]
        > 这些示例还使用 `ALLUSERS=1` 参数。 设置此参数时，**Teams Machine-Wide安装程序** 将显示在 **控制面板** 和应用中的 **程序和功能** 中 **，&** 计算机的所有 **用户Windows 设置中的** 功能。 然后，如果所有用户都有管理员凭据，则可以卸载Teams。
        >
        > 了解两`ALLUSERS=1``ALLUSER=1`者的区别很重要。 该 `ALLUSERS=1` 参数可在非 VDI 和 VDI 环境中使用，而 `ALLUSER=1` 该参数仅在 VDI 环境中用于指定每台计算机的安装。

3. 从 VDI VM 卸载 MSI。 有两种方法可以卸载Teams。

    - **PowerShell 脚本**：可以使用 [Teams部署清理](scripts/powershell-script-deployment-cleanup.md) PowerShell 脚本卸载Teams并删除用户的Teams文件夹。 运行计算机上安装Teams的每个用户配置文件的脚本。
    - **命令行**：运行以下命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      此过程从文件夹或`%ProgramFiles%`文件夹中卸载Teams`%ProgramFiles(x86)%`，具体取决于操作系统环境。

## <a name="teams-on-vdi-performance-considerations"></a>Teams VDI 性能注意事项

有各种虚拟化设置配置，每个配置都具有不同的优化重点。 例如，配置可能侧重于用户密度。 规划时，请考虑以下事项，以帮助根据组织的工作负荷需求优化设置。

- **最低要求**：某些工作负荷可能需要使用高于最低要求的资源进行设置。 例如，使用需要更多计算资源的应用程序的开发人员的工作负荷。
- **依赖关系**：这些依赖项包括基础结构、工作负荷以及Teams桌面应用之外的其他环境注意事项。
- **VDI 上的禁用功能**：Teams禁用 VDI 的 GPU 密集型功能，这有助于提高暂时性 CPU 利用率。 禁用了以下功能：
    - Teams CSS 动画
    - Giphy 自动启动

## <a name="teams-on-vdi-with-calling-and-meetings"></a>通过通话和会议在 VDI 上Teams

除了聊天和协作之外，还可通过受支持的虚拟化提供程序平台在 VDI 上Teams通话和会议。 支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。 下图概述了体系结构。

![显示 VDI 体系结构Teams的示意图。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果当前在 VDI 中运行Teams而未进行 AV 优化，并且使用尚不支持优化 (的功能（如在应用共享) 时授予和控制，则必须设置虚拟化提供程序策略以关闭Teams重定向。 这意味着不会优化Teams媒体会话。 有关如何设置策略以关闭Teams重定向的步骤，请联系虚拟化提供程序。

### <a name="network-requirements"></a>网络要求

建议评估环境，以确定可能影响整个云语音和视频部署的任何风险和要求。 使用[Skype for Business网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试网络是否已准备好进行Teams。

若要详细了解如何为Teams准备网络，请参阅[为Teams准备组织的网络](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>从 VDI 上的Skype for Business迁移到 VDI 上的Teams

如果要从 VDI 上的Skype for Business迁移到 VDI 上的Teams，除了两个应用程序之间的差异外，还实现 VDI 时会存在一些差异。 Skype for Business VDI 中的Teams VDI 中当前不支持的某些功能如下所示：

- 在 VDI 中禁用某些 AV 功能的按平台策略
- 在应用共享时给予和控制
- 没有音频的聊天屏幕共享
- 同时发送和接收视频和屏幕共享

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 浏览器上的Teams与适用于 VDI 的Teams桌面应用

Chrome 浏览器上的Teams无法使用 AV 优化来替代用于 VDI 的Teams桌面应用。 聊天和协作体验按预期工作。 当需要媒体时，某些体验可能无法满足用户在 Chrome 浏览器上的期望：

- 音频和视频流式处理体验可能不是最佳体验。 用户可能会遇到延迟或质量降低。
- 设备设置在浏览器设置中不可用。
- 设备管理通过浏览器进行处理，并且需要浏览器网站设置中的多个设置。
- 可能需要在设备管理Windows中设置设备设置。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>通过聊天和协作在 VDI 上Teams

如果你的组织只想在Teams中使用聊天和协作功能，则可以设置用户级策略以关闭Teams中的呼叫和会议功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置策略以关闭呼叫和会议功能

可以使用Teams管理中心或 PowerShell 设置策略。 要传播策略更改最多需要几个小时。 如果未立即看到给定帐户的更改，请在几个小时内重试。

[**呼叫策略**](teams-calling-policy.md)：Teams包括内置 **的 DisallowCalling** 呼叫策略，其中所有呼叫功能都处于关闭状态。 将 **DisallowCalling** 策略分配给组织中使用虚拟化环境中Teams的所有用户。

[**会议策略**](meeting-policies-overview.md)：Teams包括内置 **的 AllOff** 会议策略，其中所有会议功能都处于关闭状态。 将 **AllOff** 策略分配给组织中使用虚拟化环境中Teams的所有用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用Teams管理中心分配策略

若要将 **DisallowCalling** 调用策略和 **AllOff** 会议策略分配给用户，请执行以下操作：

1. 在Teams管理中心的左侧导航中，转到 **“用户**”。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **“呼叫策略**”下，单击 **“DisallowCalling**”。
    2. 在 **“会议策略**”下，单击 **“AllOff**”。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在Teams管理中心的左侧导航中，转到 **“用户**”，然后搜索用户或筛选视图以显示所需的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击 **表顶部的&#x2713;** (复选标记) 。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在Teams管理中心的左侧导航中，转到要分配的策略。 例如：
    - 转到 **语音** > **呼叫策略**，然后单击 **“DisallowCalling**”。
    - 转到 **会议会议** > **策略**，然后单击 **“AllOff**”。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击“ **保存**”。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将调用策略分配 `DisallowCalling` 给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理调用策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将会议策略分配 `AllOff` 给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>通过聊天和协作迁移 VDI 上的Teams，以优化通话和会议Teams

如果你已通过聊天和协作在 VDI 上实施了Teams，其中你已设置用户级策略以关闭呼叫和会议功能，并且要通过 AV 优化迁移到Teams，则必须设置策略，为 VDI 用户上的这些Teams启用呼叫和会议功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>设置策略以启用呼叫和会议功能

可以使用Teams管理中心或 PowerShell 设置呼叫和会议策略并将其分配给用户。 要传播策略更改，可能需要一些时间 (几个小时) 。 如果未立即看到给定帐户的更改，请在几个小时后重试。

[**呼叫策略**](teams-calling-policy.md)：呼叫策略Teams控制哪些呼叫功能可供用户使用。 Teams包括内置 **AllowCalling** 调用策略，其中所有调用功能都处于打开状态。 若要打开所有调用功能，请分配 **AllowCalling** 策略。 或者，创建自定义调用策略以打开所需的调用功能，并将其分配给用户。

[**会议策略**](meeting-policies-overview.md)：会议策略Teams控制用户可以创建的会议类型以及可供组织中用户安排的会议参与者使用的功能。 Teams包括内置的 **AllOn** 会议策略，其中所有会议功能都处于打开状态。 若要打开所有会议功能，请分配 **AllOn** 策略。 或者，创建自定义会议策略以打开所需的会议功能并将其分配给用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用Teams管理中心分配策略

若要将 **AllowCalling** 调用策略和 **AllOn** 会议策略分配给用户，请执行以下操作：

1. 在Teams管理中心的左侧导航中，转到 **“用户**”。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **“呼叫策略**”下，单击 **“AllowCalling**”。
    2. 在 **“会议策略**”下，单击 **“AllOn**”。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在Teams管理中心的左侧导航中，转到 **“用户**”，然后搜索用户或筛选视图以显示所需的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击 **表顶部的&#x2713;** (复选标记) 。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在Teams管理中心的左侧导航中，转到要分配的策略。 例如：
    - 转到 **语音** > **呼叫策略**，然后单击 **AllowCalling**。
    - 转到 **会议会议** > **策略**，然后单击 **“AllOn**”。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击“ **保存**”。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将调用策略分配 `AllowCalling` 给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理调用策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将会议策略分配 `AllOn` 给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>控制Teams中的回退模式

当用户从不受支持的终结点进行连接时，用户处于回退模式，其中未优化 AV。 可以通过设置以下注册表 `DWORD` 值之一来禁用或启用回退模式：

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

若要禁用回退模式，请将值设置为 **1**。 若要仅启用音频，请将值设置为 **2**。 如果该值不存在或设置为 **0** (零) ，则启用回退模式。

此功能在 Teams 版本 1.3.00.13565 及更高版本中提供。

## <a name="disable-audio-and-video-settings-for-vdi"></a>禁用 VDI 的音频和视频设置

Teams VDI 策略在Teams模块中可用。 这些策略在非优化的 VDI 环境中处于活动状态并强制实施。

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> 这仅适用于非优化环境。

### <a name="update-a-module-name"></a>更新模块名称

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>设置策略以限制调用功能

当 VDI `DisableCallsAndMeetings` 策略设置为`$true`在 VDI 上登录Teams的用户无法：

- 进行呼叫。
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

当 VDI `DisableAudioVideoInCallsAndMeetings` 策略设置为登录以`$true`Teams VDI 的用户时，他们：

- 可以通过聊天屏幕共享。
- 可以加入会议并共享屏幕，并将其音频移动到手机。
- 无法保存来自 VDI 的人员对人音频和视频呼叫。

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

- 通过每台计算机安装，VDI 上的Teams不会像非 VDI Teams客户端那样自动更新。 必须按在 [VDI 部分安装或更新Teams桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)中所述安装新的 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。
- 在 Citrix 环境中，如果用户在运行Teams时与虚拟机断开连接，则Teams更新可能会导致用户在重新连接时处于 AV 的非优化状态。 我们建议用户在断开与 Citrix 虚拟机的连接之前退出Teams，以避免这种情况。
- 应为每个用户或每台计算机部署Teams。 不支持为每个用户和每台计算机部署并发Teams。 若要从每台计算机或每个用户迁移到其中一种模式，请遵循卸载过程并重新部署到任一模式。
- Azure 虚拟桌面目前不支持macOS和基于 Linux 的客户端。
- 快速的租户切换可能会导致 VDI 上的呼叫相关问题，例如屏幕共享不可用。 重启客户端将缓解这些问题。

### <a name="notifications"></a>通知

- Windows Server 2016主机上不支持Windows任务栏上的消息计数通知和状态。

### <a name="calling-and-meetings"></a>通话和会议

不支持以下通话和会议功能：

- 任何多窗口功能，如新会议体验或新会议体验附带的任何功能
- Citrix 和 VMware 的Teams应用和设备之间的 HID 按钮和 LED 控件
- 背景模糊和效果
- 直播和直播活动制作人和演示者角色
- Location-Based路由 (LBR) 
- PSTN 调用回调音
- 共享系统音频/计算机声音
- 直接路由的媒体旁路
- 缩放控件

> [!NOTE]
> 我们正在努力添加当前仅在非 VDI 环境中提供的通话和会议功能。 这可能包括对质量的更多管理员控制、其他屏幕共享方案以及最近添加到Teams的高级功能。 请联系Teams代表，详细了解即将推出的功能。

以下是通话和会议的已知问题和限制：

- 与Skype for Business的互操作性仅限于音频呼叫;没有视频模式。
- 传入和传出视频流解析限制为 720p 分辨率。
- 仅支持来自传入相机或屏幕共享流的一个视频流。 当有传入的屏幕共享时，将显示该屏幕共享，而不是占主导地位的扬声器的视频。
- Teams不会切换到使用用户选择的最后一个音频设备（如果设备断开连接，然后重新连接）。
- 未优化实时事件。
- 传出屏幕共享：
  - 不支持应用程序共享。
- 提供控制并控制：
  - 在屏幕共享或应用程序共享会话期间不受支持。
  - 在PowerPoint共享会话期间受支持。

有关Teams与 VDI 无关的已知问题，请参阅[组织中的支持Teams](/MicrosoftTeams/troubleshoot/teams-welcome)。

## <a name="troubleshooting"></a>疑难解答

### <a name="troubleshoot-citrix-components"></a>排查 Citrix 组件问题

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams崩溃或Teams登录屏幕为空白

这是 Citrix VDA 版本 1906 和 1909 的已知问题。 若要解决此问题，请添加以下注册表 `DWORD` 值，并将其 `204` 设置为 (十六进制) 。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

然后，重启 VDA。 若要了解详细信息，请参阅此 Citrix 支持文章，[为Microsoft Teams的 HDX 优化进行故障排除](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相关主题

- [使用 Windows Installer (MSI) 批量安装Teams](msi-deployment.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Azure 虚拟桌面上使用Microsoft Teams](/azure/virtual-desktop/teams-on-wvd)
