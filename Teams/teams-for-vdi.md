---
title: 适用于虚拟化桌面基础结构的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在 VDI Microsoft Teams虚拟桌面基础结构 (运行) 应用程序。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ff97fae1fb2483dcddf301715018b6a94f908a7
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711436"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用Microsoft Teams的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是虚拟化技术，在数据中心的集中服务器上托管桌面操作系统和应用程序。 这使具有完全安全且合规的集中源的用户能够获得完整、个性化的桌面体验。

Teams环境中进行聊天和协作。 此外，通过 Azure 虚拟桌面、Citrix 和 VMware 平台，也支持呼叫和会议功能。

Teams还支持虚拟环境中的多个配置。 这些模式包括 VDI、专用、共享、持久性和非持久性模式。 功能在持续开发中，并定期添加，并且功能会随着时间的推移而扩展。

在Teams环境中使用资源可能稍有不同，Teams非虚拟化环境中使用资源。 例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能不同。

若要确保获得最佳用户体验，请遵循本文中的指导。

> [!Note]
> 有关在不同平台上Teams VDI 的详细信息，请参阅Teams[平台的功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>Teams VDI 组件

在Teams环境中使用云解决方案需要以下组件。

- **虚拟化代理**：虚拟化提供程序（例如 Azure）的资源和连接管理器
- **虚拟桌面**：虚拟机 (VM) 运行Teams
- **精简客户端**：用户实际与设备交互的设备
- **Teams桌面应用**：Teams桌面客户端应用

## <a name="teams-on-vdi-requirements"></a>Teams VDI 要求

### <a name="virtualization-provider-requirements"></a>虚拟化提供商要求

桌面Teams已使用领先的虚拟化解决方案提供商进行验证。 对于多个市场提供商，建议咨询虚拟化解决方案提供商，以确保满足最低要求。
  
目前，Teams Azure 虚拟桌面、Citrix 和 VMware (VDI) AV) VDI 上实现优化。 查看本部分的信息，确保满足正确功能的所有要求。

### <a name="platforms-certified-for-teams"></a>经认证的平台Teams

以下平台提供适用于 Teams 的虚拟桌面基础结构解决方案。

