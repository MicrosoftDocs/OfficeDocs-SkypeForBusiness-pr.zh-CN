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
description: 选择 "团队客户端应用"，规划终结点质量，获取有关部署 Wi-fi 终结点和选择音频设备的建议。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d156761d8ebc39822d6ccf2fc28ed6c380c4e117
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825180"
---
# <a name="plan-my-users-experience"></a>规划我的用户体验

本文概述了正确识别云语音服务部署中直接影响用户体验的元素的要求。 通过在部署之前准备这些项目，你将提高为用户成功提供优质、可靠体验的机会。 

## <a name="client-deployment"></a>客户端部署

Microsoft 团队拥有适用于 web、桌面（Windows 和 Mac）和移动设备（Android 和 iOS）的客户端。 有关如何安装桌面（Windows 和 Mac）和移动客户端的其他详细信息，请参阅[获取 Microsoft 团队客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="client-updates"></a>客户端更新

团队的一个主要好处是客户自动保持最新状态。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

正如您可以从下图中看到的，终结点是为用户提供质量体验的重要构建基块。

![描述三个质量组件的图表](media/plan-my-users-experience-image1.png "描述三种质量组件以及服务管理如何与所有三个组件重叠的图表。重点关注终结点。")

团队终结点可以在许多设备上运行，包括电脑、Mac、平板电脑和移动设备。 部分体验不仅包括设备，还包括用户如何连接到设备-例如，使用设备的内置麦克风/扬声器、earbuds 或优化的耳机。 使用优化耳机可以丰富整体用户体验。

以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。

## <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保组织中的所有 Pc 和其他设备都可以运行团队。 这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。 许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。

有关每个平台（web、桌面和移动版）上的团队客户端的软件要求的信息，请参阅[获取 Microsoft 团队客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙会影响通话质量，以及阻止建立通话。 应根据 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)中的信息在客户端防火墙上配置适当的排除项。 你的第三方供应商会提供有关如何创建排除项的具体指导。

>[!NOTE]
> Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。

## <a name="wi-fi-recommendations-for-endpoints"></a>针对终结点的 Wi-Fi 建议

部署已优化的 Wlan 网络以支持 Microsoft 团队中的实时工作负载，这一计划需要进行重大计划。 以下各部分提供了一些常规指南，可帮助你避免在规划终结点时遇到常见的缺陷。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

某些 Wi-fi 驱动程序可能会有问题。 例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。
这不是一种常见情况，但确保电脑上的 Wi-fi 驱动程序在部署之前已更新和测试非常重要。

### <a name="wi-fi-bands"></a>Wi-Fi 频带

当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。 如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。 在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。
此建议的前提是你已正确优化 5.0 GHz 网络频带。

### <a name="wi-fi-radio-type"></a>Wi-Fi 无线电类型

规划支持较新 Wi-Fi 无线电类型的设备 如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。

### <a name="wireless-avoidance"></a>避免使用无线

一些组织倾向于完全避免使用 Wi-Fi。 有时，此指导以建议用户直接连接有线网络来体现。 在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。 为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。

### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用不支持802.11 节能协议的无线访问点或路由器，则在 Windows 设备上运行的 Microsoft 团队中，可能会遇到呼叫中断或不好的通话质量。 如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>将在您的组织中部署哪些团队客户？</li><li>如何开始将团队客户端部署到你的用户？</li><li>谁负责评估终结点和设备以验证它们是否满足优质体验的团队要求？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录部署团队客户端所遵循的流程。</li><li>评估终结点和设备，并执行所需的执行和更正。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>支持 Teams 的设备

Microsoft Teams 可以用于会议或用作电话系统。 在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。

使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。 但通常情况下，这些设备不会针对噪声取消进行优化，并且任何类型的环境噪音都可能会对其他人在通话中产生下游影响。 利用针对这些情况优化的设备有助于确保获得高质量体验。

每个设备都需要满足用户的需求。 你需要为你组织中的不同角色和用例定制设备（例如耳机）。
应在规划流程中完成角色-设备映射操作。

选择了设备后，将其包含在试点测试计划中以便进行最终验证。 应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。

> [!NOTE]
> 目前，建议使用通过 Skype for Business 认证计划认证的音频设备。 若要查找此程序下认证的设备，请参阅[Microsoft 团队设备](https://products.office.com/en-us/microsoft-teams/across-devices/devices)和[USB 音频和视频设备](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定你的组织的整体设备策略以了解用户和会议室体验。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>为你的组织完成一个角色到设备的映射练习。</li><li>记录为用户和会议室获取设备的流程。</li><li>记录为用户和会议室部署和配置设备的流程。</li><li>购买初始设备以开始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
