---
title: 适用于虚拟化桌面基础结构的 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在虚拟桌面基础结构和 VDI (中) Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 687726febc81a727c4f6da4824487672c602809e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820982"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用 Microsoft Teams 的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是虚拟化技术，在数据中心的集中服务器上托管桌面操作系统和应用程序。 这使具有完全安全且合规的集中源的用户能够获得完全个性化的桌面体验。

虚拟化环境中 Microsoft Teams 支持聊天和协作。 此外，Windows 虚拟桌面、Citrix 和 VMware 平台也支持呼叫和会议功能。

虚拟化环境中的团队支持多种配置。 这些模式包括 VDI、专用、共享、持久和非持久模式。 功能在持续开发中并定期添加，功能将在几个月和数年内扩展。

在虚拟化环境中使用 Teams 可能与在非虚拟化环境中使用 Teams 稍有不同。 例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。

若要确保获得最佳用户体验，请遵循本文中的指导。

> [!Note]
> 有关不同平台上的 Teams VDI 的详细信息，请参阅["按平台显示 Teams 功能"。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>VDI 组件上的 Teams

在虚拟化环境中使用 Teams 需要以下组件。

- **虚拟化代理**：虚拟化提供程序（例如 Azure）的资源和连接管理器
- **虚拟桌面**：运行 Microsoft Teams (VM) 堆栈
- **精简客户端**：用户实际与它交互的终结点
- **Teams 桌面应用**：Teams 桌面客户端应用

## <a name="teams-on-vdi-requirements"></a>VDI 上的 Teams 要求

### <a name="virtualization-provider-requirements"></a>虚拟化提供商要求

Teams 桌面应用已使用领先的虚拟化解决方案提供商进行验证。 对于多个市场提供商，我们建议你咨询虚拟化解决方案提供商，以确保满足最低要求。
  
目前，VDI 上具有音频/ (AV) 优化的 Teams 已通过 Windows 虚拟桌面、Citrix 和 VMware 的认证。 查看本部分中的信息，确保满足正确功能的所有要求。

### <a name="platforms-certified-for-teams"></a>通过 Teams 认证的平台

以下平台具有适用于 Teams 的虚拟桌面基础结构解决方案。

|平台|解决方案|
|----|---|
|![表示 Microsoft 的徽标](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虚拟桌面</a> |
|![表示 Citrix 的徽标](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a> |
|![表示 VMware 的徽标](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Windows 虚拟桌面

Windows 虚拟桌面为 VDI 上的 Teams 提供 AV 优化。 若要了解更多内容以及要求和安装，请参阅"[在 Windows 虚拟桌面上使用 Teams"。](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虚拟应用和桌面要求

Citrix 虚拟应用和桌面 (以前称为 XenApp 和 XenDesktop) 为 VDI 上的 Teams 提供 AV 优化。 借助 Citrix 虚拟应用和桌面，VDI 上的 Teams 除了支持聊天和协作外，还支持呼叫和会议功能。

可以在 Citrix 下载站点下载最新版本的 Citrix 虚拟应用 [和桌面](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)。  (需要先登录。) 默认情况下，所需的组件将捆绑到 [Citrix 工作区应用 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虚拟交付代理 (VDA) 中。 无需在 CWA 或 VDA 上安装任何其他组件或插件。

有关最新的服务器和客户端要求，请参阅 [此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace 和桌面要求

VMware Horizon 是一个新式平台，用于跨混合云安全交付虚拟桌面和应用。 为了提供出色的最终用户体验，VMware Horizon 为 Teams 提供媒体优化。 此优化可跨虚拟桌面和应用提高整体工作效率，并增强使用 Teams 进行通话和开会的用户体验。

可以从"VMware 下载"页下载最新版本的 [VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon。 默认情况下，所需的媒体优化组件是 Horizon Agent 和 Horizon 客户端的一部分，无需安装任何其他插件来使用 Teams 的优化功能。

若要获取有关如何为 Teams 配置媒体优化的最新要求和说明，请参阅 [此 VMware 网站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安装或更新 Teams 桌面应用

可以使用每台计算机安装或者使用 MSI 包按用户安装来部署适用于 VDI 的 Teams 桌面应用。 确定使用哪种方法取决于是使用持久性设置还是非持久性设置，以及组织的关联功能需求。

对于专用的持久性设置，任一方法都正常工作。 但是，对于非永久性设置，Teams 需要每台计算机安装才能高效工作。 请参阅 ["非永久性设置"](#non-persistent-setup) 部分。

使用每台计算机安装时，将禁用自动更新。 这意味着要更新 Teams 应用，必须卸载当前版本以更新到较新版本。 通过按用户安装，将启用自动更新。 对于大多数 VDI 部署，建议使用每台计算机安装来部署 Teams。

若要更新到最新的 Teams 版本，请从卸载过程开始，然后是最新的 Teams 版本部署。

若要使 VDI 环境中 Teams AV 优化正常工作，精简客户端终结点必须有权访问 Internet。 如果精简客户端终结点上未提供 Internet 访问，优化启动不会成功。 这意味着用户位于未优化的媒体状态。

#### <a name="dedicated-persistent-setup"></a>专用永久性设置

在专用的永久性设置中，用户注销后会保留用户的本地操作系统更改。 对于永久性安装，Teams 支持每用户和每台计算机安装。

下面是建议的最低 VM 配置。

|参数  |工作站操作系统  |服务器操作系统  |
|---------|---------|---------|
|vCPU   |    2 个核心     |  4、6 或 8<br>必须了解 NUMA (配置中) 不一致的内存访问，并相应地配置 VM。     |
|RAM     |   4 GB      | 每个用户 512 到 1024 MB        |
|存储空间    | 8 GB        | 40 到 60 GB        |

#### <a name="non-persistent-setup"></a>非永久性设置

在非永久性设置中，用户注销后不会保留用户的本地操作系统更改。 此类设置通常共享多用户会话。 VM 配置因用户数和可用物理机资源而异。

对于非永久性设置，必须将 Teams 桌面应用安装在每台计算机的黄金映像中。  (，请参阅"在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安装或更新 Teams 桌面应用"部分。) 这将确保在用户会话期间高效启动 Teams 应用。

将 Teams 与非永久性设置一同使用还需要配置文件缓存管理器，以高效同步 Teams 运行时数据。这可确保在用户会话期间缓存 (特定用户的信息，例如，) 配置文件和设置。 确保同步这两个文件夹中的数据。  

- C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) 
- C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) 

有各种可用的缓存管理器解决方案。 例如[，FSLogix。](https://docs.microsoft.com/fslogix/overview) 有关特定配置说明，请咨询缓存管理器提供程序。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>用于非永久性设置的 Teams 缓存内容排除列表

从 Teams 缓存文件夹 %appdata%/Microsoft/Teams 中排除以下内容。 排除这些项有助于减小用户缓存大小，以进一步优化非永久性设置。

- .txt 文件
- Media-stack 文件夹
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) 

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>适用于企业的 Microsoft 365 应用

使用适用于企业的 Microsoft 365 应用在 VDI 上部署 Teams 时，请考虑以下事项。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>通过适用于企业的 Microsoft 365 应用全新部署 Teams

通过适用于企业的 Microsoft 365 应用部署 Teams 之前，必须先卸载任何预先存在的 Teams 应用（如果它们是使用每台计算机安装部署的）。

通过 Microsoft 365 企业版应用安装的 Teams 是按用户安装的。 若要了解有关详细信息，请参阅" [在 VDI 上安装或更新 Teams 桌面应用"](#install-or-update-the-teams-desktop-app-on-vdi) 部分。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>通过用于企业更新的 Microsoft 365 应用进行 Teams 部署

Teams 也会添加到适用于企业的 Microsoft 365 应用的现有安装中。 由于适用于企业的 Microsoft 365 应用仅按用户安装 Teams，请参阅"在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安装或更新 Teams 桌面应用"部分。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>将 Teams 与每台计算机安装和适用于企业的 Microsoft 365 应用一同使用

适用于企业的 Microsoft 365 应用不支持每台计算机安装 Teams。 若要使用每台计算机安装，必须从适用于企业的 Microsoft 365 应用中排除 Teams。 请参阅" [将 Teams 桌面应用部署到 VM"](#deploy-the-teams-desktop-app-to-the-vm) 和 ["如何通过适用于企业的 Microsoft 365](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 应用排除 Teams 部署"部分。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何通过适用于企业的 Microsoft 365 应用排除 Teams 部署

若要详细了解 Teams 和适用于企业的 Microsoft 365 应用，请参阅"如何从适用于企业的 [Microsoft 365](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 应用的新安装中排除 [Teams"，](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)以及使用组策略来控制 Teams 的安装。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>将 Teams 桌面应用部署到 VM

1. 使用下列链接之一下载与 VDI VM 操作系统匹配的 Teams MSI 包：

    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 对于政府云，请参阅 ["使用 Microsoft 终结点配置](msi-deployment.md) 管理器安装 Microsoft Teams"，了解 MSI 文件的下载链接。

    所需的 Teams 桌面应用最低版本是版本 1.3.00.4461。  (.) 不支持 PSTN 保留

2. 通过运行以下命令之一，将 MSI 安装到 VDI VM：

    - 按用户安装 (默认) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此过程是默认安装，用于将 Teams 安装到 %AppData% 用户文件夹。 此时，黄金映像设置已完成。 Teams 在非永久性设置上无法正常执行按用户安装。

    - 每台计算机安装

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此过程将 Teams 安装到 64 (操作系统 (x86) 文件夹，将 Teams 安装到 32 位操作系统上的 Program Files 文件夹。 此时，黄金映像设置已完成。 非永久性设置需要每台计算机安装 Teams。

        下一个交互式登录会话将启动 Teams 并请求凭据。

        > [!NOTE]
        > 这些示例还使用 **ALLUSERS=1** 参数。 设置此参数时，Teams Machine-Wide 安装程序会显示在"控制面板"中的"程序和功能"中，以及"应用& Windows 设置中针对计算机的所有用户显示的功能。 然后，所有用户都可以卸载 Teams（如果他们具有管理员凭据）。
        必须了解 **ALLUSERS=1** 和 **ALLUSER=1 的区别**。 **ALLUSERS=1** 参数可用于非 VDI 和 VDI 环境，而 **ALLUSER=1** 参数仅在 VDI 环境中用于指定每台计算机安装。

3. 从 VDI VM 卸载 MSI。 有两种方法可以卸载 Teams。

    - PowerShell 脚本：可以使用此 [PowerShell 脚本](scripts/powershell-script-deployment-cleanup.md) 卸载 Teams 并删除用户的 Teams 文件夹。 为计算机上安装 Teams 的每个用户配置文件运行脚本。
    - 命令行：运行以下命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      此过程从 x86 (程序) 或 Program Files 文件夹中卸载 Teams，具体取决于操作系统环境。

## <a name="teams-on-vdi-performance-considerations"></a>有关 VDI 性能的 Teams 注意事项

有各种虚拟化设置配置，每个配置都有不同的优化焦点。 例如，配置可能侧重于用户密度。 规划时，请考虑以下事项，以便根据组织的工作负荷需求优化设置。

- 最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。 例如，对于使用需要更多计算资源的应用程序的开发人员的工作负荷。
- 依赖项：其中包括对基础结构、工作负荷的依赖关系，以及 Teams 桌面应用外部的其他环境注意事项。
- VDI 上的已禁用功能：Teams 禁用 VDI 的 GPU 密集型功能，这有助于改善暂时性 CPU 利用率。 禁用了以下功能：
    - Teams CSS 动画
    - Giphy 自动启动

## <a name="teams-on-vdi-with-calling-and-meetings"></a>具有通话和会议的 VDI 上的 Teams

除了聊天和协作外，支持虚拟化提供商平台的 VDI 上的 Teams 还支持通话和会议。 支持的功能基于 WebRTC 媒体堆栈和虚拟化提供程序实现。 下图提供了体系结构的概述。

![显示 Teams on VDI 体系结构的示意图](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果当前运行 Teams 时未在 VDI 中优化 AV，并且使用尚不支持用于优化的功能 (如在应用共享) 时授予和控制，必须设置虚拟化提供程序策略以关闭 Teams 重定向。 这意味着 Teams 媒体会话不会优化。 若要了解如何设置策略以关闭 Teams 重定向的步骤，请联系虚拟化提供商。

### <a name="network-requirements"></a>网络要求

建议评估环境，确定可能影响总体云语音和视频部署的任何风险和要求。 使用 [Skype for Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) 测试网络是否适用于 Teams。

若要详细了解如何为 Teams 准备网络，请参阅"为 Teams 准备[组织的网络"。](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams

如果要从 VDI 上的 Skype for Business 迁移到 VDI 上的 Teams，则除了两个应用程序之间的差异外，实施 VDI 时也有一些差异。 Skype for Business VDI 中的 Teams VDI 目前不支持的一些功能如下所示：

- 每个平台的策略，用于禁用 VDI 中的某些 AV 功能
- 在应用共享时授予并控制
- 无音频聊天中的屏幕共享
- 同时发送和接收视频和屏幕共享

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 浏览器上的 Teams 与适用于 VDI 的 Teams 桌面应用

Chrome 浏览器上的 Teams 不提供用于 VDI 的 Teams 桌面应用与 AV 优化的替换项。 聊天和协作体验如期工作。 当需要媒体时，某些体验可能无法满足用户在 Chrome 浏览器中的期望：

- 音频和视频流式处理体验可能并非最佳。 用户可能会遇到延迟或质量下降的情况。
- 设备设置在浏览器设置中不可用。
- 设备管理通过浏览器进行处理，需要在浏览器网站设置中设置多个设置。
- 可能还需要在 Windows 设备管理中设置设备设置。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>使用聊天和协作的 VDI 上的 Teams

如果你的组织只想使用 Teams 中的聊天和协作功能，你可以设置用户级策略以关闭 Teams 中的呼叫和会议功能。 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置策略以关闭呼叫和会议功能

可以使用 Microsoft Teams 管理中心或 PowerShell 设置策略。 传播策略更改 (可能需要) 几个小时。 如果未立即看到给定帐户的更改，请在几个小时后重试。

[**调用策略**](teams-calling-policy.md)：Teams 包括内置的 DisallowCalling 调用策略，其中所有调用功能都已关闭。 将 DisallowCalling 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

[**会议策略**](meeting-policies-in-teams.md)：Teams 包括内置的 AllOff 会议策略，其中所有会议功能都已关闭。 将 AllOff 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心分配策略

将 DisallowCalling 调用策略和 AllOff 会议策略分配给用户：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**用户"。**
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1.  在 **"调用策略**"下，**单击"DisallowCalling"。**
    2.  在 **"会议策略"** 下，单击 **"AllOff"。**
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。 例如：
    - 转到 **语音**  >  **呼叫策略，** 然后单击 **"DisallowCalling"。**
    - 转到"**会议**  >  **会议策略"，** 然后单击 **"AllOff"。**
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击"保存 **"。**

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 将 DisallowCalling 调用策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOff 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>通过聊天和协作迁移 VDI 上的 Teams，以优化 Teams 的通话和会议

如果在 VDI 上已有 Teams 的聊天和协作实现，其中你已设置用户级策略以关闭呼叫和会议功能，并且你将迁移到具有 AV 优化的 Teams，则必须设置策略，为 VDI 用户启用这些 Teams 的呼叫和会议功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>设置策略以启用呼叫和会议功能

可以使用 Microsoft Teams 管理中心或 PowerShell 设置呼叫和会议策略并将其分配给用户。 传播策略更改 (可能需要) 几个小时。 如果未立即看到给定帐户的更改，请在几小时后重试。

[**调用策略**](teams-calling-policy.md)：在 Teams 中调用策略控制哪些调用功能可供用户使用。 Teams 包括内置的 AllowCalling 调用策略，其中所有调用功能都打开。 若要启用所有调用功能，请分配 AllowCalling 策略。 或者，创建自定义呼叫策略以打开你需要的呼叫功能并将其分配给用户。 

[**会议策略**](meeting-policies-in-teams.md)：Teams 中的会议策略控制用户可以创建的会议类型和可供组织中用户安排的会议参与者使用的功能。 Teams 包括内置的 AllOn 会议策略，其中所有会议功能都开启。 若要启用所有会议功能，请分配 AllOn 策略。 或者，创建自定义会议策略以打开您需要的会议功能，并为其分配用户。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心分配策略

若要向用户分配 AllowCalling 调用策略和 AllOn 会议策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**用户"。**
2. 单击用户名的左侧以选择用户，然后单击“编辑设置”。
3. 执行以下操作：
    1.  在 **"调用策略"** 下，单击 **"AllowCalling"。**
    2.  在 **"会议策略"** 下，单击 **"AllOn"。**
4. 单击“**应用**”。

若要一次向多个用户分配策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请单击&#x2713;(表顶部的) 复选框。
3. 单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。

或者，还可以执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。 例如：
    - 转到"**语音**  >  **呼叫策略"，** 然后单击 **"AllowCalling"。**
    - 转到 **"会议**  >  **会议"策略**，然后单击 **"AllOn"。**
2. 选择“管理用户”。
3. 在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，单击"保存 **"。**

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 将 AllowCalling 调用策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要详细了解如何使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOn 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>在 Teams 中控制回退模式

当用户从不受支持的终结点进行连接时，用户会进入回退模式，其中 AV 未优化。 可以通过设置以下注册表 DWORD 值之一来禁用或启用回退模式：

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

若要禁用回退模式，将值设置为 **1。** 若要仅启用音频，将值设置为 **2。** 如果该值不存在或设置为 **0** (零) ，则启用回退模式。

此功能在 Teams 版本 1.3.00.13565 及更高版本中可用。

## <a name="known-issues-and-limitations"></a>已知问题和限制

### <a name="client-deployment-installation-and-setup"></a>客户端部署、安装和设置

- 通过每台计算机安装，VDI 上的 Teams 不会以非 VDI Teams 客户端的方式自动更新。 必须按"在 [VDI](#install-or-update-the-teams-desktop-app-on-vdi) 上安装或更新 Teams 桌面应用"部分中所述安装新的 MSI 来更新 VM 映像。 必须卸载当前版本以更新到较新版本。
- 应该按用户或每台计算机部署团队。 不支持为每个用户和每台计算机同时部署 Teams。 若要从每台计算机或每个用户迁移到这些模式之一，请遵循卸载过程并重新部署到任一模式。
- Windows 虚拟桌面和 VMware 目前不支持基于 MacOS 和 Linux 的客户端。
- Citrix 目前不支持 MacOs 客户端。
- Citrix 不支持使用在终结点上定义的显式 HTTP 代理。

### <a name="calling-and-meetings"></a>呼叫和会议

不支持以下呼叫和会议功能：

- 增强的紧急服务
- Teams 应用和设备之间的 HID 按钮和 LED 控件
- 背景模糊和效果
- 直播和实时事件制作者和演示者角色
- Location-Based LBR (路由) 
- 呼叫寄存
- 呼叫队列
- 共享系统音频/计算机声音
- 直接路由的媒体旁路

> [!NOTE]
> 我们正在努力添加当前仅在非 VDI 环境中可用的呼叫和会议功能。 这些可能包括对质量的更多管理员控制、其他屏幕共享方案和最近添加到 Teams 的高级功能。 请联系 Teams 代表，详细了解即将推出的功能。

以下是通话和会议的已知问题和限制：

- Skype for Business 的互操作性仅限于音频通话;没有视频形式。
- 会议或群组通话仅支持单个传入视频流。 当多人发送视频时，在任意给定时间仅显示主发言人的视频。
- 传入和传出视频流分辨率限制为 720p 分辨率。 这是 WebRTC 限制。
- 仅支持来自传入相机或屏幕共享流的一个视频流。 当存在传入的屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。
- Teams 不会切换为使用用户选择的最后一个音频设备（如果设备已断开连接，然后重新连接）。
- 传出屏幕共享：
    - 不支持应用程序共享。
- 授予控制权并控制：
    - 在屏幕共享或应用程序共享会话期间不受支持。
    - 在 PowerPoint 共享会话期间受支持。
- 仅 Citrix 限制
    - 在多监视器设置中共享屏幕时，仅共享主监视器。
    - 不支持 CWA 上的高 DPI 缩放。

有关与 VDI 不相关的 Teams 已知问题，请参阅 [组织中支持团队](Known-issues.md)。

## <a name="troubleshooting"></a>疑难解答

### <a name="troubleshoot-citrix-components"></a>Citrix 组件疑难解答

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams 崩溃或 Teams 登录屏幕为空

这是 Citrix VDA 版本 1906 和 1909 的已知问题。 若要解决此问题，请添加以下注册表 DWORD 值，将其设置为 204 (十六进制) 。

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

然后，重启 VDA。 若要了解有关详细信息，请参阅此 Citrix 支持文章 [：Teams 的 HDX 优化故障排除](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相关主题

- [使用 MSI 安装 Microsoft Teams](msi-deployment.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Windows 虚拟桌面上使用 Microsoft Teams](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
