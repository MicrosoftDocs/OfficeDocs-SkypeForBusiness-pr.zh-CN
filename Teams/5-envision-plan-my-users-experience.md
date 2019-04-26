---
title: 规划用户的 Microsoft Teams 体验
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 选择团队客户端应用程序，规划终结点质量，获取有关部署 Wi-fi 终结点和选择音频设备的建议。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: abef4c9e1096396d7844002ebda38a32876b403b
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304362"
---
# <a name="plan-my-users-experience"></a>规划我的用户体验

本文概述了正确标识直接影响用户体验的元素的云语音服务部署的要求。 为这些项目在部署之前做好准备，可以将增加成功提供高质量、 可靠地为用户体验的可能性。 

## <a name="client-deployment"></a>客户端部署

Microsoft 团队具有客户端适用于网站，桌面 （Windows 和 Mac） 和移动设备 （Android 和 iOS）。 有关如何安装 （Windows 和 Mac） 的桌面和移动客户端的其他详细信息，请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="client-updates"></a>客户端更新

一个团队的主要优点是，客户端保持最新自动。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

下图从中可以看出，如终结点是中为用户提供用户体验质量重要构建基块。

![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。](media/plan-my-users-experience-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。")

团队终结点可以在多个设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。 体验的一部分而不是只包括该设备，但用户如何连接到设备 — 例如，使用设备的内置的麦克风扬声器、 耳机或优化的耳麦。 使用优化耳机可以丰富整体用户体验。

以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。

## <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保所有 Pc 和您的组织中的其他设备可以运行团队。 这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。 许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。

有关团队的软件要求的信息 （web、 桌面和移动），每个平台上的客户端请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。
客户端防火墙会影响通话质量，以及阻止建立通话。 应根据 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)中的信息在客户端防火墙上配置适当的排除项。 你的第三方供应商会提供有关如何创建排除项的具体指导。

>[!NOTE]
> Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。

## <a name="wi-fi-recommendations-for-endpoints"></a>针对终结点的 Wi-Fi 建议

计重要规划部署优化的 Wi-fi 网络支持的 Microsoft 团队中的实时工作负荷。 以下各节提供了一些可帮助您规划终结点时应避免常见错误的一般指导。

### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

某些 Wi-fi 驱动程序可能会产生问题。 例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。
这不是很常见，但务必确保已更新和部署之前测试 PC 上的 Wi-fi 驱动程序。

### <a name="wi-fi-bands"></a>Wi-Fi 频带

当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。 如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。 在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。
此建议的前提是你已正确优化 5.0 GHz 网络频带。

### <a name="wi-fi-radio-type"></a>Wi-Fi 无线电类型

规划支持较新 Wi-Fi 无线电类型的设备 如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。

### <a name="wireless-avoidance"></a>避免使用无线

一些组织倾向于完全避免使用 Wi-Fi。 有时，此指导以建议用户直接连接有线网络来体现。 在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。 为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。

### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用无线访问点或不支持的 802.11 节能协议的路由器，您可能会遇到丢弃的呼叫或质量欠佳的呼叫质量在 Windows 设备上运行的 Microsoft 团队中。 如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>将您的组织中部署哪些团队客户端？</li><li>如何将您最初部署团队客户端到您的用户？</li><li>它们由谁来负责评估终结点和设备，以验证符合团队要求用户体验质量？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>记录将先部署团队客户端的过程。</li><li>评估终结点和设备，并执行和所需的补救措施。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>支持 Teams 的设备

Microsoft Teams 可以用于会议或用作电话系统。 在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。

使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。 通常情况下，这些设备不适合干扰取消，但任何类型的环境的噪音上可能具有下游影响其他人在调用。 利用针对这些情况优化的设备有助于确保获得高质量体验。

每个设备都需要满足用户的需求。 你需要为你组织中的不同角色和用例定制设备（例如耳机）。
应在规划流程中完成角色-设备映射操作。

选择了设备后，将其包含在试点测试计划中以便进行最终验证。 应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。

> [!NOTE]
> 目前，建议使用通过 Skype for Business 认证计划认证的音频设备。 若要查找此计划认证的设备，请参阅[USB 设备认证可用于 for Business 的 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>确定用户和会议室内体验的组织的总体设备策略。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>完成您的组织个人到设备映射练习。</li><li>文档获取用户的设备和会议室的过程。</li><li>文档的用户和会议室的部署和配置设备的过程。</li><li>获取初始设备开始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->