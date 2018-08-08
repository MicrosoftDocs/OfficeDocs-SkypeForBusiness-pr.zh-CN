---
title: 规划用户体验的 Microsoft 团队
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 选择团队客户端应用程序，规划终结点质量，获取有关部署 Wi-fi 终结点和选择音频设备的建议。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e328f591ac97ace73b2cd2bb45aab61db75f064
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695347"
---
# <a name="plan-my-users-experience"></a>规划我的用户体验

本文概述了正确标识直接影响用户体验的元素的云语音服务部署的要求。 为这些项目在部署之前做好准备，可以将增加成功提供高质量、 可靠地为用户体验的可能性。 

## <a name="client-deployment"></a>客户端部署

支持 Microsoft Teams 的客户端包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。 有关如何安装 （Windows 和 Mac） 的桌面和移动客户端的其他详细信息，请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="client-updates"></a>客户端更新

一个团队的主要优点是，客户端保持最新自动。 PC 和 Mac 客户端是通过使用背景过程，为新的生成检查并下载新客户端应用程序空闲时进行了更新。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

下图从中可以看出，如终结点是中为用户提供用户体验质量重要构建基块。

![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。](media/plan-my-users-experience-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有终结点上焦点。")

团队终结点可以在多个设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。 体验的一部分而不是只包括该设备，但用户如何连接到设备 — 例如，使用设备的内置的麦克风扬声器、 耳机或优化的耳麦。 使用优化的耳麦可以丰富的整体用户体验。

终结点规划以下指南将帮助您确保您的组织具有与团队体验成功入职培训。

## <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保所有 Pc 和您的组织中的其他设备可以运行团队。 此步骤需要而不仅仅看硬件要求，但也了解 PC 在后台执行什么操作。 许多组织运行其他软件，包括入侵检测系统和反恶意软件，这可能会影响设备的基本的性能。

有关团队的软件要求的信息 （web、 桌面和移动），每个平台上的客户端请参阅[获取 Microsoft 团队的客户端](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验产生重大影响。
客户端防火墙可能会影响除了阻止的建立呼叫的呼叫质量。 基于[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息客户端防火墙上配置了适当的排除项。 您的第三方供应商将对如何创建排除的特定指南。

>[!NOTE]
> Microsoft 团队将具有适当的防火墙配置自动更新 Windows 防火墙。

## <a name="wi-fi-recommendations-for-endpoints"></a>终结点的 Wi-fi 建议

计重要规划部署优化的 Wi-fi 网络支持的 Microsoft 团队中的实时工作负荷。 以下各节提供了一些可帮助您规划终结点时应避免常见错误的一般指导。

### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

某些 Wi-fi 驱动程序可能会产生问题。 例如，驱动程序可能必须访问点，导致质量欠佳的呼叫质量之间积极漫游行为。
这不是很常见，但务必确保已更新和部署之前测试 PC 上的 Wi-fi 驱动程序。

### <a name="wi-fi-bands"></a>Wi-fi 带区

有两个主要类型的用于 Wi-fi 设备今天、 2.4 GHz 和 5.0 GHz 的分隔条。 如果您的组织提供了两个带区，应配置首选 5.0 GHz 带您驱动程序设置。 此带是得多方面吞吐量高密度和小于受干扰 2.4 GHz 带中所示。
此建议假定您已正确优化 5.0 GHz 网络带。

### <a name="wi-fi-radio-type"></a>Wi-fi 单选类型

规划支持较新 Wi-fi 单选类型的设备。 如果您利用 802.11ac，您可以获取很好的 Wi-fi 性能或更高版本上设置的设备。

### <a name="wireless-avoidance"></a>无线避免

某些组织希望完全避免 Wi-fi。 有时本指南建议通过提供给用户直接连接到有线网络。 在某些情况下，网络绑定顺序可能具有首选的无线连接，并且可以继续使用该连接，即使 PC 连接到有线连接。 若要避免此意外的行为，请配置绑定为了避免这种情况。

### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用无线访问点或不支持的 802.11 节能协议的路由器，您可能会遇到丢弃的呼叫或质量欠佳的呼叫质量在 Windows 设备上运行的 Microsoft 团队中。 如果不能升级您的无线访问点或传送器，您应更新 Windows 电源计划运行电池供电的设备上的设置。 在下列[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)提供了进一步的详细信息和配置指导。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>将您的组织中部署哪些团队客户端？</li><li>如何将您最初部署团队客户端到您的用户？</li><li>它们由谁来负责评估终结点和设备，以验证符合团队要求用户体验质量？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>记录将先部署团队客户端的过程。</li><li>评估终结点和设备，并执行和所需的补救措施。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>团队的设备

为会议或作为电话系统，则可以使用 Microsoft 团队。 时使用这些功能，用于团队接口设备中的用户体验起着重要作用。

使用内置的 PC 扬声器和麦克风听起来到已配置的用户可接受。 通常情况下，这些设备不适合干扰取消，但任何类型的环境的噪音上可能具有下游影响其他人在调用。 利用设备优化的这些方案将有助于确保高质量体验。

每个设备需要满足您的用户。 您需要定制的不同角色如耳机设备和您的组织中使用案例。
个人到设备映射练习应完成规划过程的一部分。

选择设备后，请将它们包括在最终验证试点测试计划。 利用调查在试验阶段，收集反馈，以确保您的设备策略是最佳。

> [!NOTE]
> 此时，我们建议使用已通过 Skype 业务认证计划认证的音频设备。 若要查找此计划认证的设备，请参阅[USB 设备认证可用于 for Business 的 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定用户和会议室内体验的组织的总体设备策略。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>完成您的组织个人到设备映射练习。</li><li>文档获取用户的设备和会议室的过程。</li><li>文档的用户和会议室的部署和配置设备的过程。</li><li>获取初始设备开始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->