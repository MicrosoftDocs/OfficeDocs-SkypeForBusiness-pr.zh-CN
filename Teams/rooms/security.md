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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 了解如何保护Microsoft Teams 会议室设备。
ms.openlocfilehash: 4814bd5930bd311bf79fc749a1e736d1c3645165
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270047"
---
# <a name="microsoft-teams-rooms-security"></a>Microsoft Teams 会议室安全性

Microsoft 与我们的合作伙伴合作，提供安全且不需要其他操作来保护Microsoft Teams 会议室的解决方案。 本文讨论在Teams 会议室中找到的许多安全功能。

> [!NOTE]
> 不应将Microsoft Teams 会议室视为典型的最终用户工作站。 不仅用例大不相同，而且默认安全配置文件也大不相同。
> 本文适用于在 Windows 上运行的Microsoft Teams 会议室设备。

有限的最终用户数据存储在Teams 会议室上。 最终用户数据可能存储在日志文件中，以便进行故障排除和支持。 与会者不能使用Teams 会议室将文件复制到硬盘驱动器或以自己身份登录。 不会将最终用户数据传输到Microsoft Teams 会议室设备或可访问该设备。

尽管最终用户无法将文件放在Teams 会议室硬盘驱动器上，但 Microsoft Defender 仍处于启用状态。 Teams 会议室性能通过 Microsoft Defender 进行测试。 禁用此软件或添加终结点安全软件可能会导致不可预知的结果和潜在的系统降级。

## <a name="hardware-security"></a>硬件安全性

在Teams 会议室环境中，有一个运行Windows 10 IoT 企业版版本的中央计算模块。 每个经过认证的计算模块都必须有安全装载解决方案、安全锁槽 (例如肯辛顿锁) 和 I/O 端口访问安全措施，以防止连接未经授权的设备。 还可以通过统一可扩展固件接口 (UEFI) 配置禁用特定端口。

每个经过认证的计算模块都必须附带默认启用的受信任平台模块 (TPM) 2.0 兼容的技术。 TPM 用于加密Teams 会议室资源帐户的登录信息。

默认情况下启用安全启动。 安全启动是电脑行业成员开发的安全标准，可帮助确保设备启动仅使用原始设备制造商 (OEM) 信任的软件。 电脑启动时，固件会检查每个启动软件的签名，包括 UEFI 固件驱动程序 (也称为选项 ROM) 、EFI 应用程序和操作系统。 如果签名有效，电脑会启动，固件将控制操作系统。 有关详细信息，请参阅 [安全启动](/windows-hardware/design/device-experiences/oem-secure-boot)。

只能通过附加物理键盘和鼠标来访问 UEFI 设置。 这可防止通过启用Teams 会议室触摸的控制台以及附加到Teams 会议室的任何其他启用触摸的显示器访问 UEFI。

内核直接内存访问 (DMA) 保护是在Teams 会议室上启用的Windows 10设置。 使用此功能，OS 和系统固件可保护系统免受所有支持 DMA 的设备的恶意和意外 DMA 攻击：

- 在启动过程中。

- 在 OS 运行时，通过连接到易于访问的内部/外部支持 DMA 的端口（例如 M.2 PCIe 槽和 Thunderbolt 3）的设备来对抗恶意 DMA。

Teams 会议室还启用受虚拟机监控程序保护的代码完整性 (HVCI) 。 HVCI 提供的功能之一是 Credential Guard。 Credential Guard 提供以下优势：

- **硬件安全性** NTLM、Kerberos 和 Credential Manager 利用平台安全功能（包括安全启动和虚拟化）来保护凭据。

- **基于虚拟化的安全性** Windows NTLM 和 Kerberos 派生凭据和其他机密在与正在运行的操作系统隔离的受保护环境中运行。

- **更好地防范高级持久性威胁** 使用基于虚拟化的安全性保护凭据管理器域凭据、NTLM 和 Kerberos 派生凭据时，会阻止在许多目标攻击中使用的凭据盗窃攻击技术和工具。 在具有管理权限的操作系统中运行的恶意软件无法提取受基于虚拟化的安全保护的机密。

## <a name="software-security"></a>软件安全性

