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

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="b7df7-102">Lync Server 2013 中的 Exchange 统一消息 (UM) 支持</span><span class="sxs-lookup"><span data-stu-id="b7df7-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7df7-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b7df7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b7df7-104">Lync Server 2013 支持与 Exchange 统一消息 (UM) 集成, 以将语音消息和电子邮件合并到单个消息传递基础结构中。</span><span class="sxs-lookup"><span data-stu-id="b7df7-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="b7df7-105">在 Exchange 2013 中, Exchange UM 由 Exchange UM 服务 (在邮箱服务器上安装和运行) 和 UM 呼叫路由器 (在客户端访问服务器上安装和运行) 组成。</span><span class="sxs-lookup"><span data-stu-id="b7df7-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="b7df7-106">对于 Lync Server 2013 企业语音部署, Exchange UM 将语音消息和电子邮件合并到可通过电话 (即 Outlook Voice Access) 或计算机访问的单个应用商店。</span><span class="sxs-lookup"><span data-stu-id="b7df7-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="b7df7-107">Exchange UM 和 Lync Server 2013 协同工作, 为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="b7df7-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="b7df7-108">除了支持 Exchange 的本地部署之外, Lync Server 2013 支持与托管 Exchange UM 的集成。</span><span class="sxs-lookup"><span data-stu-id="b7df7-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="b7df7-109">这使你可以向你的用户提供语音消息传递, 如果你将部分或全部迁移到托管 Exchange 服务提供商 (如 Microsoft Exchange Online)。</span><span class="sxs-lookup"><span data-stu-id="b7df7-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="b7df7-110">Lync Server 2013 支持下列版本:</span><span class="sxs-lookup"><span data-stu-id="b7df7-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="b7df7-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="b7df7-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="b7df7-112">Microsoft Exchange Server 2010 (必需) 或最新 service pack (推荐)</span><span class="sxs-lookup"><span data-stu-id="b7df7-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="b7df7-113">Microsoft Exchange Server 2007 Service Pack 1 (SP1) (必需) 或最新服务包 (推荐)</span><span class="sxs-lookup"><span data-stu-id="b7df7-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="b7df7-114">您不能将 Exchange UM 与 Lync Server 2013 或 Lync Server 2013 数据库 collocate。</span><span class="sxs-lookup"><span data-stu-id="b7df7-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="b7df7-115">你可以在单独的林中安装 Exchange UM 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b7df7-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7df7-116">对于已部署 PBX 的企业语音部署, Exchange UM 可能不是必需的, 因为 PBX 可以继续向所有用户提供语音邮件和相关服务。</span><span class="sxs-lookup"><span data-stu-id="b7df7-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="b7df7-117">如果你最终停用了 PBX (例如, 如果你为公共交换电话网络 (PSTN) 连接部署 SIP 中继), 则必须重新配置 Exchange UM, 以便向以前使用 PBX 语音邮件系统的用户提供语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b7df7-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7df7-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="b7df7-118">In This Section</span></span>

  - [<span data-ttu-id="b7df7-119">Lync Server 2013 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="b7df7-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="b7df7-120">Lync Server 2013 中的托管 Exchange UM 集成支持</span><span class="sxs-lookup"><span data-stu-id="b7df7-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

