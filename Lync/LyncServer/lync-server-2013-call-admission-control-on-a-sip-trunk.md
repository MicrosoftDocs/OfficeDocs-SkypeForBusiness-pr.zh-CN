---
title: Lync Server 2013：SIP 中继上的呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8196070bbb7992aed915cf188d67e95912524a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="00e9c-102">Lync Server 2013 中 SIP 中继上的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="00e9c-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00e9c-103">_**主题上次修改时间：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="00e9c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="00e9c-p101">要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。</span><span class="sxs-lookup"><span data-stu-id="00e9c-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="00e9c-106">下图显示 SIP 中继上的 CAC 部署示例。</span><span class="sxs-lookup"><span data-stu-id="00e9c-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="00e9c-107">**SIP 中继上的 CAC 配置**</span><span class="sxs-lookup"><span data-stu-id="00e9c-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="00e9c-108">![呼叫允许控制 SIP 中继图](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "呼叫允许控制 SIP 中继图")</span><span class="sxs-lookup"><span data-stu-id="00e9c-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="00e9c-109">要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="00e9c-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="00e9c-110">创建一个网络站点，代表 ITSP。</span><span class="sxs-lookup"><span data-stu-id="00e9c-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="00e9c-111">将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。</span><span class="sxs-lookup"><span data-stu-id="00e9c-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="00e9c-112">有关详细信息，请参阅部署文档中的[Lync Server 2013 中的 CAC 的 "配置网络站点](lync-server-2013-configure-network-sites-for-cac.md)"。</span><span class="sxs-lookup"><span data-stu-id="00e9c-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00e9c-113">对于 ITSP，该网络站点配置不起作用。</span><span class="sxs-lookup"><span data-stu-id="00e9c-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="00e9c-114">带宽策略值实际是在步骤 2 中应用。</span><span class="sxs-lookup"><span data-stu-id="00e9c-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="00e9c-115">使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。</span><span class="sxs-lookup"><span data-stu-id="00e9c-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="00e9c-116">例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。</span><span class="sxs-lookup"><span data-stu-id="00e9c-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="00e9c-117">有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="00e9c-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="00e9c-118">另请参阅 CsNetworkInterSitePolicy cmdlet 的 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="00e9c-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="00e9c-119">从 ITSP 获取会话边界控制器 (SCB) 的媒体端点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="00e9c-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="00e9c-120">将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。</span><span class="sxs-lookup"><span data-stu-id="00e9c-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="00e9c-121">有关详细信息，请参阅[在 Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="00e9c-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

