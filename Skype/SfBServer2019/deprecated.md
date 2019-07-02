---
title: Skype for Business Server 2019 中的弃用内容
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 已从 Skype for Business Server 2019 中删除这些功能。'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418359"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Skype for Business Server 2019 中的弃用内容

了解 Skype for Business Server 2019 中已弃用的功能和功能。 有关 Skype for Business Server 2019 中的新增功能的信息, 请参阅[skype for Business server 2019 中的内容](whats-new.md)。

Skype for Business Server 2019 中提供了一些突出的功能, 可与以前的产品版本兼容。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 中已弃用的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Skype for business Server 的 XMPP 网关

Skype for Business Server 2015 及其前置任务允许你在 Edge 服务器上配置可扩展消息和状态协议 (XMPP) 代理和前端服务器或前端池上的 XMPP 网关。 Skype for Business Server 2019 不再提供此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>Skype for business 服务器的持久聊天

持久聊天服务器是一种可选角色, 允许组织中的多个用户参与不断保持的聊天室对话。 Skype for Business Server 2019 不能部署持久聊天。 此服务器角色将从拓扑生成器和代码中删除。 

团队中提供了相同的功能。 有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。

### <a name="sql-mirroring-for-skype-for-business-server"></a>Skype for business Server 的 SQL 镜像

无法通过 Skype for Business Server 2019 部署 SQL 镜像。 提供高可用性和灾难恢复的其他选项仍受支持, 你应从这些选项中进行选择。 请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)以查看选项。

### <a name="in-place-upgrades"></a>就地升级 

Skype for business Server 2015 中提供了就地升级, 但 Skype for business Server 2019 不再支持就地升级。 支持并行升级和 coexistance, 有关详细信息, 请参阅[迁移到 Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) 。

### <a name="mobility-service-mcx"></a>移动服务 (Mcx)

旧版移动客户端使用的移动服务支持不再在 Skype for Business Server 2019 中可用。 这是以前在 Skype for Business Server 2015 中宣布的。

所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 Mcx 的旧客户端的用户将需要升级到当前客户端。

有关更多详细信息, 请参阅 Skype for business 适用于 skype for business Server 和[移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)的[计划](../SfbServer/plan-your-deployment/mobility.md)。

## <a name="tools"></a>工具

Skype for business Server 2019 的初始版本中将不提供以下工具:

- Skype for Business Server 容量计划计算器
- Skype for Business 服务器调试工具
- Skype for Business 服务器资源工具包工具 (某些工具将被删除)
    - 呼叫寄存时间记录器
    - 查找用户控制台
    - 未分配号码公告迁移

Skype for Business Server 2019 不支持以下工具:

- 通话质量方法 (但不是通话质量仪表板)
- Microsoft 通话质量方法记分卡, v 1。5
- Skype for Business Server 2015 规划工具
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>另请参阅

[Skype for Business Server 2019 中的新增功能](whats-new.md)

[管理 XMPP 联盟](migration/migrating-xmpp-federation.md)
