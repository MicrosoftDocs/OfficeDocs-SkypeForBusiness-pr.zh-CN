---
title: Lync Server 2013：托管 Exchange 统一消息集成
description: Lync Server 2013：托管 Exchange 统一消息集成。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980c0bc47258e9fae94ff623559342ca36eea145
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550118"
---
# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="8f38e-103">Lync Server 2013 中的托管 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="8f38e-103">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f38e-104">_**上次修改的主题：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="8f38e-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="8f38e-105">除了支持以前的 Lync Server 2013 版本与 Exchange 统一消息 (UM) 的 *本地* 部署集成之外，Lync Server 2013 还引入了支持与 *托管* Exchange UM 的集成。</span><span class="sxs-lookup"><span data-stu-id="8f38e-105">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="8f38e-106">如果将部分或全部传输到托管 Exchange 服务提供程序（如 Microsoft Exchange Online），则托管 Exchange UM 将启用 Lync Server 2013 以向用户提供语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8f38e-106">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="8f38e-107">Lync Server 2013 企业版语音使用 Exchange UM 基础结构来提供呼叫应答、呼叫通知、语音访问 (包括语音邮件) 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="8f38e-107">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="8f38e-108">有关详细信息，请参阅 [集成统一消息和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="8f38e-108">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f38e-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="8f38e-109">In This Section</span></span>

  - [<span data-ttu-id="8f38e-110">Lync Server 2013 中的托管 Exchange UM 体系结构和路由</span><span class="sxs-lookup"><span data-stu-id="8f38e-110">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="8f38e-111">Lync Server 2013 中的托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="8f38e-111">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="8f38e-112">Lync Server 2013 中的托管 Exchange 用户管理</span><span class="sxs-lookup"><span data-stu-id="8f38e-112">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="8f38e-113">Lync Server 2013 中的托管 Exchange 联系人对象管理</span><span class="sxs-lookup"><span data-stu-id="8f38e-113">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="8f38e-114">将托管 Exchange UM 与 Lync Server 2013 集成在一起的部署过程</span><span class="sxs-lookup"><span data-stu-id="8f38e-114">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