Microsoft Windows 启动后，Teams 会议室自动登录到名为 Skype 的本地 Windows 用户帐户。 Skype 帐户没有密码。 若要使 Skype 帐户会话安全，请执行以下步骤。

> [!IMPORTANT]
> 请勿更改密码或编辑本地 Skype 用户帐户。 这样做可以防止Teams 会议室自动登录。

Microsoft Teams 会议室应用使用在 Windows 10 1903 及更高版本中找到的分配访问功能运行。 分配的访问权限是Windows 10中的一项功能，它限制向用户公开的应用程序入口点。 这就是启用单应用展台模式的原因。 使用 Shell Launcher，Teams 会议室配置为将 Windows 桌面应用程序作为用户界面运行的展台设备。 Microsoft Teams 会议室应用将替换用户登录时通常运行的默认 shell (explorer.exe) 。 换句话说，传统的 Explorer shell 根本无法启动。 这大大减少了 Windows 中的Microsoft Teams 会议室漏洞面。 有关详细信息，请参阅 [在 Windows 桌面版上配置展台和数字标志](/windows/configuration/kiosk-methods)。

如果决定在Teams 会议室上运行安全扫描或 Internet 安全中心 (CIS) 基准，则扫描只能在本地管理员帐户的上下文下运行，因为 Skype 用户帐户不支持运行Teams 会议室应用以外的应用程序。 应用于 Skype 用户上下文的许多安全功能不适用于其他本地用户，因此，这些安全扫描不会显示应用于 Skype 帐户的完全安全锁定。 因此，不建议在Teams 会议室上运行本地扫描。 但是，如果需要，可以运行外部渗透测试。 因此，我们建议针对Teams 会议室设备运行外部渗透测试，而不是运行本地扫描。

此外，将应用锁定策略来限制非管理功能的使用。 已启用键盘筛选器来拦截和阻止分配的访问策略未涵盖的潜在不安全键盘组合。 仅允许具有本地或域管理权限的用户登录 Windows 以管理Teams 会议室。 在产品生命周期内，将持续评估和测试应用到Microsoft Teams 会议室设备上的 Windows 的这些策略和其他策略。

## <a name="account-security"></a>帐户安全性

Teams 会议室设备包含一个名为“管理员”的管理帐户，其中包含默认密码。 强烈建议在完成设置后尽快更改默认密码。

管理员帐户不是正确操作Teams 会议室设备所必需的，可以重命名甚至删除。 但是，在删除管理员帐户之前，请确保在删除附带Teams 会议室设备的帐户之前，先设置配置的备用本地管理员帐户。 有关如何使用内置 Windows 工具或 PowerShell 更改本地 Windows 帐户的密码的详细信息，请参阅以下内容：

