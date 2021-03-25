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
description: 了解如何保护 Microsoft Teams 会议室设备。
ms.openlocfilehash: 77c7d71cfb41318b123fb262ee4a57b9aaeba493
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117390"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 会议室安全性

Microsoft 与合作伙伴合作，提供一种安全的解决方案，不需要执行其他操作来保护 Microsoft Teams 会议室。 本文介绍 Teams 会议室中的许多安全功能。

> [!NOTE]
> 不应将 Microsoft Teams 会议室视为典型的最终用户工作站。 不仅用例差异很大，默认安全配置文件也大有不同。

有限的最终用户数据存储在 Teams 会议室中。 最终用户数据存储在日志文件中，仅进行故障排除和支持。 使用 Teams 会议室参加会议的与会者不能将文件复制到硬盘驱动器或以自己方式登录。 不会向 Microsoft Teams 会议室设备传输或访问最终用户数据。

即使最终用户无法将文件放在 Teams 会议室硬盘上，Microsoft Defender 仍然启用。 Teams 会议室性能通过 Microsoft Defender 进行测试。 禁用此功能或添加终结点安全软件可能会导致不可预测的结果和潜在的系统降级。

## <a name="hardware-security"></a>硬件安全性

在 Teams 会议室环境中，有一个运行 Windows 10 IoT Enterprise 版本的中央计算模块。 每个经过认证的计算模块都必须具有安全的装载解决方案、安全锁槽 (例如 Kensington lock) 和 I/O 端口访问安全措施，以防止未经授权的设备连接。 也可通过统一可扩展固件接口和 UEFI (禁用) 端口。

每个经过认证的计算模块都必须随默认启用 (TPM) 2.0 兼容技术一起提供。 TPM 用于加密 Teams 会议室资源帐户的登录信息。

默认启用安全启动。 安全启动是电脑行业成员开发的安全标准，可帮助确保设备启动时仅使用原始设备制造商和 OEM (信任) 。 电脑启动时，固件会检查每个启动软件（包括 UEFI 固件驱动程序 (也称为选项 ROM) 、EFI 应用程序和操作系统）的签名。 如果签名有效，电脑将启动，并且固件将控制权授予操作系统。 有关详细信息，请参阅安全 [启动](/windows-hardware/design/device-experiences/oem-secure-boot)。

只能通过附加物理键盘和鼠标来访问 UEFI 设置。 这可以防止通过 Teams 会议室支持触摸的控制台以及附加到 Teams 会议室的其他任何支持触摸的显示器访问 UEFI。

DMA (DMA) 保护的内核直接内存访问是在 Teams 会议室中启用的 Windows 10 设置。 使用此功能，OS 和系统固件可保护系统免受所有支持 DMA 的设备的恶意和意外 DMA 攻击：

- 在启动过程中。

- 针对在 OS 运行时连接到易于访问的内部/外部 DMA 端口的设备（例如 M.2 PCIe 槽和 Thunderbolt 3）的恶意 DMA。

Teams 会议室还支持受虚拟机监控程序保护的代码完整性 (HVCI) 。 HVCI 提供的功能之一是凭据防护。 凭据防护提供以下优势：

- **硬件安全性** NTLM、Kerberos 和凭据管理器利用平台安全功能（包括安全启动和虚拟化）来保护凭据。

- **基于虚拟化的安全性** Windows NTLM 和 Kerberos 派生的凭据和其他机密在独立于正在运行的操作系统的受保护环境中运行。

- **更好地防范高级持久威胁** 使用基于虚拟化的安全性保护凭据管理器域凭据、NTLM 和 Kerberos 派生的凭据时，会阻止在许多目标攻击中使用的凭据窃取攻击技术和工具。 在具有管理权限的操作系统中运行的恶意软件无法提取受基于虚拟化的安全性保护的机密。

## <a name="software-security"></a>软件安全性

Microsoft Windows 启动后，Teams 会议室会自动登录名为 Skype 的本地 Windows 用户帐户。 Skype 帐户没有密码。 若要确保 Skype 帐户会话安全，请执行以下步骤。

