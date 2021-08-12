---
title: Microsoft Teams 会议室安全性
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解如何保护Microsoft Teams 会议室设备。
ms.openlocfilehash: 33ace09520f43804a6e6aa8cdd36a6016b195a650e821036f0caa2953e73f8ff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296659"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 会议室安全性

Microsoft 与合作伙伴合作，提供一种安全的解决方案，不需要采取其他操作来Microsoft Teams 会议室。 本文介绍本文中的许多安全功能Teams 会议室。

> [!NOTE]
> Microsoft Teams 会议室不应视为典型的最终用户工作站。 不仅用例差异很大，默认安全配置文件也大有不同。
> 本文适用于在 Microsoft Teams 会议室 上运行的设备Windows。

有限的最终用户数据存储在Teams 会议室。 最终用户数据存储在日志文件中，仅进行故障排除和支持。 会议与会者不能使用 Teams 会议室文件复制到硬盘驱动器或以自己方式登录。 最终用户数据不会传输到设备，也不得由Microsoft Teams 会议室访问。

即使最终用户无法将文件放在硬盘驱动器Teams 会议室，Microsoft Defender 仍然启用。 Teams 会议室 Microsoft Defender 测试性能。 禁用此功能或添加终结点安全软件可能会导致不可预测的结果和潜在的系统降级。

## <a name="hardware-security"></a>硬件安全性

在Teams 会议室环境中，有一个运行 Windows 10 IoT 企业版 版本的中央计算模块。 每个经过认证的计算模块都必须具有安全的装载解决方案、安全锁槽 (例如 Kensington lock) 和 I/O 端口访问安全措施，以防止未经授权的设备连接。 也可通过统一可扩展固件接口和 UEFI (禁用) 端口。

每个经过认证的计算模块都必须随默认启用 (TPM) 2.0 兼容技术一起提供。 TPM 用于加密资源帐户的Teams 会议室信息。

默认启用安全启动。 安全启动是电脑行业成员开发的安全标准，可帮助确保设备启动时仅使用原始设备制造商和 OEM (信任) 。 电脑启动时，固件会检查每个启动软件（包括 UEFI 固件驱动程序 (也称为选项 ROM) 、EFI 应用程序和操作系统）的签名。 如果签名有效，电脑将启动，并且固件将控制权授予操作系统。 有关详细信息，请参阅安全 [启动](/windows-hardware/design/device-experiences/oem-secure-boot)。

只能通过附加物理键盘和鼠标来访问 UEFI 设置。 这可以防止通过支持触摸的Teams 会议室以及连接到支持触摸的其他任何支持触摸的显示器访问 UEFI Teams 会议室。

内核直接内存 (DMA) 保护是在 Windows 10 上启用的一项Teams 会议室。 使用此功能，OS 和系统固件可保护系统免受所有支持 DMA 的设备的恶意和意外 DMA 攻击：

- 在启动过程中。

- 针对在 OS 运行时连接到易于访问的内部/外部 DMA 端口的设备（例如 M.2 PCIe 槽和 Thunderbolt 3）的恶意 DMA。

Teams 会议室启用受虚拟机监控程序保护的代码完整性 (HVCI) 。 HVCI 提供的功能之一是凭据防护。 凭据防护提供以下优势：

- **硬件安全性** NTLM、Kerberos 和凭据管理器利用平台安全功能（包括安全启动和虚拟化）来保护凭据。

- **基于虚拟化的安全Windows** NTLM 和 Kerberos 派生的凭据和其他机密在独立于正在运行的操作系统的受保护环境中运行。

- **更好地防范高级持久威胁** 使用基于虚拟化的安全性保护凭据管理器域凭据、NTLM 和 Kerberos 派生的凭据时，会阻止在许多目标攻击中使用的凭据窃取攻击技术和工具。 在具有管理权限的操作系统中运行的恶意软件无法提取受基于虚拟化的安全性保护的机密。

## <a name="software-security"></a>软件安全性

