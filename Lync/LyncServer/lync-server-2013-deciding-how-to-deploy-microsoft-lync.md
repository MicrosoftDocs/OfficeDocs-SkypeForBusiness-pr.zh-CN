---
title: Lync Server 2013：决定如何部署 Microsoft Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f1869cce980f8eb530e1541bd64ead3a7b4258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="ad522-102">确定如何部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad522-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad522-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ad522-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ad522-104">在规划 Lync 时，第一个主要决策是如何部署 Microsoft Lync：在本地使用 Lync Server 2013，或在云中使用 Microsoft Office 365 的 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="ad522-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="ad522-105">**Lync Server 2013 本地**版：此选择提供完整的 Lync 功能集，并在配置、自定义和操作部署方面提供了极大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="ad522-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="ad522-106">所有服务器都是现场安装的，并且由您的组织进行维护。</span><span class="sxs-lookup"><span data-stu-id="ad522-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="ad522-107">本地部署提供了所有的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="ad522-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="ad522-108">**云中的 Lync Online**Lync Online 专为希望提供基于云的即时消息、状态和会议的成本和灵活性优势而不牺牲 Lync Server 的业务类功能的组织而设计。</span><span class="sxs-lookup"><span data-stu-id="ad522-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="ad522-109">借助 Lync Online，Microsoft 将部署和维护所需的服务器基础结构，并处理日常维护、修补程序和升级。</span><span class="sxs-lookup"><span data-stu-id="ad522-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="ad522-110">本地部署中提供的某些功能在 Lync Online 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ad522-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="ad522-111">最适合您的部署类型取决于您要部署的工作负载，以及您组织的地理位置和业务状态。</span><span class="sxs-lookup"><span data-stu-id="ad522-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="ad522-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ad522-112">Lync Server</span></span>

<span data-ttu-id="ad522-113">本地 Lync Server 部署最适合以下方案：</span><span class="sxs-lookup"><span data-stu-id="ad522-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="ad522-114">**完整的企业语音功能**   如果您计划部署完整的企业语音解决方案以替换 PBX 或使用高级呼叫功能，则需要本地 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="ad522-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="ad522-115">本地部署支持与 PBX 系统和中继的直接连接以及高级电话功能（如响应组和呼叫寄存）。</span><span class="sxs-lookup"><span data-stu-id="ad522-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="ad522-116">Lync Online 目前不支持这些功能。</span><span class="sxs-lookup"><span data-stu-id="ad522-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="ad522-117">**媒体质量控制**   如果您希望完全范围的媒体质量保证功能（如呼叫允许控制（CAC）和服务质量（QoS）功能），您需要本地部署。</span><span class="sxs-lookup"><span data-stu-id="ad522-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="ad522-118">**持久聊天**   如果需要为您的组织部署持久聊天，则必须选择本地部署。</span><span class="sxs-lookup"><span data-stu-id="ad522-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="ad522-119">**第三方服务器应用程序**   仅本地部署可以与使用 Microsoft 统一通信托管 API （UCMA）的受信任的第三方应用程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="ad522-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="ad522-120">**需要区域支持**   的多国家/地区公司如果您有多个国家或地区的数据中心，并且需要在区域的基础上部署和管理服务器，则本地部署是最佳的，因为它提供了这种类型的区域管理功能。</span><span class="sxs-lookup"><span data-stu-id="ad522-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="ad522-121">**对策略、报告和升级**   的完全控制在本地 Lync Server 部署中，您可以访问一组完整的服务器和客户端策略、监视和其他报告以及升级的时间。</span><span class="sxs-lookup"><span data-stu-id="ad522-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="ad522-122">Lync Online 提供了策略设置和报告的子集，并提供了用于接受升级的有限但有效的窗口。</span><span class="sxs-lookup"><span data-stu-id="ad522-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="ad522-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="ad522-123">Lync Online</span></span>

<span data-ttu-id="ad522-124">如果以上列表中的所有因素对您都不重要，您可能需要选择 Lync Online 来实现更简单的部署和管理。</span><span class="sxs-lookup"><span data-stu-id="ad522-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="ad522-125">Lync Online 提供了强健的 IM、状态和会议功能集，还允许在组织中的用户之间通过 IP 进行语音和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad522-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

