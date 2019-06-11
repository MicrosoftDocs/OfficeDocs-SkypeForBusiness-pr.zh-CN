---
title: 'Lync Server 2013: 前端服务器 VoIP 组件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3558d230b1fb767f0e7844be3894b579149c3f6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Lync Server 2013 的前端服务器 VoIP 组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

位于前端服务器上的 VoIP 组件如下所示:

  - 转换服务

  - 入站路由组件

  - 出站路由组件

  - Exchange UM 路由组件

  - 群集间路由组件

  - [Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>转换服务

转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。

</div>

<div>

## <a name="inbound-routing-component"></a>入站路由组件

入站路由组件根据用户在其企业语音客户端指定的首选项处理传入的呼叫。 它还可以实现代理人响铃和同时响铃（如果用户已配置）。 例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。 如果启用了呼叫转移, 用户可以指定是否应将未应答的呼叫转发到另一个号码或已配置为提供呼叫应答的 Exchange UM 服务器。 入站路由组件默认情况下在所有标准版服务器和前端服务器上安装。

</div>

<div>

## <a name="outbound-routing-component"></a>出站路由组件

出站路由组件将呼叫路由到 PBX 或 PSTN 目标。 它将呼叫授权规则（如用户的语音策略所定义）应用于呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。 默认情况下, 在所有标准版服务器和前端服务器上安装出站路由组件。

出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。

</div>

<div>

## <a name="exchange-um-routing-component"></a>Exchange UM 路由组件

Exchange UM 路由组件处理 Lync 服务器与运行 Exchange 统一消息 (UM) 的服务器之间的路由, 以便将 Lync Server 与统一邮件功能集成。

如果 Exchange UM 服务器不可用, Exchange UM 路由组件还会通过 PSTN 处理语音邮件的重新路由。 如果在没有指向中心网站的弹性 WAN 链接的分支站点上有企业语音用户, 则在分支站点上部署的 Survivable 分支装置将在 WAN 中断期间为分支用户提供语音邮件留存。 当 WAN 链接不可用时, Survivable 分支装置将执行以下操作:

  - 通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器

  - 为用户提供通过 PSTN 取回语音邮件消息的功能

  - 使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。

为了启用语音邮件重新路由, 我们建议你的 Exchange 管理员将 Exchange UM 自动助理 (AA) 配置为仅接受邮件。

有关这些功能的详细信息, 请参阅[在 Lync server 2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[在 lync Server 2013 中规划企业语音弹性](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

</div>

<div>

## <a name="intercluster-routing-component"></a>群集间路由组件

群集间路由组件负责将呼叫路由至被叫方的主注册器池。如果该池不可用，则组件将呼叫路由至被叫方的备份注册器池。如果无法通过 IP 网络访问被叫方的主注册器池和备份注册器池，则群集间路由组件会通过 PSTN 将呼叫重新路由至用户的电话号码。

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP 所需的其他前端服务器组件

驻留在前端服务器或控制器上的其他组件, 可提供对 VoIP 的重要支持, 但不是自身的 VoIP 组件, 包括以下内容:

  - **用户服务。** 对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。 入站路由组件利用这一信息将呼叫分发到该用户的已注册 SIP 终结点。 用户服务是所有前端服务器和控制器上的核心组件。

  - **用户复制程序。** 从 Active Directory 域服务中提取用户电话号码, 并将其写入到 RTC 数据库中的表中, 用户服务和通讯簿服务器可使用这些号码。 用户复制程序是所有前端服务器上的核心组件。

  - **通讯簿服务器。** 提供从 Active Directory 域服务到 Lync Server 客户端的全局地址列表信息。 它还从 RTC 数据库中检索用户和联系人信息, 将信息写入通讯簿文件, 然后将文件存储在由 Lync 客户端下载的共享文件夹中。 通讯簿服务器将信息写入 RTCAb 数据库, 由通讯簿 Web 查询服务用于响应 Microsoft Lync 2010 Mobile 中的用户搜索查询。 它还可以对写入 RTC 数据库的企业用户电话号码进行标准化, 以便在 Lync 中预配用户联系人。 默认情况下, 通讯簿服务在所有前端服务器上安装。 默认情况下, 通讯簿 Web 查询服务与每个前端服务器上的 Web 服务一起安装。

</div>

</div>

<span> </span>

</div>

</div>

</div>