Microsoft Windows启动后，Teams 会议室自动登录名为 Windows 的本地 Skype。 Skype帐户没有密码。 若要确保Skype会话安全，请执行以下步骤。

> [!IMPORTANT]
> 请勿更改密码或编辑本地Skype用户帐户。 这样做可以防止Teams 会议室登录。

应用Microsoft Teams 会议室 1903 和更高版本中发现的"分配的访问"Windows 10运行。 分配的访问是应用程序中Windows 10一项功能，可限制向用户公开的应用程序入口点。 这就是启用单应用展台模式的方式。 使用 Shell Launcher，Teams 会议室配置为以用户界面Windows桌面应用程序的展台设备。 Microsoft Teams 会议室应用替换默认 shell (explorer.exe) 当用户登录时通常运行。 换言之，传统的资源管理器 shell 完全不启动。 这大大减少了Microsoft Teams 会议室漏洞面Windows。 有关详细信息，请参阅在桌面版 上配置展台[Windows数字签名](/windows/configuration/kiosk-methods)。

如果决定在 Teams 会议室 上运行安全扫描或 Internet 安全中心 (CIS) 基准测试，则扫描只能在本地管理员帐户的上下文中运行，因为 Skype 用户帐户不支持运行 Teams 会议室 应用外的应用程序。 应用到 Skype 用户上下文的许多安全功能不适用于其他本地用户，因此，这些安全扫描不会显示应用于 Skype 帐户的完整安全锁定。 因此，不建议在 Teams 会议室 上运行本地Teams 会议室。 但是，如果需要，可以运行外部渗透测试。 因此，建议针对设备运行外部渗透Teams 会议室，而不是运行本地扫描。

此外，还会应用锁定策略来限制使用非安全功能。 启用键盘筛选器可以拦截和阻止分配的访问策略未涵盖的潜在不安全键盘组合。 仅允许具有本地或域管理权限的用户登录Windows管理Teams 会议室。 在产品生命周期内，Windows这些Microsoft Teams 会议室在设备上应用的其他策略会持续进行评估和测试。

## <a name="account-security"></a>帐户安全性

Teams 会议室包括一个名为"Admin"的管理帐户，该帐户具有默认密码。 强烈建议在设置完成后尽快更改默认密码。

正确操作设备不需要管理员帐户，Teams 会议室重命名甚至删除。 但是，在删除管理员帐户之前，请确保设置配置的备用本地管理员帐户，然后再删除设备Teams 会议室帐户。 若要详细了解如何使用内置 Windows 工具或 PowerShell Windows本地帐户的密码，请参阅以下内容：

