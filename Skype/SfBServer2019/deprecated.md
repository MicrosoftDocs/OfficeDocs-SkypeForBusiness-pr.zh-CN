---
title: 什么被弃用从 Skype 业务服务器 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 这些功能已从 Skype 的业务服务器 2019年。
ms.openlocfilehash: 66366c2272db8d6f605fde6dc066f730543883b6
ms.sourcegitcommit: 27cd6d540485d5a1557a6131612894ca2f3516ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025078"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>什么被弃用从 Skype 业务服务器 2019 

了解如何为业务服务器 2019 Skype 中弃用的功能。 有关业务服务器 2019 Skype 中的新功能的信息，请参阅[What's 中的业务服务器 2019 Skype](whats-new.md)。

某些消除 emphasised 的功能中包含 Skype 的业务服务器 2019年与早期的产品版本的兼容性。 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>为业务服务器 2019 Skype 中弃用的功能 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP 网关的 Skype 业务服务器

业务服务器 2015年和其前置任务的 Skype 允许您配置边缘服务器和前端服务器或前端池上的 XMPP 网关的可扩展消息传递和状态协议 (XMPP) 的代理。 此功能不再可用的业务服务器 2019 Skype 中。


### <a name="persistent-chat-for-skype-for-business-server"></a>持久聊天的 Skype 业务服务器

持久聊天服务器是一个可选角色，可让您的组织中的多个用户参与随着时间的推移保留的聊天室对话。 持久聊天不能与 Skype 部署业务服务器 2019年。 从拓扑生成器，以及从代码删除此服务器角色。 

中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。   

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL 镜像 Skype 业务服务器

SQL 镜像无法部署与 Skype 的业务服务器 2019年。 仍然支持用于提供高可用性和灾难恢复的其他选项，您应选择从它们。 请参阅[规划高可用性和灾难恢复 Skype 业务服务器中的](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)检查的选项。

### <a name="in-place-upgrades"></a>就地升级 

就地升级中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 升级和 coexistance 都支持并排，详细信息，请参阅[迁移到业务服务器 2019年的 Skype](migration/migration-to-skype-for-business-server-2019.md) 。

###  <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

移动服务支持旧的移动客户端使用不再可用的业务服务器 2019 Skype 中。 这先前已的业务服务器 2015年宣布 Skype 中。

业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 Mcx 的旧客户端的用户需要升级到当前客户端。

有关详细信息，请参阅[规划 Mobility for Business Server 的 Skype](../SfbServer/plan-your-deployment/mobility.md)和[Skype for Business 的移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。

## <a name="tools"></a>工具

不将可用于在初始版本的 Skype 的业务服务器 2019年以下工具：

- Skype 业务服务器容量规划计算器
- Skype 业务 server 调试工具
- Skype 的业务 Server 资源工具包工具 （一些工具将被删除）
    - 呼叫寄存时间记录器
    - 查找用户控制台
    - 未分配的号码通知迁移

以下工具不支持与 Skype 业务服务器 2019年:

- 呼叫质量方法 （但不是呼叫质量仪表板）
- Microsoft 呼叫质量方法记分卡、 v1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>另请参阅

[What's new in Business Server 2019 的 Skype](whats-new.md)

[迁移 XMPP 联盟](migration/migrating-xmpp-federation.md)