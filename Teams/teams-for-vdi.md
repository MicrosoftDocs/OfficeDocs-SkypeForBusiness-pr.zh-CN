---
title: 适用于虚拟化桌面基础结构的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 了解如何在虚拟桌面基础结构（VDI）环境中运行 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2afe86014bcce01d60ceef768f6f888718c3696c
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952845"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用 Microsoft 团队的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构（VDI）是在数据中心的集中式服务器上托管桌面操作系统和应用程序的虚拟化技术。 这使具有完全安全和合规的集中源的用户能够获得完全个性化的桌面体验。
 
虚拟环境中的 Microsoft 团队支持聊天和协作，并且通过 Citrix 平台，还支持调用和会议功能。

虚拟环境中的团队支持多个配置。 其中包括 VDI、专用、共享、持久和非持久模式。 功能在连续开发中且定期添加，并且功能将在未来的几个月和几年内扩展。
 
在虚拟化环境中使用团队可能与在非虚拟化环境中使用团队稍有不同。 例如，某些高级功能在虚拟化环境中可能不可用，并且视频分辨率可能有所不同。 若要确保获得最佳的用户体验，请按照本文中的指南操作。

## <a name="teams-on-vdi-components"></a>VDI 组件上的团队

在虚拟化环境中使用团队需要以下组件。

- **虚拟化代理**：针对虚拟化提供程序的资源和连接管理器，例如 Azure
- **虚拟桌面**：运行 Microsoft 团队的虚拟机（VM）堆栈
- **瘦客户端**：用户使用物理接口的终结点
- **团队桌面应用**：这是团队桌面客户端应用程序

## <a name="teams-on-vdi-requirements"></a>VDI 要求的团队

### <a name="virtualization-provider-requirements"></a>虚拟化提供商要求

团队桌面应用已通过主流虚拟化解决方案提供商进行验证。 有了多个市场提供商，我们建议你咨询你的虚拟化解决方案提供商以确保满足最低要求。
  
目前，带有音频/视频（AV）优化的团队在通过 Citrix 认证。 查看本部分中的信息，确保同时满足 Citrix 和团队要求才能获得正确的功能。

### <a name="partners-certified-for-teams"></a>合作伙伴认证的团队

以下合作伙伴拥有团队的虚拟桌面基础结构解决方案。

