---
title: Windows 安全Microsoft Teams 会议室
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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 了解如何在 Windows 设备上保护Microsoft Teams 会议室。
ms.openlocfilehash: f7774b43542885118bd66eb09cf1d30049b84425
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438459"
---
# <a name="microsoft-teams-rooms-on-windows-security"></a>Windows 安全Microsoft Teams 会议室

Microsoft与我们的合作伙伴合作，提供一个安全的解决方案，无需执行其他操作即可保护 Windows 上的Microsoft Teams 会议室。 本文介绍 Windows Teams 会议室 中的许多安全功能。

有关 Android 设备上Teams 会议室安全性的信息，请参阅 [Android 安全性Microsoft Teams 会议室](security-android.md)。

> [!NOTE]
> 不应将Microsoft Teams 会议室视为典型的最终用户工作站。 不仅用例大不相同，而且默认安全配置文件也大不相同。
> 本文适用于在 Windows 上运行Microsoft Teams 会议室设备。

有限的最终用户数据存储在Teams 会议室上。 最终用户数据可能存储在日志文件中，仅供故障排除和支持。 使用Teams 会议室会议与会者将文件复制到硬盘驱动器或以自己身份登录，这绝不可能。 最终用户数据不会传输到Microsoft Teams 会议室设备，也不会被Microsoft Teams 会议室设备访问。

即使最终用户无法将文件放在Teams 会议室硬盘驱动器上，Microsoft Defender仍已启用。 使用 Microsoft Defender 测试Teams 会议室性能。 禁用此或添加终结点安全软件可能会导致不可预知的结果和潜在的系统降级。

## <a name="hardware-security"></a>硬件安全性

在Teams 会议室环境中，有一个运行 Windows 10 IoT 企业版 版本的中央计算模块。 每个认证的计算模块都必须具有安全装载解决方案、安全锁槽 (例如 Kensington 锁) 和 I/O 端口访问安全措施，以防止未经授权的设备连接。 还可以通过统一可扩展固件接口 (UEFI) 配置禁用特定端口。

每个经过认证的计算模块都必须附带受信任的平台模块 (TPM) 默认启用的 2.0 兼容技术。 TPM 用于加密Teams 会议室资源帐户的登录信息。

默认情况下启用安全启动。 安全启动是电脑行业成员开发的一项安全标准，旨在帮助确保设备仅使用原始设备制造商 (OEM) 信任的软件启动。 电脑启动时，固件会检查每个启动软件的签名，包括 UEFI 固件驱动程序 (也称为选项 ROM) 、EFI 应用程序和操作系统。 如果签名有效，电脑将启动，固件将控制操作系统。 有关详细信息，请参阅 [安全启动](/windows-hardware/design/device-experiences/oem-secure-boot)。

只能通过附加物理键盘和鼠标来访问 UEFI 设置。 这可以防止通过Teams 会议室支持触摸的控制台以及附加到Teams 会议室的任何其他支持触摸的显示器访问 UEFI。

内核直接内存访问 (DMA) 保护是在Teams 会议室上启用的Windows 10设置。 使用此功能，OS 和系统固件可保护系统免受所有支持 DMA 的设备遭到恶意和意外的 DMA 攻击：

- 在启动过程中。

- 在 OS 运行时期间，通过连接到易于访问的内部/外部支持 DMA 的端口（例如 M.2 PCIe 插槽和 Thunderbolt 3）的设备，针对恶意 DMA。

Teams 会议室还 (HVCI) 启用受虚拟机监控程序保护的代码完整性。 HVCI 提供的功能之一是 Credential Guard。 Credential Guard 具有以下优势：

- **硬件安全性** NTLM、Kerberos 和凭据管理器利用平台安全功能（包括安全启动和虚拟化）来保护凭据。

- **基于虚拟化的安全性** Windows NTLM 和 Kerberos 派生凭据和其他机密在与正在运行的操作系统隔离的受保护环境中运行。

- **更好地防范高级持久性威胁** 使用基于虚拟化的安全性保护凭据管理器域凭据、NTLM 和 Kerberos 派生凭据时，会阻止许多目标攻击中使用的凭据盗窃攻击技术和工具。 在具有管理特权的操作系统中运行的恶意软件无法提取受基于虚拟化的安全性保护的机密。

