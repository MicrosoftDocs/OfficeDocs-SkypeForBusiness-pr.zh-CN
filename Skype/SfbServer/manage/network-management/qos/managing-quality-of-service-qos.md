---
title: 管理服务质量 (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 服务质量 (QoS) 是一种网络技术，某些组织中使用的音频和视频通信提供最佳的最终用户体验帮助。
ms.openlocfilehash: e8d5cf9da3be6537d4531683cfbbb9e437b66b77
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891144"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>管理服务质量 (QoS Skype 中) 的业务服务器


服务质量 (QoS) 是一种网络技术，某些组织中使用的音频和视频通信提供最佳的最终用户体验帮助。 QoS 最常网络上都使用其中带宽受到限制： 大量争夺相对较小的可用带宽量的网络数据包，通过服务质量提供了一种管理员能够为数据包分配更高优先级的方法执行音频或视频数据。 通过授予这些数据包更高的优先级，几乎完成得更快和较少中断，比涉及等文件传输、 web 浏览，或数据库进行备份的网络会话的音频和视频通信。 这是因为用于文件传输或数据库进行备份的网络数据包分配了"最大努力"的优先级。


> [!NOTE]  
> 一般来说，服务质量仅适用于内部网络上通信会话。 当实现 QoS 时，配置您的服务器和传送器以支持数据包标记;但是，您可以配置这些设备以支持数据包标记以特定方式。 不能假定在 Internet 上或其他网络上，将支持的服务质量。 即使质量如果服务支持其他网络，则不能保证 QoS 将配置网络上配置服务的方式相同。

Skype 业务服务器不需要的服务质量;如果您当前未使用 QoS，没有为业务服务器安装 Skype 之前安装服务任何要求。 如果您遇到的大量数据包丢失网络解决此问题的建议方式是将添加额外带宽。 如果不能添加更多的带宽，您可能希望改为实现服务质量。

Skype 业务服务器提供完全支持的服务质量:，意味着已在使用 QoS 的组织可以轻松地集成 Skype 业务服务器其现有的网络基础结构。 才能执行此操作，您必须执行以下任务：

  - [的未基于 Windows 的设备启用 QoS](enabling-qos-for-devices-that-are-not-based-on-windows.md)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 尽管可以使用 Skype 业务服务器启用和禁用的服务质量的设备，您通常不能使用该产品可修改使用这些设备的 DSCP 代码。

  - [配置端口范围和会议、 应用程序和中介服务器的服务质量策略](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 与 Skype 的业务服务器执行不启用或禁用服务质量，说，设置的属性值为 True 或 False。 而是您通过配置端口范围然后创建并应用组策略启用服务质量。 如果稍后决定不想用 QoS 您可以"禁用"的服务质量即可删除相应的组策略对象。

  - [配置端口范围和边缘服务器的服务质量策略](configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。 边缘服务器的内部端只应完成配置服务质量策略。 这是因为 Quality of Service 旨在用于在内部网络，不在 Internet 上。

- [配置端口范围和客户端中的业务服务器 Skype 的服务质量策略](configuring-port-ranges-for-your-skype-clients.md) 这些端口范围只能应用于客户端计算机和通常不同于您的服务器上配置的端口范围。 请注意，Skype 业务服务器不支持 Windows 10 之外的 QoS 的 Windows 操作系统。