- [更改或重置 Windows 密码](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

还可以将域帐户导入本地 Windows 管理员组。 可以使用Intune对 Azure AD 帐户执行此操作。 有关详细信息，请参阅[策略 CSP – RestrictedGroups。](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> 如果使用的是 Crestron 控制台，请务必在主机上和计算模块上更新管理员密码。 有关详细信息，请联系 Crestron。

> [!CAUTION]
> 如果在向其他本地或域帐户授予本地管理员权限之前删除或禁用管理员帐户，则可能会失去管理Teams 会议室设备的能力。 如果发生这种情况，则需要将设备重置回其原始设置，然后再次完成安装过程。

请勿向 Skype 用户帐户授予本地管理员权限。

Windows 配置设计器可用于创建Windows 10预配包。 除了更改本地管理员密码，还可以执行更改计算机名称和注册到 Azure Active Directory 等操作。 有关创建 Windows 配置设计器预配包的详细信息，请参阅[Windows 10的预配包](/windows/configuration/provisioning-packages/provisioning-packages)。

你需要为每个Teams 会议室设备创建一个资源帐户，以便它可以登录到 Teams。 不能将双因素或多重身份验证与此帐户配合使用。 需要第二个因素会阻止帐户在重新启动后自动登录到Teams 会议室应用。 但是，可以为此帐户启用新式身份验证，以获得额外的安全性。 此外，可以部署 Azure Active Directory 条件访问策略和Intune合规性策略来保护资源帐户的安全。 有关详细信息，请参阅[支持的条件访问和Intune设备符合性策略，以便Microsoft Teams 会议室](supported-ca-and-compliance-policies.md)和[条件访问，并Intune符合Microsoft Teams 会议室](conditional-access-and-compliance-for-devices.md)

如果可能，建议在 Azure AD 中创建资源帐户。 虽然同步的帐户可以在混合部署中使用Teams 会议室，但这些同步帐户通常难以登录到Teams 会议室，并且可能难以进行故障排除。 如果选择使用第三方联合身份验证服务对资源帐户的凭据进行身份验证，请确保第三方 IDP 响应的 `wsTrustResponse` 属性设置为 `urn:oasis:names:tc:SAML:1.0:assertion`。

## <a name="network-security"></a>网络安全

通常，Teams 会议室具有与任何 Microsoft Teams 客户端相同的网络要求。 通过防火墙和其他安全设备进行的访问与任何其他 Microsoft Teams 客户端的Teams 会议室相同。 特定于Teams 会议室，作为 Teams“必需”列出的类别必须在防火墙上打开。 如果使用Microsoft Intune管理设备) ，Teams 会议室还需要访问Windows 更新、Microsoft Store 和Microsoft Intune (。 有关Microsoft Teams 会议室所需的 IP 和 URL 的完整列表，请参阅：

- **Microsoft Teams** [Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows 更新**[配置 WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **适用于**[适用于企业的 Microsoft Store和教育的 Microsoft Store 先决条件](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune**[网络终结点Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

如果使用的是Microsoft Teams 会议室高级版Microsoft Teams 会议室托管服务组件，则还需要确保Teams 会议室可以访问以下 URL：

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

Teams 会议室配置为使用最新的 Windows 更新（包括安全更新）自动对其进行修补。 Teams 会议室使用预设置的本地策略从每天凌晨 2：00 开始安装任何挂起的更新。 无需使用其他工具来部署和应用 Windows 汇报。 使用其他工具来部署和应用更新可能会延迟 Windows 修补程序的安装，从而导致部署安全性降低。 Teams 会议室应用是使用 Microsoft Store 部署的。 如果设备已获得Microsoft Teams 会议室标准版许可，则在夜间修补过程中会自动安装应用的任何新版本。 如果设备已获得Microsoft Teams 会议室高级版许可并在 Microsoft 托管服务中注册，则根据定义的推出计划安装新版本的Teams 会议室应用。

Teams 会议室设备使用大多数 802.1X 或其他基于网络的安全协议。 但是，我们无法针对所有可能的网络安全配置测试Teams 会议室。 因此，如果出现可能跟踪到网络性能问题的性能问题，则可能需要在组织中配置这些协议时禁用这些协议。

为了获得实时媒体的最佳性能，我们强烈建议将 Teams 媒体流量配置为绕过代理服务器和其他网络安全设备。 实时媒体非常敏感延迟，代理服务器和网络安全设备可能会显著降低用户的视频和音频质量。 此外，由于 Teams 媒体已加密，因此通过代理服务器传递流量没有实际好处。 有关详细信息，请参阅网络[ (云) - 一个架构师的观点](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide)，讨论网络建议，以提高媒体与 Microsoft Teams 和Microsoft Teams 会议室的性能。

> [!IMPORTANT]
> Teams 会议室不支持经过身份验证的代理服务器。

Teams 会议室设备不需要连接到内部 LAN。 考虑将Teams 会议室置于具有直接 Internet 访问权限的安全网络段中。 如果内部 LAN 遭到入侵，则针对Teams 会议室的攻击向量机会将会减少。

强烈建议将Teams 会议室设备连接到有线网络。 不建议或认证在Teams 会议室设备上使用无线网络。 默认情况下，某些连接功能（如 Wi-Fi Sense）处于禁用状态。

邻近联接和其他Teams 会议室功能依赖于蓝牙。 但是，Teams 会议室设备上的蓝牙实现不允许与Teams 会议室设备建立外部设备连接。 蓝牙技术在Teams 会议室设备上的使用目前仅限于广告信标和提示的近似连接。 在 `ADV_NONCONN_INT` 广告信标中使用协议数据单元 (PDU) 类型。 此 PDU 类型适用于不可连接的设备，可将信息播发到侦听设备。 这些功能没有蓝牙设备配对。 有关蓝牙协议的其他详细信息，请参阅 [蓝牙 SIG 网站](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)。
