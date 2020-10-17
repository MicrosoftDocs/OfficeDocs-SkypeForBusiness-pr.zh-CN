---
title: Lync Server 2013： Exchange 统一消息 (UM) 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac42e46bf92e7fa170ee3dff059edc1b5871aafd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533119"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 统一消息 (UM) 支持

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

Lync Server 2013 支持与 Exchange 统一消息 (UM) 集成，以便将语音邮件和电子邮件消息合并到一个邮件基础结构中。 在 Exchange 2013 中，Exchange UM 由在邮箱服务器上安装和运行的 Exchange UM 服务以及在客户端访问服务器上安装和运行的 UM 呼叫路由器组成。 对于 Lync Server 2013 企业语音部署，Exchange UM 将语音邮件和电子邮件合并到可通过电话 (（即 Outlook Voice Access) 或计算机）访问的单个存储中。 Exchange UM 和 Lync Server 2013 协同工作，为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。

除了支持与 Exchange UM 的本地部署集成之外，Lync Server 2013 还支持与托管 Exchange UM 集成。 这样可使您在将某些或所有用户迁移到托管 Exchange 服务提供商（如 Microsoft Exchange Online）时，为用户提供语音消息传递。

Lync Server 2013 支持以下版本：

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必需的) 或 (建议的最新 service pack) 

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1)  (所需的) 或最新的 service pack (建议的) 

您不能并置 Exchange UM 与 Lync Server 2013 或 Lync Server 2013 数据库。 您可以在单独的林中安装 Exchange UM 和 Lync Server 2013。

<div>


> [!NOTE]  
> Exchange UM 可能不是已部署 PBX 的企业语音部署所必需的，因为 PBX 可以继续向所有用户提供语音邮件和相关服务。 如果您最终停用 PBX (例如，如果为公用电话交换网 (PSTN) 连接) 部署 SIP 中继，则必须重新配置 Exchange UM，以向以前使用 PBX 语音邮件系统的用户提供语音邮件。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的本地统一消息的组件和拓扑](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [在 Lync Server 2013 中支持托管 Exchange UM 集成](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

