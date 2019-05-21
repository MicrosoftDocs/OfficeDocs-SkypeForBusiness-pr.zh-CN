---
title: 管理服务质量 (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 服务质量 (QoS) 是在某些组织中使用的网络技术, 可帮助为音频和视频通信提供最佳的最终用户体验。
ms.openlocfilehash: fbc10c5e94706348b7e3f66687b4868a9feb44ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279401"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理服务质量 (QoS)


服务质量 (QoS) 是在某些组织中使用的网络技术, 可帮助为音频和视频通信提供最佳的最终用户体验。 QoS 最常用于带宽受限的网络: 有大量的网络数据包 (这些数据包的可用带宽相对较少), 服务质量为管理员提供了一种为数据包分配更高优先级的方式。携带音频或视频数据。 通过为这些数据包提供更高优先级, 音频和视频通信可能会更快、更少中断, 而不是涉及文件传输、web 浏览或数据库备份等内容的网络会话。 这是因为用于文件传输或数据库备份的网络数据包被分配了 "最大努力" 优先级。


> [!NOTE]  
> 作为一般规则, 服务质量仅适用于内部网络上的通信会话。 实现 QoS 时, 配置服务器和路由器以支持数据包标记;但是, 你可以配置这些设备以支持以特定方式标记数据包。 您无法假定在 Internet 或其他网络上不支持该服务质量。 即使在其他网络上支持优质 if 服务, 也不能保证 QoS 的配置方式与您在网络上配置该服务的方式相同。

Skype for Business 服务器不需要服务质量;如果当前未使用 QoS, 则不需要在安装 Skype for Business 服务器之前安装服务。 如果你在网络上遇到大量数据包丢失, 建议的缓解此问题的方法是增加额外带宽。 如果无法增加更多的带宽, 则你可能希望改为实现服务质量。

Skype for Business 服务器提供全面的服务质量支持: 这意味着已使用 QoS 的组织可以轻松地将 Skype for business 服务器集成到其现有网络基础结构中。 若要执行此操作, 必须执行以下任务:

  - [为不基于 Windows 的设备启用 QoS](enabling-qos-for-devices-that-are-not-based-on-windows.md)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 尽管可以使用 Skype for Business 服务器启用和禁用设备的服务质量, 但通常无法使用该产品修改这些设备使用的 DSCP 代码。

  - [为你的会议、应用程序和中介服务器配置端口范围和服务质量策略](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 使用 Skype for Business 服务器, 您不能启用或禁用服务质量, 例如, 将属性值设置为 True 或 False。 而是通过配置端口范围, 然后创建和应用组策略来启用服务质量。 如果稍后决定不使用 QoS, 您只需通过删除相应的组策略对象即可 "禁用" 服务质量。

  - [为 Edge 服务器配置端口范围和服务质量策略](configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。 只有在边缘服务器的内部端才应配置服务质量策略。 这是因为 "服务质量" 专用于在内部网络上使用, 而不是在 Internet 上使用。

- [为 Skype For Business Server 中的客户端配置端口范围和服务质量策略](configuring-port-ranges-for-your-skype-clients.md) 这些端口范围仅适用于客户端计算机, 并且通常与服务器上配置的端口范围不同。 请注意, Skype for Business 服务器不支持 windows 10 之外的 Windows 操作系统的 QoS。


