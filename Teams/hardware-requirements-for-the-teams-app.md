---
title: Microsoft Teams 的硬件要求
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
localization_priority: Normal
search.appverid: MET150
description: 本文介绍安装和运行 Microsoft Teams 所需的硬件要求。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c04820336cc992f7ec4e53a80d8eb8f7deb05622
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460622"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams 的硬件要求

以下各节中的所有要求对 Microsoft Teams 桌面版应用和 Teams 网页版应用均适用。

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Teams 在 Windows 电脑上的硬件要求

| 组件 | 要求 |
|---------|---------|
|计算机和处理器    | 最低 1.6 GHz (或更高) ，2 核<br><br>注意：对于 Intel 处理器，必须考虑使用 Intel Turbo Boost Technology (Max Turbo Frequency) 实现的最大速度         |
|内存     |    4.0 GB RAM     |
|硬盘    | 3.0 GB 可用磁盘空间        |
|显示器    |   1024 x 768 屏幕分辨率 |
|图形硬件 |  Windows OS：图形硬件加速需要 DirectX 9 或更高版本，对于 Windows 10 Fall Creators Update (或 WDDM 1.3 或更高版本，使用 WDDM 2.0 或更高版本) 
|操作系统  |    Windows 10、Windows 10 on ARM、Windows 8.1、Windows Server 2019、Windows Server 2016|
|.NET 版本    |  需要 .NET 4.5 CLR 或更高版本       |
|视频    |  USB 2.0 视频摄像头       |
|设备    |   标准笔记本电脑摄像头、麦克风和扬声器    |
|视频通话和会议|<ul><li>需要 2 核处理器。 对于更高的视频/屏幕共享分辨率和帧速率，建议使用 4 核处理器或更好的处理器。</li> <li>背景视频效果需要 Windows 10 或具有 AVX2 指令集的处理器。</li> <li>请参阅[硬件解码器和编码器驱动程序建议](hardware-decoders-and-encoders.md)，查看不受支持的解码器和编码器的列表。</li><li>在 Microsoft Teams 会议室使用邻近感应检测加入会议需要 Bluetooth LE，这需要在客户端设备上启用 Bluetooth，对于 Windows 客户端，还需要 64 位 Teams 客户端。 此功能在 32 位 Teams 客户端上不可用。</li></ul> |
|Teams 实时事件 | 如果要生成 Teams 实时事件，我们建议使用具有 Core i5 Kaby Lake 处理器、4.0-GB RAM (或更高版本) 和硬件编码器的计算机。 有关[不受支持解码器与](hardware-decoders-and-encoders.md)编码器的列表，请参阅硬件解码器与编码器驱动程序建议。 |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Teams 在 Mac 上的硬件要求

| 组件 | 要求 |
|---------|---------|
|计算机和处理器    | Intel Core Duo 处理器 |
|内存     |   4.0 GB RAM      |
|硬盘    |   1.5 GB 可用磁盘空间      |
|显示器    | 1280 x 800 或更高分辨率    |
|操作系统  |    macOS 的三个最新版本之一。 可在此处找到有关最新 macOS 版本以及如何升级 macOS 版本 [的信息](https://support.apple.com/en-us/HT201260)。 例如，发布新版本的 macOS 时，新版本及其前两个版本将成为受支持的版本。      |
|视频  |    兼容的网络摄像机     |
|语音    |  兼容的麦克风和扬声器、带麦克风的耳机或等效设备       |
|视频通话和会议 | <ul><li>需要 2 核处理器。 对于更高的视频/屏幕共享分辨率和帧速率，建议使用 4 核处理器或更好的处理器。 </li><li>在 microsoft Teams 会议室内使用邻近感应检测加入会议在 macOS 上不可用。</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Teams 在 Linux 上的硬件要求

| 组件 | 要求 |
|---------|---------|
|计算机和处理器    | 1.6 GHz (或)  (32 位或 64) 2 核        |
|内存     |    4.0 GB RAM     |
|硬盘    | 3.0 GB 可用磁盘空间        |
|显示器    |   1024 x 768 屏幕分辨率 |
|图形硬件 |  128 MB 图形内存
|操作系统  | Linux 发行版，支持安装 DEB 或 RPM。 |
|视频    |  USB 2.0 视频摄像头       |
|设备    |   标准笔记本电脑摄像头、麦克风和扬声器    |
|语音    |  兼容的麦克风和扬声器、带麦克风的耳机或等效设备       |
|视频通话和会议 | <ul><li>需要 2 核处理器。 对于更高的视频/屏幕共享分辨率和帧速率，建议使用 4 核处理器或更好的处理器。</li><li>使用近程检测在 Microsoft Teams 会议室中加入会议的功能在 Linux 上不可用。</li></ul>
|支持的 Linux 发行版 | Ubuntu 18.04 LTS、20.04 LTS、Fedora 30 工作站、RHEL 8 工作站、CentOS 8       |
|支持的桌面环境 | GNOME、KDE       |
|支持的显示服务器 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Teams 在移动设备上的硬件要求

可在以下移动平台上使用 Teams：

- Android：与 Android 手机和平板电脑兼容。

  支持仅限于 Android **的最后四** 个主要版本。 例如，当新的主要版本的 Android 发布时，Android 要求是新版本，以及它之前三个最新版本。

- iOS：与 iPhone、iPad 和 iPod touch 兼容。

  支持仅限于 iOS **的两** 个最新主要版本。 例如，当新的 iOS 主版本发布时，iOS 要求是新版本及其前面的最新版本。 iOS上的可选模糊我的背景视频效果需要一个与以下设备兼容的 iOS 12 或更高版本的操作系统：iPhone 7 或更高版本、iPad 2018 (第 6 代) 或更高版本，以及 iPod touch 2019 (第 7 代) 。

> [!Note]
> 为获得 Teams 的最佳体验，请使用最新版本的 iOS 和 Android。

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Teams 在虚拟桌面基础结构 (VDI) 环境中的硬件要求

请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)，了解在虚拟环境中运行 Teams 的要求。

### <a name="related-topics"></a>相关主题

- [获取 Teams 应用](get-clients.md)
- [移动设备上的 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [使用 MSI 安装 Microsoft Teams 应用](msi-deployment.md)
- [Microsoft Teams 的限制和规范](limits-specifications-teams.md)