> [!IMPORTANT]
> 请勿更改密码或编辑本地 Skype 用户帐户。 这样做可以防止 Teams 会议室自动登录。

Microsoft Teams 会议室应用使用 Windows 10 1903 和更高版本中的"已分配访问权限"功能运行。 分配的访问是 Windows 10 中的一项功能，可限制向用户公开的应用程序入口点。 这就是启用单应用展台模式的方式。 使用 Shell 启动器，Teams 会议室配置为以用户界面方式运行 Windows 桌面应用程序的展台设备。 Microsoft Teams 会议室应用替换默认 shell (explorer.exe) 当用户登录时通常运行。 换言之，传统的资源管理器 shell 完全不启动。 这大大减少了 Windows 中的 Microsoft Teams 会议室漏洞面。 有关详细信息，请参阅在 Windows 桌面版上配置网亭 [和数字签名](/windows/configuration/kiosk-methods)。

如果你决定在 Teams 会议室上运行安全扫描或 Internet 安全中心 (CIS) 基准测试，则扫描只能在本地管理员帐户的上下文中运行，因为 Skype 用户帐户不支持运行 Teams 会议室应用外的应用程序。 应用到 Skype 用户上下文的许多安全功能不适用于其他本地用户，因此，这些安全扫描不会显示应用于 Skype 帐户的完整安全锁定。 因此，不建议在 Teams 会议室中运行本地扫描。 但是，如果需要，可以运行外部渗透测试。 因此，建议针对 Teams 会议室设备运行外部渗透测试，而不是运行本地扫描。

此外，还会应用锁定策略来限制使用非安全功能。 启用键盘筛选器可以拦截和阻止分配的访问策略未涵盖的潜在不安全键盘组合。 仅允许具有本地或域管理权限的用户登录到 Windows 以管理 Teams 会议室。 在产品生命周期内，Microsoft Teams 会议室设备上应用的这些策略和其他策略将持续进行评估和测试。

## <a name="account-security"></a>帐户安全性

Teams 会议室设备包括一个名为"Admin"的管理帐户，该帐户具有默认密码。 强烈建议在设置完成后尽快更改默认密码。

正确操作 Teams 会议室设备不需要管理员帐户，可重命名甚至删除。 但是，在删除管理员帐户之前，请确保设置配置的备用本地管理员帐户，然后再删除 Teams 会议室设备附带的帐户。 若要详细了解如何使用内置 Windows 工具或 PowerShell 更改本地 Windows 帐户的密码，请参阅以下内容：

