---
title: Lync Server 2013： IP 手机的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="baf80-102">Lync Server 2013 中的 IP 电话拓扑</span><span class="sxs-lookup"><span data-stu-id="baf80-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf80-103">_**主题上次修改时间：** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="baf80-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="baf80-104">本部分概述了连接过程，并介绍了 IP 电话在内部和外部网络中的连接方式之间的区别。</span><span class="sxs-lookup"><span data-stu-id="baf80-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="baf80-105">Lync Server 支持下列 IP 电话： Aastra 6721ip 常见的区域电话、Aastra 6725ip 桌面电话、HP 4110 IP 电话（通用区域电话）、HP 4120 IP 电话（桌面电话）、Polycom CX600 ip 桌面电话、Polycom CX700 IP 桌面电话、Polycom CX500 IP常见的区域电话和 Polycom CX3000 IP 会议电话。</span><span class="sxs-lookup"><span data-stu-id="baf80-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="baf80-106">在这些电话中，除 Polycom CX700 之外的所有其他设备都可以运行 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="baf80-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="baf80-107">下图介绍了企业环境中的设备连接所涉及的所有组件。</span><span class="sxs-lookup"><span data-stu-id="baf80-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="baf80-108">**内部拓扑**</span><span class="sxs-lookup"><span data-stu-id="baf80-108">**Internal Topology**</span></span>

<span data-ttu-id="baf80-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="baf80-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="baf80-110">上图是逻辑表示形式，而不是物理概述。</span><span class="sxs-lookup"><span data-stu-id="baf80-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="baf80-111">例如，Active Directory 域服务（AD DS）很少与任何 Lync 服务器组件位于同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="baf80-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="baf80-112">用户存储可以位于后端服务器或存档和监视服务器上。</span><span class="sxs-lookup"><span data-stu-id="baf80-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="baf80-113">Lync Server Management Shell、web 服务器和更新服务均为前端服务器角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="baf80-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="baf80-114">下图简要介绍了设备位于公司网络外部时所涉及的组件。</span><span class="sxs-lookup"><span data-stu-id="baf80-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="baf80-115">**外部拓扑**</span><span class="sxs-lookup"><span data-stu-id="baf80-115">**External Topology**</span></span>

<span data-ttu-id="baf80-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="baf80-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="baf80-117">设备更新 Web 服务提供外部和内部网站，但仅在此处显示外部网站。</span><span class="sxs-lookup"><span data-stu-id="baf80-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="baf80-118">如果启用外部访问，则注册机构和设备更新 Web 服务的 URL 的位置必须在 DNS 中发布。</span><span class="sxs-lookup"><span data-stu-id="baf80-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="baf80-119">此外，还必须部署和正确配置边缘服务器，以便允许从设备到公司环境的外部通信。</span><span class="sxs-lookup"><span data-stu-id="baf80-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="baf80-120">这将从以前的图表中省略，因为 Edge 部署并非特定于设备连接。</span><span class="sxs-lookup"><span data-stu-id="baf80-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