|配偶|合作伙伴解决方案|
|----|---|
|![表示 Citrix 的徽标](media/citrix.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虚拟应用和桌面</a> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虚拟应用和桌面要求

Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）为适用于 VDI 的团队提供 AV 优化。 通过 Citrix 虚拟应用和桌面，VDI 上的团队不仅支持聊天和协作，还支持呼叫和会议功能。

你可以在[此处](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下载 Citrix 虚拟应用和桌面的最新版本。 （您需要首先登录。）默认情况下，必要的组件捆绑到[Citrix 工作区应用（CWA）](https://www.citrix.com/downloads/workspace-app/)和虚拟交付代理（VDA）中。 无需在 CWA 或 VDA 上安装任何其他组件或插件。

有关最新的服务器和客户端要求，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安装或更新团队桌面应用

你可以使用 MSI 程序包使用每台计算机安装或每用户安装来部署适用于 VDI 的团队桌面应用。 决定使用哪种方法取决于您使用的是持久设置还是非持久设置以及您的组织的相关功能需求。
对于专用的永久设置，这两种方法都适用。  但是，对于非持久设置，团队需要每计算机安装才能高效工作。 请参阅[非持久设置](#non-persistent-setup)部分。

对于每台计算机安装，自动更新已禁用。 这意味着，若要更新团队应用，必须卸载当前版本才能更新到较新的版本。 对于每用户安装，自动更新已启用。 对于大多数 VDI 部署，建议使用每台计算机安装部署团队。

若要更新到最新的团队版本，请从卸载过程开始，后跟最新的团队版本部署。

为了使 VDI 环境中的团队防病毒优化正常工作，瘦客户端终结点必须有权访问 internet。 如果在瘦客户端终结点上无法访问 internet，优化启动将不会成功。 这意味着用户处于非优化的媒体状态。

#### <a name="dedicated-persistent-setup"></a>专用永久设置

在专用的永久设置中，用户注销后，将保留用户的本地操作系统更改。  对于永久设置，团队同时支持每用户和每计算机安装。

以下是推荐的最低 VM 配置。

|参数  |工作站操作系统  |服务器操作系统  |
|---------|---------|---------|
|vCPU   |    2核     |  4、6或8<br>了解基础非统一内存访问（NUMA）配置和相应配置 Vm 非常重要。     |
|RAM     |   4 GB      | 每个用户512到 1024 MB        |
|存储空间    | 8 GB        | 40到 60 GB        |

#### <a name="non-persistent-setup"></a>非持久设置

在非持久设置中，用户注销后将不保留用户的本地操作系统更改。 此类设置通常共享多用户会话。 VM 配置根据用户数量和可用的物理箱资源而有所不同。

对于非持久设置，必须将团队桌面应用安装到黄金图像的每台计算机上。 （若要了解详细信息，请参阅在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)）。 这可确保在用户会话期间有效地启动团队应用。 将团队与非持久性设置配合使用时，还需要配置文件缓存管理器才能高效团队运行时数据同步。这可确保在用户会话期间缓存相应的特定于用户的信息（例如，用户数据、配置文件和设置）。  有多种可用的缓存管理器解决方案。 例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。 有关特定配置说明，请咨询您的缓存管理器提供程序。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>用于非持久设置的工作组缓存的内容排除列表

从 "团队缓存" 文件夹（% appdata%/Microsoft/Teams.）中排除以下项  排除这些帮助将减少用户缓存大小，以进一步优化非持久设置。

- .txt 文件
- 媒体堆叠文件夹

### <a name="office-365-proplus-considerations"></a>Office 365 专业增强版注意事项

在 VDI 上部署具有 Office 365 专业增强版的团队时，请考虑以下事项。

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a>通过 Office 365 专业增强版的新部署团队

在通过 Office 365 专业增强版部署团队之前，必须先卸载任何预先存在的团队应用（如果它们是使用按计算机安装部署的）。

通过 Office 365 专业增强版的团队将针对每个用户进行安装。 若要了解详细信息，请参阅[在 VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)。

#### <a name="teams-deployments-through-office-365-proplus-updates"></a>通过 Office 365 专业增强版更新的团队部署

团队也将添加到 Office 365 专业增强版的现有安装。 由于 Office 365 专业增强版仅为每位用户安装团队，请参阅在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)。

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a>对每台计算机安装使用团队和 Office 365 专业增强版

Office 365 专业增强版不支持团队的每计算机安装。 若要使用每台计算机安装，必须从 Office 365 专业增强版中排除团队。 请参阅将[团队桌面应用部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)和[如何通过 Office 365 专业增强版部分排除团队部署](#how-to-exclude-teams-deployment-through-office-365-proplus)。

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a>如何通过 Office 365 专业增强版排除团队部署

若要了解有关团队和 Office 365 专业增强版的详细信息，请参阅[如何从 Office 365 专业增强版的新安装中排除团队](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，并[使用组策略来控制团队的安装](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>将团队桌面应用部署到 VM

1. 使用以下链接之一下载与你的 VDI VM 操作系统匹配的团队 MSI 程序包：

    - [32位版本](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [64位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    所需的团队桌面应用的最低版本是1.2.00.31357 版本。 （早期版本不支持 PSTN 保留。）

2. 通过运行以下命令之一将 MSI 安装到 VDI VM：

    - 每用户安装（默认）
  
        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        这是默认安装，可将团队安装到% AppData% 用户文件夹。 此时，将完成黄金图像设置。 在非持久设置中，团队将不会在每用户安装中正常工作。
    
    - 每计算机安装

        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        这会将团队安装到64位操作系统上的 "程序文件（x86）" 文件夹和32位操作系统上的 "程序文件" 文件夹中。 此时，将完成黄金图像设置。 对于非持久设置，需要针对每台计算机安装团队。
 
        下一个交互式登录会话将启动团队并要求提供凭据。

3. 从 VDI VM 卸载 MSI。 

    可通过两种方式卸载团队：  
  
    - PowerShell 脚本（推荐）：你可以使用此[PowerShell 脚本](scripts/powershell-script-teams-deployment-clean-up.md)清理目标计算机或用户的团队。 应针对目标计算机上的每个用户执行该应用。 
    
    - 命令行：此方法删除团队，但阻止团队重新安装。 运行以下命令：
  
      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      这将从 "程序文件（x86）" 文件夹或 "程序文件" 文件夹中卸载团队，具体取决于操作系统环境。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 性能注意事项的团队

有多种虚拟化设置配置，每个配置都具有不同的优化焦点。 例如，用户密度。 规划时，请考虑以下事项，以帮助根据组织的工作负载需求优化设置：

- 最低要求：某些工作负荷可能需要使用高于最低要求的资源进行设置。 例如，使用需要更多计算资源的应用程序的开发人员的工作负荷。
- 依赖关系：包括有关基础架构、工作量以及团队桌面应用之外的其他环境注意事项的依赖关系。
- VDI 上已禁用的功能：团队禁用适用于 VDI 的 GPU 密集型功能，这有助于提高暂时 CPU 的利用率。 已禁用以下功能：
    - 团队 CSS 动画
    - Giphy 自动启动

## <a name="teams-on-vdi-with-calling-and-meetings"></a>VDI 上的团队与呼叫和会议

除了聊天和协作，使用基于 Citrix 的平台提供与呼叫和会议支持的 VDI 团队。 支持的功能基于 WebRTC 媒体堆栈和特定于 Citrix 的实现。 下图概括介绍了体系结构。

![显示 VDI 体系结构上的团队的图表](media/teams-on-vdi-architecture.png)

不支持以下呼叫和会议功能：

- 增强的紧急服务
- 团队应用和设备之间的 HID 按钮和 LED 控件
- 背景模糊和效果
- 广播/实时事件
- 基于位置的路由（LBR）
- 呼叫寄存
- 通话队列

> [!IMPORTANT]
> 如果当前在 VDI 中运行团队没有 AV 优化，并且你使用尚不支持的功能（例如，在应用共享时授予和控制），则必须设置 Citrix 策略以关闭团队重定向。 这意味着不会优化团队媒体会话。 有关如何设置策略以关闭团队重定向的步骤，请参阅此[Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。

我们正在努力添加目前仅在非 VDI 环境中可用的呼叫和会议功能。 这些功能可能包括对质量、其他屏幕共享方案以及最近添加到团队的高级功能的更多管理控制。 联系你的团队代表了解有关即将推出的功能的详细信息。

### <a name="network-requirements"></a>网络要求

我们建议你对环境进行评估，以确定任何风险和要求，这些风险和要求会影响你的整体云语音和视频部署。 使用[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)测试您的网络是否已准备好使用团队。

若要了解有关如何为团队准备网络的详细信息，请参阅[为团队准备组织的网络](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>在 vdi 上从 Skype for Business 迁移到 VDI 上的团队

如果你要从 VDI 的 Skype for Business 迁移到 VDI 上的团队，除了两个应用程序之间的区别之外，还有一些差异。 Skype for Business VDI 中的团队 VDI 目前不支持的某些功能如下所示：

- 利用限制媒体比特率的策略控制 VDI 呼叫体验
- 用于禁用 VDI 中的某些 AV 功能的每个平台策略
- 在应用共享时提供和获取控制权
- 不带音频聊天的屏幕共享
- 同时视频和屏幕共享发送和接收

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 浏览器上的团队与 VDI 的团队桌面应用

Chrome 浏览器上的团队不会通过 AV 优化提供适用于 VDI 的团队桌面应用的替代项。 聊天和协作体验按预期工作。 当需要媒体时，有一些体验可能无法在 Chrome 浏览器中满足用户的预期：

- 音频和视频流体验可能不是最佳的。 用户可能会遇到延迟或降低质量。
- "设备设置" 在浏览器设置中不可用。
- 设备管理通过浏览器进行处理，并在浏览器网站设置中需要多个设置。
- 可能还需要在 Windows 设备管理中设置设备设置。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>具有聊天和协作功能的 VDI 团队

如果你的组织希望仅使用团队中的聊天和协作功能，你可以设置用户级策略以关闭团队中的呼叫和会议功能。 此功能级别不需要 Citrix 虚拟应用和桌面。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置用于关闭呼叫和会议功能的策略

你可以使用 Microsoft 团队管理中心或 PowerShell 设置策略。 需要花费一些时间（几个小时）才能传播策略更改。 如果你没有立即看到给定帐户的更改，请在几个小时后重试。

[**通话策略**](teams-calling-policy.md)：团队包括内置的 DisallowCalling 呼叫策略，其中所有的通话功能均处于关闭状态。 将 DisallowCalling 策略分配给组织中使用虚拟环境中的团队的所有用户。

[**会议策略**](meeting-policies-in-teams.md)：团队包括内置的 AllOff 会议策略，其中所有会议功能均处于关闭状态。 将 AllOff 策略分配给组织中使用虚拟环境中的团队的所有用户。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心分配策略

要将 DisallowCalling 呼叫策略和 AllOff 会议策略分配给用户，请按照下列步骤操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。
2. 通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。
3. 请执行下列操作：
    1.  在 "**呼叫策略**" 下，单击 " **DisallowCalling**"。
    2.  在 "**会议策略**" 下，单击 " **AllOff**"。
4. 单击“**应用**”。

若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。 例如：
    - 转到 "**语音** > **呼叫策略**"，然后单击 " **DisallowCalling**"。
    - 转到 "**会议** > **会议策略**"，然后单击 " **AllOff**"。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。 对要添加的每个用户重复此步骤。
5. 添加完用户后，单击 "**保存**"。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 DisallowCalling 调用策略。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOff 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>通过通话和会议将团队与聊天和协作迁移到 Citrix

如果您在 VDI 上有一个现有团队的实现，其中你已设置了用户级策略以关闭呼叫和会议功能，并且你要使用 AV 优化功能迁移到 Citrix，则必须设置策略以启用呼叫和适用于 VDI 用户的团队的会议功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>设置启用呼叫和会议功能的策略

你可以使用 Microsoft 团队管理中心或 PowerShell 为你的用户设置和分配呼叫和会议策略。 需要花费一些时间（几个小时）才能传播策略更改。 如果你没有立即看到给定帐户的更改，请过几个小时后重试。

[**通话策略**](teams-calling-policy.md)：在团队中调用策略控制用户可以使用哪些通话功能。 团队包括内置的 AllowCalling 呼叫策略，其中所有的通话功能均处于打开状态。 若要打开所有通话功能，请分配 AllowCalling 策略。 或者，创建自定义呼叫策略以打开所需的通话功能，并将其分配给用户。 

[**会议策略**](meeting-policies-in-teams.md)：团队中的会议策略控制用户可以创建的会议类型，以及由组织中的用户安排的可供会议参与者使用的功能。 团队包括内置的 AllOn 会议策略，其中所有会议功能均处于打开状态。 若要打开所有会议功能，请分配 AllOn 策略。 或者，创建自定义会议策略以打开所需的会议功能，并向其分配用户。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 团队管理中心分配策略

要将 AllowCalling 呼叫策略和 AllOn 会议策略分配给用户，请按照下列步骤操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"。
2. 通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。
3. 请执行下列操作：
    1.  在 "**呼叫策略**" 下，单击 " **AllowCalling**"。
    2.  在 "**会议策略**" 下，单击 " **AllOn**"。
4. 单击“**应用**”。

若要一次为多个用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者，您也可以执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到要分配的策略。 例如：
    - 转到 "**语音** > **呼叫策略**"，然后单击 " **AllowCalling**"。
    - 转到 "**会议** > **会议策略**"，然后单击 " **AllOn**"。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。 对要添加的每个用户重复此步骤。
5. 添加完用户后，单击 "**保存**"。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例显示了如何使用[Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy)向用户分配 AllowCalling 调用策略。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

若要了解有关使用 PowerShell 管理通话策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

以下示例显示了如何使用[Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)将 AllOn 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

若要了解有关使用 PowerShell 管理会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="known-issues-and-limitations"></a>已知问题和限制

### <a name="client-deployment-installation-and-setup"></a>客户端部署、安装和设置

- 对于每台计算机安装，不会以非 VDI 团队客户端的方式自动更新 VDI 上的团队。 你必须按照在[VDI 部分安装或更新团队桌面应用](#install-or-update-the-teams-desktop-app-on-vdi)中所述，通过安装新 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。
- 应按每个用户或每台计算机来部署团队。 不支持针对每个用户和每台计算机并行部署团队。  若要从每台计算机或每用户迁移到这些模式之一，请按照卸载过程进行，然后重新部署到任一模式。
- Citrix 目前不支持基于 MacOs 和 Linux 的客户端。
- Citrix 不支持使用终结点上定义的显式 HTTP 代理。 

### <a name="calling-and-meetings"></a>通话和会议

- 与 Skype for business 的互操作性仅限于音频通话，无视频模态。
- 目前不支持双音频多频率（DTMF）与电话系统交互。
- 以匿名用户身份加入团队会议并非 AV 优化。 用户可以加入会议并具有非优化的体验。
- 会议或群组通话仅支持单个传入视频流。 当多人发送视频时，在任何给定时间仅显示主要演讲者的视频。  
- 传入和传出视频流分辨率仅限于720p 分辨率。 这是一个 WebRTC 限制。
- 仅支持来自传入相机或屏幕共享流的一个视频流。 当存在传入屏幕共享时，将显示该屏幕共享，而不是主扬声器的视频。
- 出站屏幕共享：
    - 不支持应用程序共享。
- 授予控制权并获得控制权：  
    - 在屏幕共享或应用程序共享会话期间不受支持。
    - 在 PowerPoint 共享会话期间受支持。  
- 不支持 CWA 上的高 DPI 缩放。

对于不与 VDI 无关的团队已知问题，请参阅[团队的已知问题](Known-issues.md)。

## <a name="troubleshooting"></a>疑难解答

#### <a name="troubleshoot-citrix-components"></a>Citrix 组件疑难解答

有关如何解决 VDA 和 CWA 问题的信息，请参阅[此 Citrix 网站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

## <a name="related-topics"></a>相关主题

- [使用 MSI 安装 Microsoft 团队](msi-deployment.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
