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
ms.openlocfilehash: 044ff85a39058df85a1f132aaac08bb1d87c6c95
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438563"
---
# <a name="microsoft-teams-for-android-security"></a>Microsoft Teams for Android 安全性

本文不介绍 Microsoft Endpoint Manager 为专用设备模式配置的 Android 设备。 根据设计，Teams Android 设备在展台模式下运行。 有关 Android 展台的信息，请参阅 [Android Enterprise 专用设备注册](/mem/intune/enrollment/android-kiosk-enroll)。

Microsoft与我们的 OEM 合作伙伴合作，提供设计上安全且可自定义以满足客户需求的解决方案。 本文介绍 Teams Android 设备和方法中的许多安全功能。 为了便于导航，它分为四个关键部分。

> [!NOTE]
> Microsoft Teams Android 设备不应被视为典型的 Android 设备。 Teams Android 设备是专为 Teams 及其各自的用例而设计的专用设备。 本文仅适用于运行 Android 操作系统的认证和专用Microsoft Teams 设备。 Teams 认证设备只能从经过认证的 OEM 供应商购买。 有关Microsoft Teams 认证的 Android 设备的信息，请参阅 [Microsoft Teams 认证的 Android 设备](/microsoftteams/devices/teams-ip-phones)。

有关 Windows 设备上Teams 会议室安全性的信息，请参阅 [Windows 安全性Microsoft Teams 会议室](security-windows.md)。

## <a name="software-security"></a>软件安全性

### <a name="android-kiosk-mode"></a>Android 展台模式

通过在 Android 展台模式下运行设备，Teams Android 设备被锁定为仅运行已批准的应用程序。 展台模式禁止访问任何启动器功能，并有助于保护设备，以便授权应用程序在设备上启动。  

| 应用程序名称            | 应用程序说明                   |
|-----------------------------|-------------------------------------------|
| Microsoft Teams Android 应用 | Microsoft Teams 设备应用程序        |
| Microsoft Teams 管理员 代理 | Teams 管理中心远程管理      |
| Intune 公司门户       | 设备注册、注册&登录 |
| OEM 合作伙伴代理           | OEM 合作伙伴代理&设备设置应用   |

根据设计，Microsoft Teams Android 应用将在 Android 展台模式下启动，并且不会向用户提供对操作系统的任何访问权限或对指定 Teams 用户体验之外的组件的访问。

### <a name="application-code-signing"></a>应用程序代码签名

所有Microsoft和 OEM 应用程序都经过代码签名。 代码签名有助于验证设备上运行的软件是否是来自 Microsoft 和我们的硬件合作伙伴的正版。 代码签名还会尝试验证在设备上运行的软件的完整性，以便只有正版软件才能启动和运行。  

### <a name="third-party-applications"></a>第三方应用程序

Teams 认证设备没有按设计安装的 Google Play Store、Amazon App Store 或 Google Play Services。 这有助于确保无法将任何第三方应用程序从存储安装到设备上。  

### <a name="android-debug-bridge"></a>Android 调试桥

在运行发布软件的所有 Teams Android 设备上，设计禁用 android 调试桥 (ADB) 。 ADB 是一个命令行工具，使管理员能够在基于 Android 的设备上执行功能，并启用应用安装、访问设备 shell 和其他管理功能。  

### <a name="file-system-encryption"></a>文件系统加密

Teams Android 设备必须支持基于 Android 的加密，并且可以使用 Microsoft Endpoint Manager 合规性策略强制实施。 有关 Endpoint Manager 合规性策略的信息[，请使用 Endpoint Manager 合规性策略为使用 Intune 管理的设备设置规则](/mem/intune/protect/device-compliance-get-started)。

### <a name="android-os-version"></a>Android OS 版本

Teams Android 设备运行受支持的 Android 版本。 Android 操作系统由 OEM 合作伙伴管理，合并到 Teams 认证固件中，然后从 Teams 管理中心推送到设备。 有关在 Teams Android 设备上运行的 Android 版本的信息，请参阅 [Microsoft Teams 认证的 Android 设备](/microsoftteams/devices/teams-ip-phones)。

### <a name="android-security-updates"></a>Android 安全更新

OEM 供应商在固件更新过程中合并相应的 Android 安全更新基线，以帮助确保基本操作系统保持安全。 定期更新设备对于确保在设备上运行相应的 Android 安全更新非常重要。 有关详细信息，请参阅设备制造商。

### <a name="account-security"></a>帐户安全性

Teams Android 设备围绕两种类型的帐户构建，这些帐户可实现设备的成功运行。

- 本地设备管理员帐户

- 用户或资源帐户  

Teams Android 设备还与某些条件访问策略兼容，这些策略可用作设备登录的额外安全层。 有关最佳做法和支持的条件访问策略，请参阅 [支持的条件访问符合性策略](/microsoftteams/rooms/supported-ca-and-compliance-policies)。

