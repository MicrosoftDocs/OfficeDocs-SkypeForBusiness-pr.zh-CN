---
title: Microsoft Teams for Android 安全性
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
description: 了解如何保护适用于 Android 设备的 Microsoft Teams。
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532432"
---
# <a name="microsoft-teams-for-android-security"></a>Microsoft Teams for Android 安全性

本文不介绍 Microsoft Endpoint Manager 为专用设备模式配置的 Android 设备。 Teams Android 设备按设计在展台模式下运行。 有关 Android 展台的信息，请参阅 [Android Enterprise 专用设备注册](/mem/intune/enrollment/android-kiosk-enroll)。

Microsoft 与我们的 OEM 合作伙伴合作，提供设计安全且可自定义以满足客户需求的解决方案。 本文讨论 Teams Android 设备中的许多安全功能以及我们的方法。 为了便于导航，它拆分为四个关键部分。

> [!NOTE]
> Microsoft Teams Android 设备不应被视为典型的 Android 设备。 Teams Android 设备是专为与 Teams 及其各自用例一起使用而设计的专用设备。 本文仅适用于运行 Android 操作系统的认证和专用 Microsoft Teams 设备。 Teams 认证的设备只能从认证的 OEM 供应商处购买。 有关 Microsoft Teams 认证的 Android 设备的信息，请 [参阅 Microsoft Teams 认证的 Android 设备](/microsoftteams/devices/teams-ip-phones)。

有关 Windows 设备Teams 会议室的安全性的信息，请[参阅 windows 安全Microsoft Teams 会议室](security-windows.md)。

## <a name="software-security"></a>软件安全性

### <a name="android-kiosk-mode"></a>Android 展台模式

Teams Android 设备被锁定，仅通过在 Android 展台模式下运行设备来运行已批准的应用程序。 展台模式禁用对任何启动器功能的访问，并有助于保护设备的安全，以便在设备上启动授权应用程序。  

| 应用程序名称            | 应用程序说明                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android 应用 | Microsoft Teams 设备应用程序        |
| Microsoft Teams 管理员代理 | Teams 管理中心远程管理      |
| Intune 公司门户       | 设备注册、注册&登录 |
| OEM 合作伙伴代理           | OEM 合作伙伴代理&设备设置应用   |

根据设计，Microsoft Teams Android 应用将在 Android 展台模式下启动，并且不会向用户提供对操作系统的任何访问权限，也不会访问指定 Teams 用户体验之外的组件。

### <a name="application-code-signing"></a>应用程序代码签名

所有 Microsoft 和 OEM 应用程序都是代码签名的。 代码签名有助于验证在设备上运行的软件是否来自 Microsoft 和我们的硬件合作伙伴。 代码签名还尝试验证设备上运行的软件的完整性，以便只有正版软件才能启动和运行。  

### <a name="third-party-applications"></a>第三方应用程序

Teams 认证的设备没有设计安装 Google Play Store、Amazon App Store 或 Google Play Services。 这有助于确保第三方应用程序不能从存储安装到设备上。  

### <a name="android-debug-bridge"></a>Android 调试桥

在运行发布软件的所有 Teams Android 设备上，通过设计禁用 Android 调试网桥 (ADB) 。 ADB 是一种命令行工具，使管理员能够在基于 Android 的设备上执行函数，并启用应用安装、访问设备 shell 和其他管理员函数。  

### <a name="file-system-encryption"></a>文件系统加密

