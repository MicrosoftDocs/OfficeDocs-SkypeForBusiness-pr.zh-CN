---
title: 计划用户的 Microsoft 小组经验
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 选择团队客户端应用程序，用于终结点质量计划获取部署 Wi-Fi 终结点，然后选择音频设备的建议。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d15d000098a1970c7e3f471d6fec8be202f26ae
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="plan-my-users-experience"></a>计划我的用户体验

## <a name="client-deployment"></a>客户端部署

支持 Microsoft Teams 的客户端包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。 有关如何安装的桌面 （Windows 和 Mac） 和移动客户端的其他详细信息，请参阅[获取有关 Microsoft 小组的客户机](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="client-updates"></a>客户端更新

团队的主要优点之一是，客户端最新的自动保持。 在 PC 和 Mac 上的客户端使用一个后台进程，检查新生成并下载新的客户端，当应用程序处于空闲状态更新。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>终结点质量的计划

从下图可以看出，终结点都是在为用户提供品质体验的重要组成部分。

![描述的质量和服务管理与所有三个组件的重叠的三个组件的关系图。终结点为重点。](media/plan-my-users-experience-image1.png "描述的质量和服务管理与所有三个组件的重叠的三个组件的关系图。终结点为重点。")

团队的终结点可以在很多设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。 体验的一部分不仅涵盖了该设备，但如何在用户连接到设备 — — 例如，使用该设备的内置的麦克风扬声器、 耳机或优化的头戴式耳机。 使用优化的耳机可以丰富用户的总体体验。

终结点计划的以下指南将帮助您确保您的组织有经验的团队成功服务。

## <a name="endpoint-capability"></a>终结点功能

计划的第一部分是为了确保所有 Pc 和您的组织中的其他设备可以运行团队。 这涉及到不只看一看的硬件要求，但也知道电脑在后台干些什么。 许多组织运行的其他软件，包括入侵检测系统和反恶意软件，可能会影响设备的基本性能。

有关团队的软件要求的信息 （web、 桌面和移动），每个平台上的客户端请参阅[获取有关 Microsoft 小组的客户机](https://docs.microsoft.com/microsoftteams/get-clients)。

## <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验有很大的影响。
客户端防火墙可以影响以及防止在建立呼叫的呼叫质量。 在[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息基于客户端防火墙上配置相应的排除。 第三方供应商将对如何创建排除特定的指导。

>[!NOTE]
> Microsoft 的小组使用适当的防火墙配置中将自动更新 Windows 防火墙。

## <a name="wi-fi-recommendations-for-endpoints"></a>终结点的的 Wi-Fi 建议

它采用重大计划部署优化的 Wi-fi 网络，以在 Microsoft 小组支持实时的工作负载。 以下各节提供了可以帮助您避免常见缺陷，规划为终结点时某些一般性指导。

### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

一些 Wi-fi 驱动程序可能有问题。 例如，驱动程序可能必须接入点，从而导致较差的呼叫质量之间的极具挑战性漫游行为。
这不是很常见，但一定要确保已更新并在部署之前测试 Wi-fi 驱动程序在计算机上。

### <a name="wi-fi-bands"></a>Wi-Fi 带区

有两个主要类型的区段采用 Wi-fi 设备今天、 2.4 g h z 和 5.0 g h z。 如果您的组织提供了这两个区段，应配置驱动程序设置表示希望 5.0 g h z 频段。 该带是在吞吐量方面更高密度，更少受到干扰，在 2.4 GHz 频带中看到。
这一建议假定您已经正确地优化 5.0 g h z 网络带。

### <a name="wi-fi-radio-type"></a>Wi-fi 无线电类型

支持较新的 Wi-fi 无线电类型的设备的计划。 如果利用 802.11ac，可以获得很好的 Wi-fi 性能或更高版本在您配置的设备。

### <a name="wireless-avoidance"></a>无线回避

一些组织倾向于完全避免 Wi-fi。 有时本指南建议通过提供给用户直接连接到有线网络。 在某些情况下，网络绑定顺序可能具有首选的无线连接并继续使用该连接，即使将此电脑连接到有线连接。 若要避免此意外的现象，请配置绑定顺序，以避免这种情况。

### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用无线访问点或路由器不支持 802.11 节能协议，您可能会遇到通话中断或在 Windows 设备上运行的 Microsoft 小组在较差的呼叫质量。 如果不能升级您的无线访问点或路由器，则应更新设备上，使用电池电源运行 Windows 电源计划的设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指南。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>什么样的团队的客户端将在组织中部署？</li><li>如何将您最初部署团队客户端到您的用户？</li><li>它们由谁来负责评估终结点和设备，以验证符合品质体验团队要求？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>记录将遵循部署团队客户的过程。</li><li>终结点和设备评估和执行以及所需的补救措施。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>团队的的设备

会议或电话系统，则可以使用 Microsoft 小组。 在使用这些功能时的接口设备，用于团队将用户体验中起着重要作用。

使用内置的 PC 扬声器和麦克风听起来可接受该配置的用户。 但通常，这些设备不会干扰取消优化和任何类型的环境噪音会对下游的影响他人待命。 利用设备适合这些方案将有助于确保高质量的体验。

每个设备都需要以满足用户的需要。 您需要定制不同的角色如耳机的设备和您的组织中使用用例。
角色到设备的映射练习应作为规划过程的一部分来完成。

选择设备后，则将它们包括在最终验证的试验性测试计划。 在试验阶段，若要收集反馈信息以确保您的设备战略利用调查是最佳的。

> [!NOTE]
> 到目前为止，我们建议使用 Skype 业务认证计划通过认证的音频设备。 若要查找在此计划下认证的设备，请参阅[USB 设备认证，Skype 业务](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>确定您的组织的整体设备策略用户和会议空间体验。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>完成角色到设备的映射练习为您的组织。</li><li>文档获取用户的设备和会议室的过程。</li><li>记录用户和会议室的部署和配置设备的过程。</li><li>获得初始设备开始部署。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->