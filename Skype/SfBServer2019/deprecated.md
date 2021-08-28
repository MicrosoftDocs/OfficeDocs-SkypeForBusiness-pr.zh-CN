---
title: 自 2019 年 10 Skype for Business Server弃用功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 摘要：这些功能已从 2019 Skype for Business Server中删除。
ms.openlocfilehash: cdc7b54f815c324707ee657d8365aa842f28293d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595026"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>自 2019 年 10 Skype for Business Server弃用功能

了解 2019 年 10 月弃Skype for Business Server的功能。 有关 Skype for Business Server 2019 中的新功能的信息，请参阅[what's in Skype for Business Server 2019](whats-new.md)。

为了与以前的产品版本兼容，Skype for Business Server 2019 年包含一些有所强调的功能。

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>2019 年 Skype for Business Server弃用的功能 

2019 年 3 月，已弃Skype for Business Server功能。

### <a name="xmpp-gateways-for-skype-for-business-server"></a>用于网关的 XMPP Skype for Business Server

Skype for Business Server 2015 及其前置版本允许在边缘服务器上配置可扩展消息传递和状态协议 (XMPP) 代理，在前端服务器或前端池上配置 XMPP 网关。 2019 年 10 月Skype for Business Server此功能。

### <a name="persistent-chat-for-skype-for-business-server"></a>持久聊天Skype for Business Server

持久聊天服务器是一个可选角色，可让贵组织中多个用户参与持久聊天室对话。 2019 年 10 月Skype for Business Server持久聊天。 此服务器角色已从拓扑生成器和代码中删除。 

相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL镜像Skype for Business Server

SQL2019 年 10 月Skype for Business Server镜像。 提供高可用性和灾难恢复的其他选项仍受支持，你应该从中选择。 请参阅[Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)查看这些选项。

### <a name="in-place-upgrades"></a>就地升级 

2015 年 2 月Skype for Business Server就地升级，但在 2019 年 2 月不再Skype for Business Server升级。 支持并行升级和共存。 有关详细信息，请参阅 Migration [to Skype for Business Server 2019。](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx) 

所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 Mcx 的旧客户端的用户将需要升级到当前客户端。

有关更多详细信息，请参阅 Plan [for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for [Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。

## <a name="tools"></a>工具

在 2019 年 10 月的初始版本中，以下Skype for Business Server可用：

- Skype for Business Server 容量计划计算器
- Skype for Business Server调试工具
- Skype for Business Server资源工具包 (一些工具将) 
    - 呼叫 Parkometer
    - 查找用户控制台
    - 未分配号码通知迁移

2019 年 3 月不支持Skype for Business Server工具：

- 通话质量方法 (而不是呼叫质量仪表板) 
- Microsoft 呼叫质量方法记分卡，v1.5
- Skype for Business Server 2015 规划工具
- Skype for Business Server 2015 压力和性能工具

### <a name="see-also"></a>另请参阅

[2019 年 Skype for Business Server 的新增功能](whats-new.md)

[管理 XMPP 联盟](migration/migrating-xmpp-federation.md)
