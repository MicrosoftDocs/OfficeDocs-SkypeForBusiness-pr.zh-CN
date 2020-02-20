---
title: Skype for Business Server 2019 中弃用的内容
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能已从 Skype for Business Server 2019 中删除。
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125215"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 中弃用的内容

了解 Skype for Business Server 2019 中弃用的特性和功能。 有关 Skype for business Server 2019 中的新功能的信息，请参阅[skype For Business server 2019 中的内容](whats-new.md)。

Skype for Business Server 2019 中包含一些突出的功能，以与以前的产品版本兼容。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 中弃用的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Skype for business Server 的 XMPP 网关

Skype for Business Server 2015 及其前置任务允许您在边缘服务器上配置可扩展消息和状态协议（XMPP）代理，并在前端服务器或前端池上配置 XMPP 网关。 Skype for Business Server 2019 不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for business Server 的持久聊天

持久聊天服务器是一个可选角色，允许组织中的多个用户参与随时间推移而保留的聊天室对话。 不能使用 Skype for Business Server 2019 部署持久聊天。 此服务器角色将从拓扑生成器和代码中删除。 

团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。

### <a name="sql-mirroring-for-skype-for-business-server"></a>Skype for business Server 的 SQL 镜像

无法使用 Skype for Business Server 2019 部署 SQL 镜像。 仍支持其他提供高可用性和灾难恢复的选项，您应从这些选项中进行选择。 请参阅[在 Skype For Business Server 中规划高可用性和灾难恢复](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)以查看选项。

### <a name="in-place-upgrades"></a>就地升级 

Skype for Business Server 2015 中提供了就地升级，但 Skype for Business Server 2019 不再支持就地升级。 并行升级和共存受支持，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) 。

### <a name="mobility-service-mcx"></a>移动服务（Mcx）

旧版移动客户端使用的移动服务支持不再在 Skype for Business Server 2019 中可用。 这是以前在 Skype for Business Server 2015 中宣布的。

所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 Mcx 的旧版客户端的用户将需要升级到当前客户端。

有关更多详细信息，请参阅[Plan For skype for Business Server 的移动性](../SfbServer/plan-your-deployment/mobility.md)和[skype For business 的移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。

## <a name="tools"></a>工具

以下工具在最初发布的 Skype for Business Server 2019 中将不可用：

- Skype for Business Server 容量规划计算器
- Skype for Business Server 调试工具
- Skype for Business Server 资源工具包工具（某些工具将被删除）
    - 调用寄存时间记录器
    - 查找用户控制台
    - 未分配号码通知迁移

Skype for Business Server 2019 不支持以下工具：

- 呼叫质量方法（但不是呼叫质量仪表板）
- Microsoft 呼叫质量方法记分卡，1。5
- Skype for Business Server 2015 规划工具
- Skype for Business Server 2015 压力和性能工具

### <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 中的新增功能](whats-new.md)

[迁移 XMPP 联合](migration/migrating-xmpp-federation.md)