- [更改或重置 Windows 密码](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

还可以将域帐户导入本地 Windows 管理员组。 可以使用 Intune 为 Azure AD 帐户执行此操作。 有关详细信息，请参阅策略[CSP – 受限组。](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> 如果在向另一个本地或域帐户授予本地管理员权限之前删除或禁用管理员帐户，则可能无法管理 Teams 会议室设备。 如果发生这种情况，你需要将设备重置回其原始设置并再次完成设置过程。
>
> 不要向 Skype 用户帐户授予本地管理员权限。

Windows 配置设计器可用于创建 Windows 10 预配包。 除了更改本地管理员密码，还可以执行更改计算机名称和注册到 Azure Active Directory 等操作。 有关创建 Windows 配置设计器预配包的信息，请参阅适用于 [Windows 10](/windows/configuration/provisioning-packages/provisioning-packages)的预配包。

你需要为每个 Teams 会议室设备创建一个资源帐户，以便它可以登录到 Teams。 不能对此帐户使用双因素或多重身份验证。 要求第二个因素会阻止帐户在重新启动后自动登录到 Teams 会议室应用。 但是，可以为此帐户启用新式身份验证，以提供额外的安全性。 此外，还可以为资源帐户部署基于位置的条件访问策略，以防止从未批准的位置登录帐户。 有关详细信息，请参阅在条件 [访问策略中使用位置条件](/azure/active-directory/conditional-access/location-condition)

如果可能，我们建议在 Azure AD 中创建资源帐户。 虽然同步的帐户可以在混合部署中与 Teams 会议室一起工作，但这些同步的帐户通常难以登录 Teams 会议室，并且可能很难进行故障排除。 如果选择使用第三方联合身份验证服务对资源帐户的凭据进行身份验证，请确保第三方 IDP 使用设置为 的属性 `wsTrustResponse` 进行响应 `urn:oasis:names:tc:SAML:1.0:assertion` 。

## <a name="network-security"></a>网络安全

通常，Teams 会议室的网络要求与任何 Microsoft Teams 客户端相同。 对于 Teams 会议室，通过防火墙和其他安全设备访问的方式与其他任何 Microsoft Teams 客户端相同。 特定于 Teams 聊天室，Teams 列为"必需"的类别必须在防火墙上打开。 如果使用 Microsoft In) tune 管理设备，Teams 会议室还需要访问 Windows 更新、Microsoft Store 和 Microsoft Intune (。 有关 Microsoft Teams 会议室所需的 IP 和 URL 的完整列表，请参阅：

- **Microsoft Teams** [Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows 更新**[配置 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **适用于商业**[和教育的 Microsoft Store 先决条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints for Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

如果使用 Microsoft Teams 会议室高级版 Microsoft Teams 会议室托管服务组件，还需要确保 Teams 会议室可以访问以下 URL：

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

Teams 会议室配置为自动使用最新的 Windows 更新（包括安全更新）进行修补。 Teams 会议室使用预先设置的本地策略在每天凌晨 2：00 开始安装任何挂起的更新。 无需使用其他工具来部署和应用 Windows 更新。 使用其他工具来部署和应用更新可能会延迟 Windows 修补程序的安装，因而导致部署的安全性降低。 Teams 会议室应用是使用 Microsoft Store 部署的。 如果你的设备获得 Microsoft Teams 会议室标准版的许可，则在夜间修补过程中会自动安装该应用的任何新版本。 如果设备已获得 Microsoft Teams 会议室高级版的许可，并且已注册到 Microsoft 托管服务，则根据定义的推出计划安装新版本的 Teams 会议室应用。

Teams 会议室设备支持大多数 802.1X 或其他基于网络的安全协议。 但是，无法针对所有可能的网络安全配置测试 Teams 会议室。 因此，如果性能问题可以跟踪到网络性能问题，可能需要禁用这些协议（如果它们已在你的组织中配置）。

为获得实时媒体的最佳性能，我们强烈建议将 Teams 媒体流量配置为绕过代理服务器和其他网络安全设备。 实时媒体对延迟非常敏感，代理服务器和网络安全设备可能会显著降低用户的视频和音频质量。 此外，由于 Teams 媒体已加密，因此通过代理服务器传递流量没有实际的好处。 有关详细信息，请参阅将 (连接到云 [) -](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) 一位架构师的观点，其中讨论了使用 Microsoft Teams 和 Microsoft Teams 会议室提高媒体性能的网络建议。

> [!IMPORTANT]
> Teams 会议室不支持经过身份验证的代理服务器。

Teams 会议室设备无需连接到内部 LAN。 考虑将 Teams 会议室放置在具有直接 Internet 访问的安全网络段中。 如果内部 LAN 遭到入侵，则针对 Teams 会议室的攻击途径机会将减少。

强烈建议将 Teams 会议室设备连接到有线网络。 不建议或认证在 Teams 会议室设备上使用无线网络。 某些连接功能（如 Wi-Fi Sense）在默认情况下处于禁用状态。

邻近联接和其他 Teams 会议室功能依赖于Bluetooth。 但是，Bluetooth Teams 会议室设备实现不允许外部设备连接到 Teams 会议室设备。 Bluetooth Teams 会议室设备上使用的技术目前仅限于广告信号和提示的代理连接。 在 `ADV_NONCONN_INT` 广告信号 (使用) PDU 协议数据单元。 此 PDU 类型适用于向侦听设备发布信息的不可连接设备。 这些功能没有Bluetooth设备配对。 有关 Bluetooth 协议的其他详细信息，请参阅 [Bluetooth SIG 网站](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。