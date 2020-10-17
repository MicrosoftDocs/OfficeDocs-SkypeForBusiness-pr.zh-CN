---
title: Lync Server 2013：前端池配对数据安全
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500719"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="b1d2e-102">Lync Server 2013 中的前端池配对数据安全性</span><span class="sxs-lookup"><span data-stu-id="b1d2e-102">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1d2e-103">_**上次修改的主题：** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="b1d2e-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="b1d2e-104">备份服务是 Lync Server 2013 中引入的一种数据复制机制，可跨两个数据中心连续传输两个配对前端池之间的用户数据和会议内容，以实现灾难恢复目的。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="b1d2e-105">用户数据包含 SIP URI，以及联系人列表和设置。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="b1d2e-106">会议内容包括 Microsoft PowerPoint 2010 上传以及在会议中使用的白板。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="b1d2e-107">从源池，将用户数据和会议内容从本地存储导出、提取和转换到目标池，其中是解压和导入到本地存储。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="b1d2e-108">备份服务假定两个数据中心之间的通讯链路位于公司网络内部，受 Internet 保护。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="b1d2e-109">它不会在两个数据中心之间加密传输的数据，也不会在安全协议（如 HTTPS）内进行本地封装。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="b1d2e-110">因此有可能受到公司网络内来自内部人员的中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="b1d2e-111">评估安全风险</span><span class="sxs-lookup"><span data-stu-id="b1d2e-111">Evaluating Security Risks</span></span>

<span data-ttu-id="b1d2e-112">跨多个数据中心部署 Lync Server 2013 并使用灾难恢复功能的任何企业都必须确保跨数据中心流量受到其公司 Intranet 的保护。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="b1d2e-113">在意内部攻击保护的企业必须保护数据中心中通讯链路的安全。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="b1d2e-p103">假定企业的数据中心受公司 Intranet 的保护是标准。有许多其他类型的公司敏感数据在这些数据中心间传输。如果不保护跨数据中心链接，则企业的 IT 基础结构处于极端的风险中。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="b1d2e-p104">当公司网络内存在中间人攻击的风险时，比较而言，它相当于包含将流量公开到 Internet。尤其是，通过备份服务（如，SIP URI）公开的用户数据通过其他方法（例如，按 Exchange 或其他目录软件列出的全局通讯簿）通常可用于公司内的所有员工。因此，当将备份服务用于复制两个成对池之间的数据时，重点应该是保护两个数据中心之间的 WAN。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="b1d2e-120">减轻安全风险</span><span class="sxs-lookup"><span data-stu-id="b1d2e-120">Mitigating Security Risks</span></span>

<span data-ttu-id="b1d2e-121">可通过多种方式来增强对备份服务流量的安全保护，包括限制对数据中心的访问，以保护两个数据中心之间的 WAN 传输。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="b1d2e-122">在大多数情况下，部署 Lync Server 2013 的企业可能已经具备所需的安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="b1d2e-123">对于寻求指导的企业，Microsoft 提供解决方案作为如何构建安全 IT 基础结构的示例。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="b1d2e-124">但是，这并不意味着它是唯一的解决方案，也不意味着它是 Lync Server 的首选解决方案。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="b1d2e-125">我们建议企业客户根据其 IT 安全基础结构和要求选择解决方案满足其特定需求。Microsoft 解决方案示例为服务器和域隔离采用 IPSec 和组策略。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="b1d2e-126">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) 。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="b1d2e-127">有关问题和意见，请联系 secwish@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="b1d2e-128">另一种可能的解决方案是使用 IPSec 来帮助保护由备份服务本身发送的数据。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="b1d2e-129">如果选择此方法，则应为以下服务器配置 SMB 协议的 IPSec 规则，其中池 A 和池 B 是两个配对的前端池。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="b1d2e-130">SMB 服务 (TCP/445) 从池 A 中的每个前端服务器到池 B 使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="b1d2e-131">SMB 服务 (TCP/445) 从池 B 中的每个前端服务器到池 A 使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b1d2e-132">IPsec 不是为了替换应用程序级别的安全，如 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="b1d2e-133">使用 IPsec 的一个优点是，它可以为现有的应用程序提供网络流量安全性，而无需对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="b1d2e-134">希望仅保护两个数据中心之间的传输安全的企业应咨询其各自的网络硬件供应商，了解如何使用供应商的设备设置安全 WAN 连接。</span><span class="sxs-lookup"><span data-stu-id="b1d2e-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

