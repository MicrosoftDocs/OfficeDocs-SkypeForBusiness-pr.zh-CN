---
title: Lync Server 2013：前端服务器 VoIP 组件
TOCTitle: 前端服务器 VoIP 组件
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425812(v=OCS.15)
ms:contentKeyID: 49312411
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的前端服务器 VoIP 组件

 

_**上一次修改主题：** 2012-10-01_

位于 前端服务器上的 VoIP 组件如下：

  - 转换服务

  - 入站路由组件

  - 出站路由组件

  - Exchange UM 路由组件

  - 群集间路由组件

  - [Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)

## 转换服务

转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。

## 入站路由组件

入站路由组件在很大程度上是根据用户在其 企业语音客户端上指定的首选项来处理传入呼叫。它还可以实现代理人响铃和同时响铃（如果用户已配置）。例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。如果启用了呼叫转接，则用户可以指定是应将未应答的呼叫转接到其他号码，还是转接到已配置为提供呼叫应答的 Exchange UM 服务器。默认情况下，入站路由组件安装在所有 Standard Edition Server 和 前端服务器上。

## 出站路由组件

出站路由组件将呼叫路由到 PBX 或 PSTN 目标。它将呼叫授权规则（如用户的语音策略所定义）应用于呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。默认情况下，出站路由组件安装在所有 Standard Edition Server 和 前端服务器上。

出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。

## Exchange UM 路由组件

Exchange UM 路由组件处理 Lync Server 与运行 Exchange 统一消息 (UM) 的服务器之间的路由，以便将 Lync Server 与统一消息功能相集成。

Exchange UM 服务器不可用时， Exchange UM 路由组件还可以通过 PSTN 处理语音邮件的重新路由。如果分支站点的 企业语音用户没有连接到中央站点的可恢复 WAN 链路，则分支站点部署的 Survivable Branch Appliance 可以在 WAN 中断期间使分支用户能够继续使用语音邮件。WAN 链路不可用时， Survivable Branch Appliance 将执行以下操作：

  - 通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器

  - 为用户提供通过 PSTN 取回语音邮件消息的功能

  - 使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。

要启用语音邮件重新路由，建议您的 Exchange 管理员将 Exchange UM 自动助理 (AA) 配置为仅接受消息。

有关这些功能的详细信息，请分别参阅 [在 Lync Server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和 [在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

## 群集间路由组件

群集间路由组件负责将呼叫路由至被叫方的主注册器池。如果该池不可用，则组件将呼叫路由至被叫方的备份注册器池。如果无法通过 IP 网络访问被叫方的主注册器池和备份注册器池，则群集间路由组件会通过 PSTN 将呼叫重新路由至用户的电话号码。

## VoIP 所需的其他前端服务器组件

驻留在 前端服务器或 控制器上为 VoIP 提供必要支持、但本身并非 VoIP 组件的其他组件包括：

  - **用户服务。** 对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。入站路由组件利用这一信息将呼叫分发到该用户的已注册 SIP 终结点。用户服务是所有 前端服务器和 控制器上的核心组件。

  - **用户复制程序。** 从 Active Directory 域服务 中提取用户电话号码，然后将其写入 RTC 数据库的表中，供用户服务和通讯簿服务器使用。用户复制程序是所有 前端服务器上的核心组件。

  - **通讯簿服务器。** 向 Lync Server 客户端提供来自 Active Directory 域服务 的全局地址列表信息。此外，还从 RTC 数据库检索用户和联系人信息，将信息写入通讯簿文件，然后将文件存储在一个共享文件夹中； Lync 客户端将从该文件夹下载这些文件。通讯簿服务器将这些信息写入 RTCAb 数据库， 通讯簿 Web 查询服务使用该数据库响应来自 Microsoft Lync 2010 Mobile 的用户搜索查询。还可以规范化写入 RTC 数据库中的企业用户电话号码，以设置 Lync 中的用户联系人。默认情况下，所有 前端服务器上都有安装通讯簿服务。默认情况下， 通讯簿 Web 查询服务随 Web 服务一起安装在每台 前端服务器上。

