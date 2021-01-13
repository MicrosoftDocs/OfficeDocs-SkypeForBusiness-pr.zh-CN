---
title: Skype for Business Server 2019 弃用内容
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能已从 Skype for Business Server 2019 中删除。
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808722"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 弃用内容

了解 Skype for Business Server 2019 中弃用的特性和功能。 有关 Skype for Business Server 2019 中的新功能的信息，请参阅 [Skype for Business Server 2019](whats-new.md)中的功能。

为了与以前的产品版本兼容，Skype for Business Server 2019 中包含一些不着重强调的功能。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 中弃用的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>适用于 Skype for Business Server 的 XMPP 网关

Skype for Business Server 2015 及其前置任务允许在边缘服务器上配置可扩展消息传递和状态协议 (XMPP) 代理，在前端服务器或前端池上配置 XMPP 网关。 Skype for Business Server 2019 中不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for Business Server 持久聊天

持久聊天服务器是一个可选角色，可让贵组织中多个用户参与持续一段时间的聊天室对话。 无法通过 Skype for Business Server 2019 部署持久聊天。 此服务器角色从拓扑生成器和代码中删除。 

Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Skype for Business Server 的镜像

SQL镜像无法与 Skype for Business Server 2019 一起部署。 提供高可用性和灾难恢复的其他选项仍受支持，您应从中进行选择。 请参阅 [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.

### <a name="in-place-upgrades"></a>就地升级 

就地升级在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 支持并行升级和共存，有关详细信息，请参阅迁移到[Skype for Business Server 2019。](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx) 

旧版移动客户端使用的移动服务支持在 Skype for Business Server 2019 中不再可用。 这之前在 Skype for Business Server 2015 中公布。

所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 Mcx 的旧客户端的用户将需要升级到当前客户端。

有关详细信息，请参阅[Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business。](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="tools"></a>工具

以下工具在 Skype for Business Server 2019 的初始版本中不可用：

- Skype for Business Server 容量计划计算器
- Skype for Business Server 调试工具
- Skype for Business Server 资源工具包 (某些工具将被删除) 
    - 呼叫 Parkometer
    - 查找用户控制台
    - 未分配号码通知迁移

Skype for Business Server 2019 不支持以下工具：

- 通话质量方法 (而不是通话质量仪表板) 
- Microsoft 通话质量方法记分卡 v1.5
- Skype for Business Server 2015 规划工具
- Skype for Business Server 2015 压力和性能工具

### <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 的新增功能](whats-new.md)

[管理 XMPP 联盟](migration/migrating-xmpp-federation.md)
