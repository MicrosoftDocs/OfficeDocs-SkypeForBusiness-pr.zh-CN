---
title: Lync Server 2013：在位于外围网络外部的观察程序节点上安装证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="46b64-102">在 Lync Server 2013 外围网络外部的观察程序节点上安装证书</span><span class="sxs-lookup"><span data-stu-id="46b64-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46b64-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="46b64-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="46b64-104">在外围网络中运行的 System Center Operations Manager 代理（如 Lync Server Edge 服务器），企业外部（如外部综合事务观察程序节点）或跨 Active Directory 域服务信任边界可能需要配置 System Center Operations Manager 网关服务器。</span><span class="sxs-lookup"><span data-stu-id="46b64-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="46b64-105">此服务器角色允许与根管理服务器没有信任关系的代理发出警报。</span><span class="sxs-lookup"><span data-stu-id="46b64-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="46b64-106">有关详细信息，请参阅位于[http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)的 System Center Operations Manager TechNet Library 中的 "管理 Operations manager 2007 中的网关服务器"。</span><span class="sxs-lookup"><span data-stu-id="46b64-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="46b64-107">如果在其中一个位置中部署代理，则还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。</span><span class="sxs-lookup"><span data-stu-id="46b64-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="46b64-108">为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。</span><span class="sxs-lookup"><span data-stu-id="46b64-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="46b64-109">有关详细信息和下载这些实用程序的详细信息，请参阅中的 "使用证书生成向导获取用于非域加入代理的证书" [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)。中的博客文章。</span><span class="sxs-lookup"><span data-stu-id="46b64-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