### <a name="local-device-administrator-account"></a>本地设备管理员帐户

Teams Android 设备包括用于访问设备设置的管理帐户、本地 Web 服务器（如果已安装）以及任何特定于 OEM 的设置。

可以从设备制造商获取初始设备设置和配置项目，例如此帐户的默认用户名和密码。

> [!CAUTION]
> 请务必尽快更改本地设备管理员密码。  

> [!TIP]
> Teams 管理中心可用于通过应用配置文件来更改已登录 Teams Android 设备的本地设备管理员密码。 建议在初始设备登录后使用此方法，以保护 Android 设备的提升功能。 提升的功能可以包括设备设置和 Web 管理门户（如果受支持）。

### <a name="user-or-resource-account"></a>用户或资源帐户

Teams Android 设备需要使用用户或专用资源帐户登录 Microsoft 365。 我们尝试以特定方式保护这些帐户，具体取决于它是个人设备的普通用户帐户还是共享设备的资源帐户。 有关详细信息，请参阅 [为会议室和共享设备创建和配置资源帐户](/microsoftteams/rooms/with-office-365)。

### <a name="device-updates"></a>设备更新

Teams Android 设备配置为在 Teams 管理中心下载Microsoft认证的更新（当更新可用时）。 管理员可自动推送或手动调用这些内容。 如果需要，OEM 合作伙伴提供的第三方工具也可用于执行此功能。 Teams Android 设备可以在下班后安装更新，以避免对用户造成影响。 可以在 Teams 管理中心或使用 OEM 合作伙伴的第三方工具配置下班后计划。

> [!IMPORTANT]
> Microsoft建议通过 Teams 管理中心管理所有 Teams Android 设备的固件。

## <a name="network-security"></a>网络安全

Teams Android 设备具有与任何Microsoft Teams 客户端相同的网络要求，包括通过防火墙和其他安全设备进行访问。 具体而言，必须在防火墙上打开 Teams **所需的** 类别以及下面列出的其他支持服务。 有关 Teams Android 设备所需的 IP 和 URL 的完整列表，请参阅：

- Microsoft Teams、Exchange Online、SharePoint Online、Microsoft 365 Common 和 Office Online [Office 365 URL 和 IP 地址范围](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Microsoft Intune Microsoft Intune[网络终结点](/mem/intune/fundamentals/intune-endpoints)

Teams Android 设备适用于大多数 802.1X 和其他基于网络的安全协议。 但是，我们无法针对所有网络安全配置测试 Teams Android 设备。 因此，如果出现可跟踪到网络性能问题的性能问题，则可能需要禁用这些协议（如果在组织中配置了这些协议），或联系 OEM 合作伙伴寻求帮助。

为了获得实时媒体的最佳性能，强烈建议将 Teams 媒体流量配置为绕过代理服务器和其他网络安全设备。 实时媒体对网络延迟很敏感，网络延迟可能是由代理服务器和其他网络安全设备引起的。 网络延迟可能会显著降低用户的视频和音频质量。 有关详细信息，请参阅[网络 (到云) — 架构师的观点，](/microsoft-365/solutions/networking-design-principles)其中讨论了使用 Microsoft Teams 提高媒体性能的网络建议。

Teams Android 设备在 Internet 上使用加密通信和终结点身份验证。 Teams Android 设备使用 TLS 1.2+。  

> [!IMPORTANT]
> Teams Android 设备不支持经过身份验证的代理服务器或租户限制。 请联系 OEM 合作伙伴获取代理支持信息。

Teams Android 设备不需要连接到内部 LAN。 考虑将 Teams Android 设备置于具有直接 Internet 访问的安全网段中。 例如，Teams 电话可以部署在语音 VLAN 上。 如果内部 LAN 遭到入侵，则通过实施此网络隔离，将减少 Teams Android 设备的攻击途径机会。

强烈建议将 Teams Android 设备连接到有线网络。 无线网络的使用需要仔细规划和评估，以获得最佳体验。

邻近连接、更好的组合、Teams 强制转换和 Teams 面板配对依赖于蓝牙。 Android 设备上Teams 会议室上的蓝牙技术目前仅限于广告信标和提示的近端连接。  (`ADV_NONCONN_INT` PDU) 类型的协议数据单元用于广告信标。 此 PDU 类型适用于将信息播发到侦听设备的不可连接设备。 这些功能中没有蓝牙设备配对。 有关蓝牙协议的其他详细信息，请参阅蓝牙 SIG 网站。

Teams 电话和显示器提供蓝牙配对功能，以使用蓝牙Hands-Free配置文件与头戴显示设备配对。

有关 Microsoft Teams 中的安全性的详细信息，请参阅[安全和Microsoft Teams](/microsoftteams/teams-security-guide)。  