Teams Android 设备必须支持基于 Android 的加密，并且可以使用 Microsoft Endpoint Manager 合规性策略强制实施。 有关Endpoint Manager合规性策略的信息[，请使用Endpoint Manager符合性策略为使用Intune管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。

### <a name="android-os-version"></a>Android OS 版本

Teams Android 设备运行支持的 Android 版本。 Android 操作系统由 OEM 合作伙伴管理，合并到 Teams 认证固件，然后从 Teams 管理中心推送到设备。 有关在 Teams Android 设备上运行的 Android 版本的信息，请 [参阅 Microsoft Teams 认证的 Android 设备](/microsoftteams/devices/teams-ip-phones)。

### <a name="android-security-updates"></a>Android 安全更新

OEM 供应商作为固件更新过程的一部分，合并了适当的 Android 安全更新基线，以帮助确保基本操作系统保持安全。 定期更新设备对于确保设备上运行适当的 Android 安全更新非常重要。 有关详细信息，请参阅设备制造商。

### <a name="account-security"></a>帐户安全性

Teams Android 设备围绕两种类型的帐户构建，这些帐户能够成功运行设备。

- 本地设备管理员帐户

- 用户或资源帐户  

Teams Android 设备还与某些条件访问策略兼容，这些策略可用作设备登录的其他安全层。 有关最佳做法和支持的条件访问策略，请参阅 [支持的条件访问符合性策略](/microsoftteams/rooms/supported-ca-and-compliance-policies)。

### <a name="local-device-administrator-account"></a>本地设备管理员帐户

Teams Android 设备包括用于访问设备设置的管理帐户、安装的本地 Web 服务器以及任何特定于 OEM 的设置。

可以从设备制造商获取初始设备设置和配置项，例如此帐户的默认用户名和密码。

> [!CAUTION]
> 请务必尽快更改本地设备管理员密码。  

> [!TIP]
> Teams 管理中心可用于通过应用配置文件来更改已登录 Teams Android 设备的本地设备管理员密码。 我们建议在初始设备登录后使用此方法来保护 Android 设备的提升功能。 提升的功能可以包括设备设置和 Web 管理门户（如果受支持）。

### <a name="user-or-resource-account"></a>用户或资源帐户

Teams Android 设备需要使用用户或专用资源帐户登录到 Microsoft 365。 我们尝试以特定的方式保护这些帐户，具体取决于它是个人设备的正常用户帐户还是共享设备的资源帐户。 有关详细信息，请参阅 [创建和配置会议室和共享设备的资源帐户](/microsoftteams/rooms/with-office-365)。

### <a name="device-updates"></a>设备更新

Teams Android 设备配置为在可用时从 Teams 管理中心下载 Microsoft 认证的更新。 管理员可以自动推送或手动调用这些内容。 OEM 合作伙伴提供的第三方工具也可在需要时执行此函数。 Teams Android 设备可以在数小时后安装更新，以避免对用户造成影响。 下班后，可以在 Teams 管理中心配置计划，也可以使用 OEM 合作伙伴提供的第三方工具。

> [!IMPORTANT]
> Microsoft 建议通过 Teams 管理中心管理所有 Teams Android 设备的固件。

## <a name="network-security"></a>网络安全

Teams Android 设备具有与任何 Microsoft Teams 客户端相同的网络要求，包括通过防火墙和其他安全设备进行访问。 具体而言，作为 Teams **所需** 类别必须与下面列出的其他支持服务一起在防火墙上打开。 有关 Teams Android 设备所需的 IP 和 URL 的完整列表，请参阅：

- Microsoft Teams、Exchange Online、SharePoint Online、Microsoft 365 Common 和 Office Online [Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune[网络终结点Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Teams Android 设备使用大多数 802.1X 和其他基于网络的安全协议。 但是，我们无法针对所有网络安全配置测试 Teams Android 设备。 因此，如果出现可能跟踪到网络性能问题的性能问题，则可能需要在组织中配置这些协议或与 OEM 合作伙伴联系以获得帮助时禁用这些协议。

为了获得实时媒体的最佳性能，我们强烈建议将 Teams 媒体流量配置为绕过代理服务器和其他网络安全设备。 实时媒体对网络延迟很敏感，这可能导致代理服务器和其他网络安全设备。 网络延迟可能会显著降低用户的视频和音频质量。 有关详细信息，请参阅网络 [ (到云) - 一个架构师的观点](/microsoft-365/solutions/networking-design-principles) ，讨论网络建议，以提高媒体与 Microsoft Teams 的性能。

Teams Android 设备在 Internet 上使用加密的通信和终结点身份验证。 Teams Android 设备使用 TLS 1.2+。  

> [!IMPORTANT]
> Teams Android 设备不支持经过身份验证的代理服务器或租户限制。 请联系 OEM 合作伙伴获取代理支持信息。

Teams Android 设备不需要连接到内部 LAN。 考虑将 Teams Android 设备置于具有直接 Internet 访问权限的安全网络段中。 例如，Teams 电话可以部署在语音 VLAN 上。 如果内部 LAN 遭到入侵，则通过实现此网络隔离，对 Teams Android 设备的攻击向量机会将会减少。

强烈建议将 Teams Android 设备连接到有线网络。 使用无线网络需要仔细规划和评估，以获得最佳体验。

邻近加入、更好在一起、Teams 强制转换和 Teams 面板配对依赖于蓝牙。 Android 设备Teams 会议室上使用的蓝牙技术目前仅限于播发信标和提示的近似连接。 在 `ADV_NONCONN_INT` 广告信标中使用协议数据单元 (PDU) 类型。 此 PDU 类型适用于不可连接的设备，可将信息播发到侦听设备。 这些功能没有蓝牙设备配对。 有关蓝牙协议的其他详细信息，请参阅蓝牙 SIG 网站。

Teams 手机和显示器提供蓝牙配对功能，可使用蓝牙Hands-Free配置文件与耳机配对。

有关 Microsoft Teams 中安全性的详细信息，请参阅 [安全和 Microsoft Teams](/microsoftteams/teams-security-guide)。  