|平台|解决方案|
|----|---|
|![表示 Microsoft 的徽标。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虚拟桌面</a>，<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![表示 Citrix 的徽标。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a> |
|![表示 VMware 的徽标。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虚拟桌面

Azure 虚拟桌面为 VDI 上的Teams AV 优化。 若要详细了解要求和安装，请参阅[在 Azure Teams桌面上使用应用程序](/azure/virtual-desktop/teams-on-wvd)。

### <a name="windows-365"></a>Windows 365

Windows 365 使用 Azure 虚拟桌面提供的 AV 优化来确保从云Teams最佳体验。 若要详细了解要求和安装，请参阅在[Teams使用云设备](/windows-365/enterprise/teams-on-cloud-pc)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虚拟应用和桌面要求

Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的 Teams提供 AV 优化。 借助 Citrix 虚拟应用和桌面，Teams VDI 上的应用程序除了支持聊天和协作外，还支持呼叫和会议功能。

可以在 Citrix 下载站点下载最新版本的 [Citrix 虚拟应用和桌面](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。  (需要先登录。) 默认情况下，所需的组件将捆绑到 [Citrix Workspace 应用 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虚拟交付代理 (VDA) 中。 无需在 CWA 或 VDA 上安装任何其他组件或插件。

有关最新的服务器和客户端要求，请参阅 Citrix [Microsoft Teams优化文章](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace 和桌面要求

VMware Horizon 是一个新式平台，用于跨混合云安全交付虚拟桌面和应用。 为了提供出色的最终用户体验，VMware Horizon 为用户提供媒体Teams。 此优化可跨虚拟桌面和应用提高整体工作效率，并增强使用虚拟桌面和 Teams 进行呼叫和会议时Teams。

可以从 VMware 下载页下载 [最新版本的 VMware](https://customerconnect.vmware.com/downloads/#all_products) Horizon。 默认情况下，所需的媒体优化组件是 Horizon Agent 和 Horizon 客户端的一部分，无需安装任何其他插件来使用优化功能Teams。

若要获取有关如何为用户配置媒体优化的最新要求Teams，请参阅 VMware 网站上为 Microsoft Teams 配置媒体优化[](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)一文。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI Teams或更新桌面应用

可以使用每Teams安装或每用户安装，使用 MSI 包部署适用于 VDI 的桌面应用。 决定使用哪种方法取决于是使用持久性设置还是非持久性设置，以及组织的关联功能需求。

对于专用的永久性安装，每台计算机和每个用户的安装都将正常工作。 但是，对于非持久性设置，Teams要求每台计算机安装一次，以便高效工作。 请参阅 [非永久性设置](#non-persistent-setup) 部分。

使用每台计算机安装时，将禁用自动更新。 这意味着要更新 Teams 应用，必须卸载当前版本以更新到较新版本。 通过按用户安装，将启用自动更新。

对于大多数 VDI 部署，我们建议使用Teams安装来部署 VDI。 若要更新到最新版本Teams，请从卸载过程开始，然后是最新的 Teams 版本部署。

若要Teams VDI 环境中进行 AV 优化，精简客户端设备必须能够访问 Internet。 如果 Internet 访问在精简客户端设备上不可用，优化启动不会成功。 这意味着用户位于未优化的媒体状态。

#### <a name="dedicated-persistent-setup"></a>专用持久设置

在专用的永久性设置中，用户注销后，会保留用户的本地操作系统更改。 对于永久性安装，Teams支持每用户和每台计算机安装。

下面是建议的最低 VM 配置。

|参数  |工作站操作系统  |服务器操作系统  |
|---------|---------|---------|
|vCPU   |    2 个核心     |  4、6 或 8 个核心<br>必须了解 NUMA (配置) 基础的非统一内存访问，并相应地配置 VM。     |
|RAM     |   4 GB      | 每个用户 512 MB 到 1 GB        |
|存储空间    | 8 GB        | 40 GB 到 60 GB        |

#### <a name="non-persistent-setup"></a>非永久性设置

在非永久性设置中，用户注销后不会保留用户的本地操作系统更改。 此类设置通常共享多用户会话。 VM 配置因用户数和可用物理服务器资源而异。

对于非永久性设置，Teams桌面应用必须安装在每台计算机的黄金映像中。 这可确保在用户会话期间Teams应用有效启动。 有关详细信息，请参阅在 [VDI Teams或更新桌面](#install-or-update-the-teams-desktop-app-on-vdi)应用部分。

在Teams设置中使用配置文件缓存管理器还需要一个配置文件缓存管理器，Teams运行时数据同步。 高效的数据同步可确保在用户的会话 (缓存用户的数据、配置文件) 设置等用户特定信息。 确保同步这两个文件夹中的数据：<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> 漫游文件夹 (，或者，如果使用文件夹重定向，则要求缓存管理器) 以确保 Teams 应用具有运行应用程序所需的运行时数据和文件。 这是缓解网络延迟问题或网络故障所必需的，否则会导致应用程序错误，并且由于数据和文件不可用导致体验变慢。

有各种可用的缓存管理器解决方案，例如 [FSLogix](/fslogix/overview)。 有关特定配置说明，请参阅缓存管理器提供程序。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams持久性设置的缓存内容排除列表

从缓存文件夹中Teams以下内容`%AppData%/Microsoft/Teams`。 排除这些项有助于减小用户缓存大小，以进一步优化非持久性设置。

- .txt文件
- Media-stack 文件夹
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 企业应用版注意事项

在 VDI 上通过 Teams 部署Microsoft 365 企业应用版时，请考虑以下事项。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>通过 Teams 部署Microsoft 365 企业应用版

在通过 Teams 部署Microsoft 365 企业应用版，必须先卸载任何预先存在的 Teams 应用（如果它们是使用每台计算机安装部署的）。

Teams Microsoft 365 企业应用版每个用户安装一次。 有关详细信息，请参阅在 [VDI Teams或更新桌面](#install-or-update-the-teams-desktop-app-on-vdi)应用部分。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams更新Microsoft 365 企业应用版部署

Teams添加到现有安装中的 Microsoft 365 企业应用版。 由于Microsoft 365 企业应用版仅Teams用户安装，请参阅在 [VDI Teams桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)部分。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>将Teams与每台计算机的安装和Microsoft 365 企业应用版

Microsoft 365 企业应用版不支持每台计算机安装 Teams。 若要使用每台计算机安装，必须从Teams排除Microsoft 365 企业应用版。 请参阅[将 Teams 桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) 和如何通过 Teams [排除Microsoft 365 企业应用版](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)部分。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何通过Teams排除Microsoft 365 企业应用版

若要详细了解 Teams 和 Microsoft 365 企业应用版，请参阅如何从 Microsoft 365 企业应用版 的新安装中排除 [Teams 和使用组](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)策略来控制 [Teams。](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>将Teams桌面应用部署到 VM

1. 使用Teams之一下载与 VDI VM 操作系统匹配的 MSI 包：

    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 对于政府云，请参阅使用 Teams [Windows Installer (MSI ](msi-deployment.md)) 批量安装) ，了解 MSI 文件的下载链接。

    所需的桌面应用Teams版本为 1.3.00.4461。 早期版本不支持 PSTN 保留。

2. 运行以下命令之一，将 MSI 安装到 VDI VM：

    - 按用户安装 (默认) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此过程是默认安装，它Teams用户`%AppData%`文件夹。 此时，黄金映像设置已完成。

        > [!IMPORTANT]
        > Teams在非永久性设置上无法正常执行按用户安装。

    - 每台计算机安装

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此过程会将所需的注册表项添加到计算机，使Teams知道它是 VDI 实例。  如果没有它，安装程序将出错，指出："安装失败。  在未检测到 VDI 环境时，无法为所有用户安装。"

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此过程将Teams `%ProgramFiles(x86)%` 64 `%ProgramFiles%` 位操作系统上的 文件夹和 32 位操作系统上的 文件夹。 此时，黄金映像设置已完成。

        > [!IMPORTANT]
        >  非Teams需要每台计算机安装一个客户端。

        当下一个交互式登录会话启动时，Teams启动并请求凭据。

        > [!NOTE]
        > 这些示例还使用 `ALLUSERS=1` 参数。 设置此参数时，Teams Machine-Wide安装程序会显示在"控制面板"中的"程序和功能"中，&应用的"Windows 设置"功能"中供计算机所有用户使用。  然后，所有用户都可以卸载Teams管理员凭据。
        >
        > 了解 和 的区别非常重要`ALLUSERS=1``ALLUSER=1`。 参数 `ALLUSERS=1` 可以在非 VDI 和 VDI `ALLUSER=1` 环境中使用，而 参数仅在 VDI 环境中用于指定每台计算机的安装。

3. 从 VDI VM 卸载 MSI。 有两种方法可以卸载Teams。

    - **PowerShell 脚本**：可以使用 Teams [部署清理](scripts/powershell-script-deployment-cleanup.md) PowerShell 脚本卸载Teams并Teams用户的文件夹。 针对计算机上安装了 Teams的每个用户配置文件运行脚本。
    - **命令行**：运行以下命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      此过程从文件夹Teams`%ProgramFiles(x86)%`卸载`%ProgramFiles%`文件夹，具体取决于操作系统环境。

## <a name="teams-on-vdi-performance-considerations"></a>Teams VDI 性能注意事项

有各种虚拟化设置配置，每个配置都有不同的优化重点。 例如，配置可能侧重于用户密度。 规划时，请考虑以下事项，以帮助根据组织的工作负荷需求优化设置。

- **最低** 要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。 例如，对于使用需要更多计算资源的应用程序的开发人员的工作负荷。
- **依赖项**：这些依赖项包括对基础结构、工作负荷的依赖，以及桌面应用Teams环境注意事项。
- **VDI 上的已禁用** 功能：Teams禁用 VDI 的 GPU 密集型功能，这有助于改善暂时性 CPU 利用率。 禁用了以下功能：
    - Teams CSS 动画
    - Giphy 自动启动

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams呼叫和会议在 VDI 上通话

除了聊天和协作，Teams虚拟化提供商平台提供 VDI 上的呼叫和会议功能。 支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。 下图提供了体系结构的概述。

![显示 VDI Teams的图示。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果当前在 VDI 中运行 Teams 但不进行 AV 优化，并且使用尚不支持用于优化的功能 (例如，在应用共享) 时提供并控制，必须设置虚拟化提供程序策略以关闭 Teams 重定向。 这意味着Teams不会优化媒体会话。 若要了解如何设置策略以关闭重定向Teams，请与虚拟化提供商联系。

### <a name="network-requirements"></a>网络要求

建议评估环境，确定可能影响整体云语音和视频部署的任何风险和要求。 使用[Skype for Business评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试网络是否已准备好Teams。

若要详细了解如何准备网络Teams，请参阅[准备](prepare-network.md)组织的网络以Teams。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>从 VDI Skype for Business迁移到 VDI Teams VDI 上的客户端

如果要从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams，则除了这两个应用程序之间的差异外，也实现 VDI 时存在一些差异。 VDI 中当前不支持的Teams VDI Skype for Business如下所示：

- 在 VDI 中禁用某些 AV 功能的按平台策略
- 在应用共享时授予并控制
- 无音频聊天中的屏幕共享
- 同时发送和接收视频和屏幕共享

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams Chrome 浏览器与适用于 VDI Teams桌面应用

Teams Chrome 浏览器上的应用无法通过 AV 优化Teams VDI 桌面应用。 聊天和协作体验如期工作。 当需要媒体时，某些体验可能无法满足用户在 Chrome 浏览器上的期望：

- 音频和视频流式处理体验可能并非最佳。 用户可能会遇到延迟或质量降低的情况。
- 设备设置在浏览器设置中不可用。
- 设备管理通过浏览器进行处理，需要在浏览器网站设置中设置多个设置。
- 设备设置可能还需要在设备管理Windows设置。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams聊天和协作在 VDI 上聊天

如果你的组织希望仅使用 Teams 中的聊天和协作功能，你可以设置用户级策略以关闭呼叫和会议Teams。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置策略以关闭呼叫和会议功能

可以使用管理中心或 PowerShell Teams策略。 策略更改最多需要几个小时才能传播。 如果未立即看到给定帐户的更改，请在几小时后重试。

[**调用策略**](teams-calling-policy.md)：Teams包括内置的 **DisallowCalling** 调用策略，其中所有调用功能都已关闭。 将 **DisallowCalling** 策略分配给组织中在虚拟化环境中Teams用户。

[**会议策略**](meeting-policies-overview.md)Teams包括内置的 **AllOff** 会议策略，其中所有会议功能都已关闭。 将 **AllOff** 策略分配给组织中在虚拟化环境中Teams用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用管理中心Teams策略

将 **DisallowCalling 调用** 策略和 **AllOff** 会议策略分配给用户：

1. 在管理中心左侧导航Teams，转到"用户 **"**。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **"调用策略"** 下， **单击"DisallowCalling"**。
    2. 在" **会议策略"下**，单击" **AllOff"**。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在管理中心的Teams导航中，转到"用户"，然后搜索用户或筛选视图以显示想要的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户， **请单击&#x2713;(** 表) 的复选框。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，也可以执行以下操作：

1. 在管理中心Teams导航中，转到要分配的策略。 例如：
    - 转到 **VoiceCalling** >  策略，并单击 **"DisallowCalling"**。
    - 转到 **"会议** > **""会议策略"**，然后单击" **AllOff"**。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击"保存 **"**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将调用 `DisallowCalling` 策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要详细了解使用 PowerShell 管理调用策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOff` 将会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要详细了解使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>通过Teams和协作在 VDI 上迁移 Teams，以优化呼叫和Teams

如果在 VDI 上通过聊天和协作实现 Teams，并且已设置用户级策略以关闭呼叫和会议功能，并且要迁移到具有 AV 优化的 Teams，则必须设置策略，为 VDI 用户启用这些 Teams 的呼叫和会议功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>设置策略以打开呼叫和会议功能

可以使用 Teams 管理中心或 PowerShell 来设置呼叫和会议策略并将其分配给用户。 传播策略更改 (可能需要) 几个小时。 如果未立即看到给定帐户的更改，请在几小时后重试。

[**调用策略**](teams-calling-policy.md)：调用策略Teams控制哪些调用功能可供用户使用。 Teams包括内置的 **AllowCalling** 调用策略，其中所有调用功能都打开。 若要启用所有调用功能，请分配 **AllowCalling** 策略。 或者，创建自定义呼叫策略以打开你需要的呼叫功能并将其分配给用户。

[**会议**](meeting-policies-overview.md)策略：Teams中的会议策略控制用户可以创建的会议类型以及组织中用户安排的会议参与者可用的功能。 Teams包括内置的 **AllOn** 会议策略，其中所有会议功能都打开。 若要启用所有会议功能，请分配 **AllOn** 策略。 或者，创建自定义会议策略以打开你需要的会议功能并为其分配用户。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用管理中心Teams策略

若要向用户 **分配 AllowCalling** 调用策略和 **AllOn** 会议策略，请执行以下操作：

1. 在管理中心左侧导航Teams，转到"用户 **"**。
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1. 在 **"调用策略"** 下，单击" **AllowCalling"**。
    2. 在" **会议策略"** 下，单击" **AllOn"**。
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在管理中心的Teams导航中，转到"用户"，然后搜索用户或筛选视图以显示想要的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户， **请单击&#x2713;(** 表) 的复选框。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，也可以执行以下操作：

1. 在管理中心Teams导航中，转到要分配的策略。 例如：
    - 转到 **VoiceCalling** >  策略，并单击"**AllowCalling"**。
    - 转到 **"会议** > **""会议策略"**，然后单击" **AllOn"**。
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击"保存 **"**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将调用 `AllowCalling` 策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要详细了解使用 PowerShell 管理调用策略，请参阅 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOn` 将会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要详细了解使用 PowerShell 管理会议策略，请参阅 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>在控件中控制回退Teams

当用户从不受支持的终结点进行连接时，用户会进入回退模式，其中 AV 未优化。 可以通过设置以下注册表值之一来禁用或启用回退 `DWORD` 模式：

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

若要禁用回退模式，将值设置为 **1**。 若要仅启用音频，将值设置为 **2**。 如果该值不存在或设置为 **0** (零) ，则启用回退模式。

此功能在 Teams 1.3.00.13565 及更高版本中可用。

## <a name="disable-audio-and-video-settings-for-vdi"></a>禁用 VDI 的音频和视频设置

Teams模块中提供了Teams策略。 这些策略处于活动状态，在未优化的 VDI 环境中强制实施。

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> 这仅适用于未优化的环境。

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

如果用户的 VDI 策略设置为在 `$true` VDI `DisableCallsAndMeetings` Teams登录，则他们无法：

- 拨打电话。
- 加入会议。
- 聊天中的屏幕共享。

应禁用所有类型的调用。

> [!NOTE]
> 这仅适用于未优化的环境。

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

如果 VDI 策略设置为`$true`登录到 VDI `DisableAudioVideoInCallsAndMeetings` Teams，则用户：

- 可以从聊天屏幕共享。
- 可以加入会议并共享屏幕，将其音频移动到电话。
- 无法从 VDI 进行人对人的音频和视频通话。

> [!NOTE]
> 这仅适用于未优化的环境。

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

- 通过每台计算机安装，Teams VDI 上的配置不会以非 VDI 客户端Teams的方式自动更新。 必须安装新的 MSI 来更新 VM 映像，如在 VDI 上安装或Teams[桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)部分中所述。 必须卸载当前版本才能更新到较新版本。
- 在 Citrix 环境中，如果用户在运行 Teams 时从虚拟机断开连接，Teams 更新可能会导致用户在重新连接时为 AV 保持未优化状态。 建议用户在与 Citrix Teams断开连接之前退出配置，以避免这种情况。
- Teams应按用户或每台计算机部署。 不支持Teams每个用户和每台计算机的并发数进行部署。 若要从每台计算机或每个用户迁移到其中一种模式，请按照卸载过程操作并重新部署到任一模式。
- Azure 虚拟桌面目前不支持基于 macOS 和 Linux 的客户端。
- 快速租户切换可能会导致 VDI 上与调用相关的问题，例如屏幕共享不可用。 重新启动客户端将缓解这些问题。

### <a name="calling-and-meetings"></a>呼叫和会议

不支持以下呼叫和会议功能：

- 任何多窗口功能（如新会议体验）或新会议体验附带的任何功能
- Citrix 和 VMware Teams应用和设备之间的 HID 按钮和 LED 控件
- 背景模糊和效果
- 广播和实时事件制作者和演示者角色
- Location-Based LBR (路由) 
- PSTN 呼叫回铃音
- 共享系统音频/计算机声音
- 直接路由的媒体旁路
- 缩放控件

> [!NOTE]
> 我们正在努力添加当前仅在非 VDI 环境中可用的呼叫和会议功能。 这些可能包括对质量的更多管理员控制、其他屏幕共享方案和最近添加到 Teams。 请联系Teams代表，详细了解即将推出的功能。

以下是呼叫和会议的已知问题和限制：

- 与视频Skype for Business仅限于音频通话;没有视频形式。
- 传入和传出视频流分辨率限制为 720p 分辨率。
- 仅支持来自传入相机或屏幕共享流的一个视频流。 当存在传入的屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。
- Teams设备断开连接，然后重新连接，则不切换到使用用户选择的最后一个音频设备。
- 实时事件未优化。
- 传出屏幕共享：
  - 不支持应用程序共享。
- 授予控制权并控制：
  - 在屏幕共享或应用程序共享会话期间不受支持。
  - 在共享会话PowerPoint支持。

有关Teams VDI 的已知问题，请参阅[在Teams支持。](/MicrosoftTeams/troubleshoot/teams-welcome)

## <a name="troubleshooting"></a>疑难解答

### <a name="troubleshoot-citrix-components"></a>Citrix 组件故障排除

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams崩溃或Teams登录屏幕为空

这是 Citrix VDA 版本 1906 和 1909 的已知问题。 若要解决此问题，请添加以下 `DWORD` `204` 注册表值，将其设置为 (十六进制) 。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

然后重启 VDA。 若要了解有关详细信息，请参阅此 Citrix 支持文章[排查 HDX 优化问题Microsoft Teams](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相关主题

- [使用 MSI Teams安装程序Windows安装 (安装) ](msi-deployment.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Azure Microsoft Teams桌面版](/azure/virtual-desktop/teams-on-wvd)
