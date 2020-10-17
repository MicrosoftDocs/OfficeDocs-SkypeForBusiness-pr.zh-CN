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
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="f03aa-102">Lync Server 2013 中的 Exchange 统一消息 (UM) 支持</span><span class="sxs-lookup"><span data-stu-id="f03aa-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f03aa-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f03aa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f03aa-104">Lync Server 2013 支持与 Exchange 统一消息 (UM) 集成，以便将语音邮件和电子邮件消息合并到一个邮件基础结构中。</span><span class="sxs-lookup"><span data-stu-id="f03aa-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="f03aa-105">在 Exchange 2013 中，Exchange UM 由在邮箱服务器上安装和运行的 Exchange UM 服务以及在客户端访问服务器上安装和运行的 UM 呼叫路由器组成。</span><span class="sxs-lookup"><span data-stu-id="f03aa-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="f03aa-106">对于 Lync Server 2013 企业语音部署，Exchange UM 将语音邮件和电子邮件合并到可通过电话 (（即 Outlook Voice Access) 或计算机）访问的单个存储中。</span><span class="sxs-lookup"><span data-stu-id="f03aa-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="f03aa-107">Exchange UM 和 Lync Server 2013 协同工作，为企业语音的用户提供呼叫应答、Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="f03aa-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="f03aa-108">除了支持与 Exchange UM 的本地部署集成之外，Lync Server 2013 还支持与托管 Exchange UM 集成。</span><span class="sxs-lookup"><span data-stu-id="f03aa-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="f03aa-109">这样可使您在将某些或所有用户迁移到托管 Exchange 服务提供商（如 Microsoft Exchange Online）时，为用户提供语音消息传递。</span><span class="sxs-lookup"><span data-stu-id="f03aa-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="f03aa-110">Lync Server 2013 支持以下版本：</span><span class="sxs-lookup"><span data-stu-id="f03aa-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="f03aa-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="f03aa-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="f03aa-112">Microsoft Exchange Server 2010 (必需的) 或 (建议的最新 service pack) </span><span class="sxs-lookup"><span data-stu-id="f03aa-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="f03aa-113">Microsoft Exchange Server 2007 Service Pack 1 (SP1)  (所需的) 或最新的 service pack (建议的) </span><span class="sxs-lookup"><span data-stu-id="f03aa-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="f03aa-114">您不能并置 Exchange UM 与 Lync Server 2013 或 Lync Server 2013 数据库。</span><span class="sxs-lookup"><span data-stu-id="f03aa-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="f03aa-115">您可以在单独的林中安装 Exchange UM 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f03aa-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f03aa-116">Exchange UM 可能不是已部署 PBX 的企业语音部署所必需的，因为 PBX 可以继续向所有用户提供语音邮件和相关服务。</span><span class="sxs-lookup"><span data-stu-id="f03aa-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="f03aa-117">如果您最终停用 PBX (例如，如果为公用电话交换网 (PSTN) 连接) 部署 SIP 中继，则必须重新配置 Exchange UM，以向以前使用 PBX 语音邮件系统的用户提供语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f03aa-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f03aa-118">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f03aa-118">In This Section</span></span>

  - [<span data-ttu-id="f03aa-119">Lync Server 2013 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="f03aa-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="f03aa-120">在 Lync Server 2013 中支持托管 Exchange UM 集成</span><span class="sxs-lookup"><span data-stu-id="f03aa-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

