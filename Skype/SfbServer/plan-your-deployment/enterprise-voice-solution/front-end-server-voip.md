---
title: Skype for Business Server 2015 的前端服务器 VoIP 组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 了解有关企业语音组件的业务服务器，包括翻译服务和各种路由组件位于前端服务器在 Skype。
ms.openlocfilehash: eca9a83943d045c48b2b811e6370e54fc41f1714
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的前端服务器 VoIP 组件
 
了解有关企业语音组件的业务服务器，包括翻译服务和各种路由组件位于前端服务器在 Skype。
  
在前端服务器上的 VoIP 组件如下所示：
  
- 转换服务
    
- 入站路由组件
    
- 出站路由组件
    
- Exchange UM 路由组件
    
- 群集间路由组件
    
- [在业务服务器 2015年的 Skype 的中介服务器组件](mediation-server.md)
    
## <a name="translation-service"></a>转换服务

转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。
  
## <a name="inbound-routing-component"></a>入站路由组件

入站路由组件处理很大程度上根据首选项所指定的企业语音客户端上的用户的传入呼叫。 它还可以实现代理人响铃和同时响铃（如果用户已配置）。 例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。 如果启用呼叫转移，则用户可以指定无人应答的呼叫应转发到另一个号码或 Exchange UM 服务器已被配置为提供呼叫应答。 入站路由组件是默认安装的所有标准版服务器和前端服务器上。 
  
## <a name="outbound-routing-component"></a>出站路由组件

出站路由组件将呼叫路由到 PBX 或 PSTN 目标。 它应用调用授权规则，按照用户的语音策略，向调用方的定义，并确定最佳的 PSTN 网关路由选择的每个调用。 出站路由组件是默认安装的所有标准版服务器和前端服务器上。
  
出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。 
  
## <a name="exchange-um-routing-component"></a>Exchange UM 路由组件

该 UM Exchange 路由组件处理 Skype 业务服务器和运行 Exchange 统一消息 (UM)，服务器将 Skype 与统一消息功能集成业务服务器之间路由。 
  
该 UM Exchange 路由组件还可以处理通过 PSTN 重排的语音邮件，如果 Exchange UM 服务器都不可用。 如果您需要在企业语音用户没有弹性的 WAN 链接到中心站点，在分支站点部署高存活力分支装置的分支站点提供语音邮件留存能力对分支用户 WAN 中断。 WAN 链接不可用时，高存活力的分支装置执行以下任务：
  
- 通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器
    
- 为用户提供通过 PSTN 取回语音邮件消息的功能
    
- 使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。
    
若要启用语音邮件重新路由，我们建议您的 Exchange 管理员配置 Exchange UM 自动助理 (AA) 只接受消息。
  
有关这些功能的详细信息，请参阅[内部 Exchange 统一消息传递集成](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[企业语音复原规划](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)，分别。
  
## <a name="intercluster-routing-component"></a>群集间路由组件

Intercluster 的路由组件负责传送调用方的主注册器池。 如果它不可用，该组件将路由调用被调用方的备份注册器池。 如果被调用方的主要和备份注册器池将通过 IP 网络不可访问，则 Intercluster 路由组件重排通过 PSTN 到用户的电话号码呼叫。
  
## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端服务器组件

其他组件驻留在前端服务器或控制器上，提供基本支持 VoIP，但不是自己的 VoIP 组件，如下所示：
  
- **用户服务。** 对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。 使用此信息，该入站路由组件分布到该用户的注册 SIP 终结点的调用。 用户服务是核心组件，在所有前端服务器和董事。
    
- **用户复制程序。** 从 Active Directory 域服务中提取用户的电话号码并将其写入到 RTC 数据库，它们是供用户服务和通讯簿服务器中的表。 用户复制程序将所有前端服务器上的一个核心组件。
    
- **通讯簿服务器。** 提供全局地址列表信息从 Active Directory 域服务到 Skype 业务服务器的客户端。 它还从 RTC 数据库中检索用户和联系人信息、 将信息写入到通讯簿文件中，并将存储在它们的业务客户端下载通过 Skype 的共享文件夹中的文件。 通讯簿服务器写入 RTCAb 数据库，地址簿 Web 查询服务用于响应来自移动业务的 Skype 用户搜索查询的信息。 它还可以标准化写入 RTC 数据库，目的是提供在业务的 Skype 用户联系人的企业用户电话号码。 默认情况下，在所有前端服务器上安装通讯簿服务。 默认情况下，Web 服务在每个前端服务器上安装了地址簿 Web 查询服务。
    

