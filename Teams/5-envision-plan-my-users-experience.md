---
title: 规划用户的 Microsoft Teams 体验
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择Teams客户端应用，规划终结点质量，获取有关在终结点Wi-Fi和选择音频设备的建议。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094730"
---
# <a name="plan-my-users-experience"></a>规划我的用户体验

本文概述了正确标识直接影响用户体验的云语音服务部署元素的要求。 在部署之前为这些项目做准备，可以增加成功为用户提供高质量、可靠的体验的机会。 

## <a name="client-deployment"></a>客户端部署

Microsoft Teams客户端可用于 Web、桌面 (Windows 和 Mac) ，以及 Android (和 iOS) 。 有关如何安装桌面客户端和 Mac (Windows和移动) 的其他详细信息，请参阅获取适用于 Microsoft Teams 的[客户端](./get-clients.md)。

## <a name="client-updates"></a>客户端更新

应用程序的主要优势Teams之一是客户端自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

如下图所示，终结点是为用户提供优质体验的重要构建基块。

![描述质量的三个要素的示意图](media/plan-my-users-experience-image1.png "描述质量的三个组件以及服务管理如何与这三个组件重叠的示意图。将焦点放在终结点上。")

Teams终结点可在许多设备上运行，包括电脑、Mac、平板电脑和移动设备。 部分体验不仅包括设备，还包括用户如何连接到设备，例如，使用设备的内置麦克风/扬声器、耳机或优化耳机。 使用优化耳机可以丰富整体用户体验。

以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。

## <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保组织内的所有电脑和其他设备都可以运行Teams。 这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。 许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。

有关 Web、桌面和移动Teams每个平台上Teams (客户端的软件要求) ，请参阅获取适用于[Microsoft Teams。](./get-clients.md)

## <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙会影响通话质量，以及阻止建立通话。 根据客户端防火墙中的信息配置相应的排除项，Microsoft 365 Office 365 [URL](/microsoft-365/enterprise/urls-and-ip-address-ranges)和 IP 地址范围。 你的第三方供应商会提供有关如何创建排除项的具体指导。

>[!NOTE]
> Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。

## <a name="wi-fi-recommendations-for-endpoints"></a>针对终结点的 Wi-Fi 建议

需要大量规划来部署优化Wi-Fi网络，以支持实时工作负荷Microsoft Teams。 以下部分提供了一些常规指南，可帮助你在规划终结点时避免常见错误。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

某些Wi-Fi驱动程序可能存在问题。 例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。
这不是常见情况，但必须确保在部署Wi-Fi更新和测试电脑上的驱动程序。

### <a name="wi-fi-bands"></a>Wi-Fi 频带

当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。 如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。 在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。
此建议的前提是你已正确优化 5.0 GHz 网络频带。

### <a name="wi-fi-radio-type"></a>Wi-Fi 无线电类型

规划支持较新 Wi-Fi 无线电类型的设备 如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。

### <a name="wireless-avoidance"></a>避免使用无线

一些组织倾向于完全避免使用 Wi-Fi。 有时，此指导以建议用户直接连接有线网络来体现。 在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。 为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。

### <a name="80211-power-save-protocol"></a>802.11 电源保存协议

如果你的组织使用不支持 802.11 Power Save 协议的无线接入点或路由器，你可能会在 Windows 设备上运行的 Microsoft Teams 中遇到呼叫中断或呼叫质量不佳的问题。 如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>组织中Teams哪些客户端？</li><li>最初如何向用户Teams客户端？</li><li>Who负责评估终结点和设备，以验证它们是否满足Teams体验的要求？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录部署客户端时要遵循Teams的过程。</li><li>评估终结点和设备，并执行所需的修正。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>支持 Teams 的设备

Microsoft Teams 可以用于会议或用作电话系统。 在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。

使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。 但通常情况下，这些设备未针对降噪进行优化，任何类型的环境噪音都可以对呼叫中的其他人造成下游影响。 利用针对这些情况优化的设备有助于确保获得高质量体验。

每个设备都需要满足用户的需求。 你需要为你组织中的不同角色和用例定制设备（例如耳机）。
应在规划流程中完成角色-设备映射操作。

选择了设备后，将其包含在试点测试计划中以便进行最终验证。 应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。

> [!NOTE]
> 目前，建议使用通过 Skype for Business 认证计划认证的音频设备。 若要查找通过此计划认证的设备，请参阅[Microsoft Teams设备和](https://products.office.com/microsoft-teams/across-devices/devices)USB[音频和视频设备](/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>决定组织针对用户和会议室体验的总体设备策略。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>为组织完成一个"从设备到设备"映射练习。</li><li>记录为用户和会议室获取设备的过程。</li><li>记录为用户和会议室部署和配置设备的过程。</li><li>购买初始设备以开始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->