## <a name="software-security"></a>软件安全性

Microsoft Windows 启动后，Teams 会议室自动登录到名为 Skype 的本地 Windows 用户帐户。 Skype 帐户没有密码。 若要确保 Skype 帐户会话安全，请执行以下步骤。

> [!IMPORTANT]
> 请勿更改密码或编辑本地 Skype 用户帐户。 这样做可以防止Teams 会议室自动登录。

Microsoft Teams 会议室应用使用 Windows 10 1903 及更高版本中的分配访问权限功能运行。 分配的访问权限是Windows 10中的一项功能，用于限制向用户公开的应用程序入口点。 这就是启用单应用展台模式的功能。 使用 Shell 启动器，Teams 会议室配置为作为用户界面运行 Windows 桌面应用程序的展台设备。 Microsoft Teams 会议室 应用将替换用户登录时通常运行的默认 shell (explorer.exe) 。 换句话说，传统的 Explorer shell 根本无法启动。 这大大降低了 Windows 中的Microsoft Teams 会议室漏洞面。 有关详细信息，请参阅 [在 Windows 桌面版上配置展台和数字签名](/windows/configuration/kiosk-methods)。

如果你决定在 Teams 会议室 上运行安全扫描或 Internet 安全中心 (CIS) 基准测试，则扫描只能在本地管理员帐户的上下文下运行，因为 Skype 用户帐户不支持运行 Teams 会议室 应用以外的应用程序。 应用于 Skype 用户上下文的许多安全功能不适用于其他本地用户，因此，这些安全扫描不会显示应用于 Skype 帐户的完整安全锁定。 因此，不建议在Teams 会议室上运行本地扫描。 但是，如果需要，可以运行外部渗透测试。 因此，建议对Teams 会议室设备运行外部渗透测试，而不是运行本地扫描。

此外，还应用锁定策略来限制使用非管理功能。 启用了键盘筛选器来截获和阻止分配的访问权限策略未涵盖的潜在不安全键盘组合。 仅允许具有本地或域管理权限的用户登录到 Windows 以管理Teams 会议室。 Microsoft Teams 会议室设备上应用于 Windows 的这些策略和其他策略在产品生命周期内不断进行评估和测试。

## <a name="account-security"></a>帐户安全性

Teams 会议室设备包括名为“管理员”的管理帐户，其中包含默认密码。 强烈建议在完成设置后尽快更改默认密码。

Teams 会议室设备的正确操作不需要管理员帐户，可以重命名甚至删除帐户。 但是，在删除 管理员 帐户之前，请确保在删除Teams 会议室设备附带的帐户之前设置配置的备用本地管理员帐户。 有关如何使用内置 Windows 工具或 PowerShell 更改本地 Windows 帐户的密码的详细信息，请参阅以下内容：

