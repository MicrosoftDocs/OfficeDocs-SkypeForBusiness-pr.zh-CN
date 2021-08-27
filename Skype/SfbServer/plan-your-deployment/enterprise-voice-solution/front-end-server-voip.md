---
title: 用于服务器的前端服务器 VoIP Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 了解企业语音前端服务器上部署的组件，Skype for Business Server包括翻译服务和各种路由组件。
ms.openlocfilehash: d3baa24366b36d1962c1102b4c25c1745a4ea625
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585016"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>用于服务器的前端服务器 VoIP Skype for Business Server

了解企业语音前端服务器上部署的组件，Skype for Business Server包括翻译服务和各种路由组件。

位于前端服务器的 VoIP 组件如下所示：

- 转换服务

- 入站路由组件

- 出站路由组件

- Exchange UM 路由组件

- 群集间路由组件

- [中介服务器组件Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>转换服务

转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。

## <a name="inbound-routing-component"></a>入站路由组件

入站路由组件在很大程度上根据用户在客户端上指定的首选项来处理企业语音呼叫。 它还可以实现代理人响铃和同时响铃（如果用户已配置）。 例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。 如果启用了呼叫转发，则用户可以指定是应该将未应答的呼叫转发到另一个号码，还是应转发到配置为提供呼叫应答的 Exchange UM 服务器。 默认情况下，入站路由组件安装在所有Standard Edition前端服务器上。

## <a name="outbound-routing-component"></a>出站路由组件

出站路由组件将呼叫路由到 PBX 或 PSTN 目标。 它将用户语音策略定义的呼叫授权规则应用于呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。 默认情况下，出站路由组件安装在所有Standard Edition服务器和前端服务器上。

出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。

## <a name="exchange-um-routing-component"></a>Exchange UM 路由组件

um Exchange 组件处理 Skype for Business Server 与运行 Exchange 统一消息 (UM) 的服务器之间的路由，Skype for Business Server统一消息功能。

如果Exchange UM 服务器不可用，则 UM 路由组件还处理通过 PSTN Exchange语音邮件的重新路由。 如果分支企业语音没有指向中央站点的可恢复 WAN 链路的邮箱用户，则分支站点部署的 Survivable Branch Appliance 在 WAN 中断期间为分支用户提供语音邮件生存能力。 WAN 链路不可用时，Survivable Branch Appliance 将执行以下操作：

- 通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器

- 为用户提供通过 PSTN 取回语音邮件消息的功能

- 使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。

若要启用语音邮件重新路由，建议管理员Exchange UM Exchange AA 自动助理 () 接受邮件。

有关这些功能的详细信息，请分别参阅[On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)和[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)。

## <a name="intercluster-routing-component"></a>群集间路由组件

群集间路由组件负责将呼叫路由到被叫方的主注册器池。 如果不可用，组件将呼叫路由至被叫方备份注册器池。 如果无法通过 IP 网络访问被叫方的主注册器池和备份注册器池，则群集间路由组件会通过 PSTN 将呼叫重新路由至用户的电话号码。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端服务器组件

驻留在前端服务器或控制器上、为 VoIP 提供必要支持但本身不是 VoIP 组件的其他组件包括：

- **用户服务。** 对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。 入站路由组件使用此信息将呼叫分发到该用户的注册 SIP 终结点。 用户服务是所有前端服务器和控制器上的核心组件。

- **用户复制程序。** 从 Active Directory 域服务中提取用户电话号码，并写入 RTC 数据库中的表，这些表可供用户服务和通讯簿服务器使用。 用户复制程序是所有前端服务器上的核心组件。

- **通讯簿服务器。** 将来自 Active Directory 域服务的全局地址列表信息Skype for Business Server客户端。 它还从 RTC 数据库检索用户和联系人信息，将信息写入通讯簿文件，然后将文件存储在共享文件夹中，这些文件由 Skype for Business 客户端下载。 通讯簿服务器将信息写入 RTCAb 数据库，通讯簿 Web 查询服务使用该数据库响应来自移动电话的用户Skype for Business查询。 它选择性地规范化写入 RTC 数据库的企业用户电话号码，以便设置 RTC Skype for Business。 默认情况下，通讯簿服务安装在所有前端服务器上。 默认情况下，通讯簿 Web 查询服务随 Web 服务一起安装在每台前端服务器上。