- [更改或重置Windows密码](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

还可以将域帐户导入本地域Windows管理员组。 可以使用 Intune 为 Azure AD 帐户执行此操作。 有关详细信息，请参阅策略[CSP – 受限组。](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> 如果在向另一个本地或域帐户授予本地管理员权限之前删除或禁用管理员帐户，则可能无法管理Teams 会议室设备。 如果发生这种情况，你需要将设备重置回其原始设置并再次完成设置过程。
>
> 不要向用户帐户授予本地管理员Skype权限。

Windows配置设计器可用于创建Windows 10包。 除了更改本地管理员密码，还可以执行更改计算机名称和注册到 Azure Active Directory。 有关创建配置设计器Windows包的信息，请参阅预配适用于[Windows 10 的包](/windows/configuration/provisioning-packages/provisioning-packages)。

需要为每个设备创建一个资源Teams 会议室，以便它可以登录到 Teams。 不能对此帐户使用双因素或多重身份验证。 要求第二个因素会阻止帐户在重新启动后自动登录到 Teams 会议室 应用。 但是，可以为此帐户启用新式身份验证，以提供额外的安全性。 此外，还可以为资源帐户部署基于位置的条件访问策略，以防止从未批准的位置登录帐户。 有关详细信息，请参阅在条件 [访问策略中使用位置条件](/azure/active-directory/conditional-access/location-condition)

如果可能，我们建议在 Azure AD 中创建资源帐户。 虽然同步的帐户可以在混合部署Teams 会议室，但这些同步的帐户通常很难登录Teams 会议室并且可能很难进行故障排除。 如果选择使用第三方联合身份验证服务对资源帐户的凭据进行身份验证，请确保第三方 IDP 使用设置为 的属性 `wsTrustResponse` 进行响应 `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>网络安全

通常，Teams 会议室客户端的网络要求Microsoft Teams相同。 对于其他客户端，通过防火墙和其他安全设备Teams 会议室访问Microsoft Teams相同。 特定于Teams 会议室，在防火墙上必须Teams"必需"类别。 Teams 会议室使用 Windows 管理设备Microsoft Store，Microsoft Intune (用户还需要Microsoft Intune更新、) 。 有关更新所需的 IP 和 URL 的完整Microsoft Teams 会议室，请参阅：

- **Microsoft Teams Office 365** [URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows更新配置** [WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store**[教育适用于企业的 Microsoft Store先决条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune**[网络网络Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

如果使用的托管Microsoft Teams 会议室组件Microsoft Teams 会议室 高级版，还需要确保Teams 会议室以下 URL：

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams 会议室配置为使用最新的更新（包括安全更新）Windows自行修补。 Teams 会议室使用预先设置的本地策略在每天凌晨 2：00 开始安装任何挂起的更新。 无需使用其他工具来部署和应用Windows更新。 使用其他工具来部署和应用更新可能会延迟Windows修补程序的安装，因而导致部署的安全性降低。 Teams 会议室应用是使用 Microsoft Store。 如果设备使用标准Microsoft Teams 会议室许可，则在夜间修补过程中会自动安装应用的任何新版本。 如果设备获得 microsoft 托管Microsoft Teams 会议室 高级版许可，并且已注册到 Microsoft 托管服务中，则Teams 会议室计划安装新版本的应用。

Teams 会议室设备使用大多数 802.1X 或其他基于网络的安全协议。 但是，无法针对所有可能的网络安全Teams 会议室测试安全配置。 因此，如果性能问题可以跟踪到网络性能问题，可能需要禁用这些协议（如果它们已在你的组织中配置）。

为获得实时媒体的最佳性能，我们强烈建议配置Teams绕过代理服务器和其他网络安全设备的媒体流量。 实时媒体对延迟非常敏感，代理服务器和网络安全设备可能会显著降低用户的视频和音频质量。 此外，Teams媒体已加密，因此通过代理服务器传递流量没有实际的好处。 有关详细信息，请参阅将 (连接到云[) —](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide)一位架构师的观点，其中讨论了使用 Microsoft Teams 和 Microsoft Teams 会议室 改进媒体性能的网络建议。

> [!IMPORTANT]
> Teams 会议室不支持经过身份验证的代理服务器。

Teams 会议室设备无需连接到内部 LAN。 考虑将Teams 会议室直接 Internet 访问的安全网络段中。 如果内部 LAN 遭到入侵，则针对 Teams 会议室攻击途径的机会将减少。

我们强烈建议将你的Teams 会议室连接到有线网络。 不建议或认证Teams 会议室使用无线网络。 某些连接功能（如 Wi-Fi Sense）在默认情况下处于禁用状态。

邻近联接和其他Teams 会议室功能依赖于蓝牙。 但是，蓝牙设备上Teams 会议室不允许外部设备连接到 Teams 会议室 设备。 蓝牙设备上使用Teams 会议室目前仅限于广告信号和提示的代理连接。 在 `ADV_NONCONN_INT` 广告信号 (使用) PDU 协议数据单元。 此 PDU 类型适用于向侦听设备发布信息的不可连接设备。 这些功能没有蓝牙设备配对。 有关 蓝牙 协议的其他详细信息，请参阅[蓝牙 SIG 网站](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
