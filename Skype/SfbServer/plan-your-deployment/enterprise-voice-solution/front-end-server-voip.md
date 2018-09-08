---
title: Skype 业务服务器的前端服务器 VoIP 组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 了解业务服务器，包括翻译服务和各个路由组件位于 Skype 在前端服务器的企业语音组件。
ms.openlocfilehash: 5b99ea77d31f1697b0809c4089c801b2df729a29
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888895"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Skype 业务服务器的前端服务器 VoIP 组件

了解业务服务器，包括翻译服务和各个路由组件位于 Skype 在前端服务器的企业语音组件。

位于前端服务器上的 VoIP 组件如下所示：

- 转换服务

- 入站路由组件

- 出站路由组件

- Exchange UM 路由组件

- 群集间路由组件

- [Skype 业务服务器中的中介服务器组件](mediation-server.md)

## <a name="translation-service"></a>转换服务

转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。

## <a name="inbound-routing-component"></a>入站路由组件

Inbound Routing 组件处理很大程度上是根据其企业语音客户端上的用户指定的首选项的传入呼叫。 它还可以实现代理人响铃和同时响铃（如果用户已配置）。 例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。 如果启用呼叫转接后，用户可以指定未应答的呼叫应该转发到其他号码或已配置为提供呼叫应答的 Exchange UM 服务器。 默认情况下，在所有 Standard Edition 服务器和前端服务器上安装 Inbound Routing 组件。

## <a name="outbound-routing-component"></a>出站路由组件

出站路由组件将呼叫路由到 PBX 或 PSTN 目标。 它适用呼叫授权规则定义的用户的语音策略，向呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。 默认情况下，在所有 Standard Edition 服务器和前端服务器上安装的出站路由组件。

出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。

## <a name="exchange-um-routing-component"></a>Exchange UM 路由组件

Exchange UM 路由组件处理 Skype 业务服务器和服务器运行 Exchange 统一消息 (UM)，将 Skype 与统一消息功能集成业务服务器之间的路由。

Exchange UM 路由组件还会处理重新路由的语音邮件通过 PSTN 如果 Exchange UM 服务器不可用。 如果您需要在企业语音用户不具有可恢复的 WAN 链接到中心网站，在分支站点部署 Survivable Branch Appliance 的分支站点提供语音邮件生存能力为分支用户 WAN 中断期间。 在 WAN 链接不可用时，Survivable Branch Appliance 执行以下任务：

- 通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器

- 为用户提供通过 PSTN 取回语音邮件消息的功能

- 使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。

若要启用语音邮件重新路由，建议您的 Exchange 管理员配置 Exchange UM 自动助理 (AA) 仅接受消息。

有关这些功能的详细信息，请参阅[On-premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)，分别。

## <a name="intercluster-routing-component"></a>群集间路由组件

群集间路由组件，负责呼叫路由至被叫方的主注册器池。 如果是不可用，组件路由到被叫方的备份注册器池。 被叫方的主要和备份注册器池都无法访问通过 IP 网络，如果群集间路由组件将重排通过 PSTN 到用户的电话号码的呼叫。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端服务器组件

驻留在前端服务器或控制器上为 VoIP 提供必要支持，但并非 VoIP 组件的其他组件包括：

- **用户服务。** 对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。 使用此信息，Inbound Routing 组件将呼叫分发到该用户的已注册 SIP 终结点。 用户服务是所有前端服务器和控制器上的核心组件。

- **用户复制程序。** 从 Active Directory 域服务中提取用户电话号码并将它们写入到 RTC 数据库，它们是可供用户服务和通讯簿服务器中的表。 用户复制程序是所有前端服务器上的核心组件。

- **通讯簿服务器。** 全局地址列表信息向提供来自 Active Directory 域服务 Skype Business Server 客户端。 它还从 RTC 数据库中检索用户和联系人信息、 将信息写入通讯簿文件，然后将存储其中他们业务客户端下载的 Skype 的共享文件夹上的文件。 通讯簿服务器将信息写入 RTCAb 数据库，通讯簿 Web 查询服务用于响应来自 Skype for Business 移动用户搜索查询。 还可以规范化写入 RTC 数据库以设置 Skype for Business 中的用户联系人的企业用户电话号码。 默认情况下，所有前端服务器上安装通讯簿服务。 默认情况下，每个前端服务器上的 Web 服务与安装通讯簿 Web 查询服务。