- [更改或重置 Windows 密码](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

还可以将域帐户导入本地 Windows 管理员组。 可以使用 Intune 为 Azure AD 帐户执行此操作。 有关详细信息，请参阅[策略 CSP – RestrictedGroups。](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> 如果使用 Crestron 控制台，请确保同时在控制台和计算模块上更新管理员密码。 有关详细信息，请联系 Crestron。

> [!CAUTION]
> 如果在向另一个本地或域帐户授予本地管理员权限之前删除或禁用管理员帐户，则可能无法管理Teams 会议室设备。 如果发生这种情况，你需要将设备重置回其原始设置，然后再次完成设置过程。

不要向 Skype 用户帐户授予本地管理员权限。

Windows 配置设计器可用于创建Windows 10预配包。 除了更改本地管理员密码，还可以执行更改计算机名称和注册 Azure Active Directory 等操作。 有关创建 Windows 配置设计器预配包的详细信息，请参阅[预配Windows 10的包](/windows/configuration/provisioning-packages/provisioning-packages)。

你需要为每个Teams 会议室设备创建一个资源帐户，以便它可以登录到 Teams。 不能对此帐户使用双因素或多重身份验证。 要求第二个因素会阻止帐户在重新启动后自动登录到 Teams 会议室 应用。 但是，可以为此帐户启用新式身份验证以增加安全性。 此外，还可以部署 Azure Active Directory 条件访问策略和Intune合规性策略来保护资源帐户。 有关详细信息，请参阅[Microsoft Teams 会议室支持的条件访问和Intune设备符合性策略](supported-ca-and-compliance-policies.md)和[Intune Microsoft Teams 会议室](conditional-access-and-compliance-for-devices.md)

建议在 Azure AD 中创建资源帐户（如果可能）。 虽然同步的帐户可以在混合部署中处理Teams 会议室，但这些同步的帐户通常难以登录到Teams 会议室并且可能难以进行故障排除。 如果选择使用第三方联合身份验证服务对资源帐户的凭据进行身份验证，请确保第三方 IDP 响应并将 `wsTrustResponse` 属性设置为 `urn:oasis:names:tc:SAML:1.0:assertion`。

## <a name="network-security"></a>网络安全

通常，Teams 会议室具有与任何Microsoft Teams 客户端相同的网络要求。 Teams 会议室通过防火墙和其他安全设备进行的访问与任何其他 Microsoft Teams 客户端相同。 特定于 Teams 会议室，必须在防火墙上打开 Teams 列为“必需”的类别。 如果使用Microsoft Intune) 管理设备，Teams 会议室还需要访问 Windows 更新、Microsoft Store 和 Microsoft Intune (。 有关Microsoft Teams 会议室所需的 IP 和 URL 的完整列表，请参阅：

- **Microsoft Teams** [Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows 更新**[配置 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft存储**[适用于企业的 Microsoft Store和教育先决条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** Microsoft Intune [的网络终结点](/mem/intune/fundamentals/intune-endpoints)

如果使用 Microsoft Teams 会议室专业版 的 Microsoft Teams 会议室 托管服务组件，还需要确保Teams 会议室可以访问以下 URL：

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Teams 会议室配置为使用最新的 Windows 更新（包括安全更新）自动修补自身。 Teams 会议室使用预先设置的本地策略从每天凌晨 2：00 开始安装任何挂起的更新。 无需使用其他工具来部署和应用 Windows 汇报。 使用其他工具来部署和应用更新可能会延迟 Windows 修补程序的安装，从而导致部署安全性降低。 Teams 会议室应用是使用 Microsoft 应用商店部署的。

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

Teams 会议室设备适用于大多数 802.1X 或其他基于网络的安全协议。 但是，我们无法针对所有可能的网络安全配置测试Teams 会议室。 因此，如果出现可跟踪到网络性能问题的性能问题，则可能需要在组织中配置这些协议时禁用这些协议。

为了获得实时媒体的最佳性能，强烈建议将 Teams 媒体流量配置为绕过代理服务器和其他网络安全设备。 实时媒体对延迟非常敏感，代理服务器和网络安全设备可能会显著降低用户的视频和音频质量。 此外，由于 Teams 媒体已加密，因此通过代理服务器传递流量没有实际好处。 有关详细信息，请参阅[网络 (到云) — 一个架构师的观点](/microsoft-365/solutions/networking-design-principles)，其中讨论了使用Microsoft Teams 和Microsoft Teams 会议室提高媒体性能的网络建议。

> [!IMPORTANT]
> Teams 会议室不支持经过身份验证的代理服务器。

Teams 会议室设备不需要连接到内部 LAN。 考虑将Teams 会议室置于具有直接 Internet 访问的安全网段中。 如果内部 LAN 遭到入侵，Teams 会议室的攻击向量将减少。

强烈建议将Teams 会议室设备连接到有线网络。 不建议在Teams 会议室设备上使用无线网络，也不进行认证。 默认情况下，某些连接功能（如Wi-Fi感知）处于禁用状态。

邻近联接和其他Teams 会议室功能依赖于蓝牙。 但是，Teams 会议室设备上的蓝牙实现不允许外部设备连接到Teams 会议室设备。 Teams 会议室设备上的蓝牙技术目前仅限于广告信标和提示的近端连接。  (`ADV_NONCONN_INT` PDU) 类型的协议数据单元用于广告信标。 此 PDU 类型适用于将信息播发到侦听设备的不可连接设备。 这些功能中没有蓝牙设备配对。 有关蓝牙协议的其他详细信息，请参阅 [蓝牙 SIG 网站](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
