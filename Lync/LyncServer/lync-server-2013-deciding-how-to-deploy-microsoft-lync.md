---
title: Lync Server 2013：确定如何部署 Microsoft Lync
TOCTitle: 确定如何部署 Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204979(v=OCS.15)
ms:contentKeyID: 49313158
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确定如何部署 Lync Server 2013

 

_**上一次修改主题：** 2012-10-03_

在规划 Lync 时，首先要做的重要决策是如何部署 Microsoft Lync：本地部署为 Lync Server 2013，或在云中部署为带 Microsoft Office 365 的 Skype for Business Online。

  - **本地 Lync Server 2013：** 此选项不仅提供了完整的 Lync 功能集，还在配置、自定义和操作您的部署方面提供了最大的灵活性。所有服务器都是现场安装的，并且由您的组织进行维护。本地部署提供了整套 Lync Server 功能。

  - **云中的 Skype for Business Online** Skype for Business Online专为具有以下要求的组织而设计：在不牺牲 Lync Server 的业务级别功能的情况下实现基于云的即时消息、状态和会议的成本和灵活性优势。利用 Skype for Business Online， Microsoft 可部署和维护所需的服务器基础结构，还可处理持续维护、修补程序和升级。本地部署中可用的某些功能在 Skype for Business Online 中不可用。

最适合您的部署类型取决于您要部署的工作负载，以及您组织的地理位置和业务状态。

## Lync Server

本地 Lync Server 部署最适合以下方案：

  - **完整企业语音功能**   如果您计划部署完整企业语音解决方案以替换 PBX 或使用高级呼叫功能的 PBX，则需要本地 Lync Server 部署。本地部署支持与 PBX 系统和中继的直接连接以及高级电话功能（如响应组和呼叫寄存）。 Lync Online 当前不支持这些功能。

  - **媒体质量控制**   如果需要整套媒体质量保证功能（如呼叫允许控制 (CAC) 和服务质量 (QoS) 功能），您将需要本地部署。

  - **持久聊天**   如果您需要为组织部署持久聊天，则必须选择本地部署。

  - **第三方服务器应用程序**   仅本地部署可与使用 Microsoft 统一通信托管 API (UCMA) 的受信任的第三方应用程序结合使用。

  - **需要区域支持的跨国/跨地区公司**   如果您在多个国家或地区设立了数据中心并需要按地区部署和管理服务器，则本地部署将是您的最佳选择，因为它可提供此类区域管理功能。

  - **对策略、报告和升级进行完全控制**   利用本地 Lync Server 部署，您可以访问整套服务器和客户端策略、监控报告和其他报告以及升级计时。 Lync Online 不仅提供了一部分策略设置和报告，还提供了一个用于接受升级的重要的受限窗口。

## Lync Online

如果以上列表中的所有因素对您都不重要，您可能需要选择 Lync Online 来实现更简单的部署和管理。Lync Online 不仅提供了强大的 IM、状态和会议功能集，还使您组织中的各用户之间可通过 IP 进行音频和视频呼叫。

