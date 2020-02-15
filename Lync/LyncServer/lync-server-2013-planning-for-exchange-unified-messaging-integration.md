---
title: Lync Server 2013：规划 Exchange 统一消息集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5eb18418ad860452a51667fdf1550e948a1155
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="8e6c8-102">在 Lync Server 2013 中规划 Exchange 统一消息集成</span><span class="sxs-lookup"><span data-stu-id="8e6c8-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e6c8-103">_**上次修改的主题：** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="8e6c8-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="8e6c8-104">Lync Server 2013 支持与 Exchange 统一消息（UM）集成，以将语音邮件和电子邮件消息合并到一个邮件基础结构中。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="8e6c8-105">在 Microsoft Exchange Server 2007 Service Pack 1 （SP1）和 Microsoft Exchange Server 2010 中，Exchange 统一消息（UM）是您可以安装和配置的多个 Exchange 服务器角色之一。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="8e6c8-106">在 Microsoft Exchange Server 2013 中，Exchange UM 在 Exchange 邮箱服务器上作为一项服务运行。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="8e6c8-107">对于 Lync Server 2013 企业语音部署，统一消息将语音邮件和电子邮件合并到从电话（Outlook Voice Access）或计算机上提供的单个存储中。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="8e6c8-108">统一消息和 Lync Server 2013 协同工作，为企业语音用户提供呼叫应答、Outlook Voice Access 和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="8e6c8-109">有关 Microsoft Exchange Server 2013 中的体系结构更改的详细信息，请参阅中的 Microsoft Exchange Server 2013 文档中的 "语音[http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)体系结构更改"。</span><span class="sxs-lookup"><span data-stu-id="8e6c8-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="8e6c8-110">若要在本地 Exchange UM 部署中支持这些功能，您必须运行以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="8e6c8-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="8e6c8-111">Microsoft Exchange Server 2007 Service Pack 1 （SP1）或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="8e6c8-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="8e6c8-112">Microsoft Exchange Server 2010 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="8e6c8-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="8e6c8-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e6c8-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e6c8-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="8e6c8-114">In This Section</span></span>

  - [<span data-ttu-id="8e6c8-115">集成统一消息和 Lync Server 2013 的功能</span><span class="sxs-lookup"><span data-stu-id="8e6c8-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="8e6c8-116">Lync Server 2013 中的本地统一消息的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="8e6c8-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="8e6c8-117">集成本地统一消息和 Lync Server 2013 的准则</span><span class="sxs-lookup"><span data-stu-id="8e6c8-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="8e6c8-118">集成本地统一消息和 Lync Server 2013 的部署过程</span><span class="sxs-lookup"><span data-stu-id="8e6c8-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

