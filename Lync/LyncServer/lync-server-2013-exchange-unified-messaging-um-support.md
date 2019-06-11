---
title: Lync Server 2013：Exchange 统一消息 (UM) 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 统一消息 (UM) 支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

Lync Server 2013 支持与 Exchange 统一消息 (UM) 集成, 以将语音消息和电子邮件合并到单个消息传递基础结构中。 在 Exchange 2013 中, Exchange UM 由 Exchange UM 服务 (在邮箱服务器上安装和运行) 和 UM 呼叫路由器 (在客户端访问服务器上安装和运行) 组成。 对于 Lync Server 2013 企业语音部署, Exchange UM 将语音消息和电子邮件合并到可通过电话 (即 Outlook Voice Access) 或计算机访问的单个应用商店。 Exchange UM 和 Lync Server 2013 协同工作, 为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。

除了支持 Exchange 的本地部署之外, Lync Server 2013 支持与托管 Exchange UM 的集成。 这使你可以向你的用户提供语音消息传递, 如果你将部分或全部迁移到托管 Exchange 服务提供商 (如 Microsoft Exchange Online)。

Lync Server 2013 支持下列版本:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必需) 或最新 service pack (推荐)

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) (必需) 或最新服务包 (推荐)

您不能将 Exchange UM 与 Lync Server 2013 或 Lync Server 2013 数据库 collocate。 你可以在单独的林中安装 Exchange UM 和 Lync Server 2013。

<div>


> [!NOTE]  
> 对于已部署 PBX 的企业语音部署, Exchange UM 可能不是必需的, 因为 PBX 可以继续向所有用户提供语音邮件和相关服务。 如果你最终停用了 PBX (例如, 如果你为公共交换电话网络 (PSTN) 连接部署 SIP 中继), 则必须重新配置 Exchange UM, 以便向以前使用 PBX 语音邮件系统的用户提供语音邮件。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的本地统一消息的组件和拓扑](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 中的托管 Exchange UM 集成支持](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

