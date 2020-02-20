---
title: Lync Server 2013：部署移动性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying mobility
ms:assetid: f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690055(v=OCS.15)
ms:contentKeyID: 48185805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b7449da84f2e810fe6ec4d2fd199d2daba56160
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="863c3-102">在 Lync Server 2013 中部署移动功能</span><span class="sxs-lookup"><span data-stu-id="863c3-102">Deploying mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="863c3-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="863c3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="863c3-104">当您部署 Lync Server 2013 移动功能时，移动用户可以使用支持的移动设备进行 Lync 功能，如即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="863c3-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="863c3-105">有关部署移动功能的要求的详细信息，请参阅[在 Lync Server 2013 中规划移动](lync-server-2013-planning-for-mobility.md)功能。</span><span class="sxs-lookup"><span data-stu-id="863c3-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="863c3-106">本节将指导您完成部署和验证移动功能和自动发现功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="863c3-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="863c3-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="863c3-107">In This Section</span></span>

  - [<span data-ttu-id="863c3-108">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="863c3-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="863c3-109">在 Lync Server 2013 中修改证书的移动性</span><span class="sxs-lookup"><span data-stu-id="863c3-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="863c3-110">在 Lync Server 2013 中配置反向代理以实现移动功能</span><span class="sxs-lookup"><span data-stu-id="863c3-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="863c3-111">在 Lync Server 2013 中配置自动发现以实现与混合部署的移动性</span><span class="sxs-lookup"><span data-stu-id="863c3-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="863c3-112">在 Lync Server 2013 中验证移动性部署</span><span class="sxs-lookup"><span data-stu-id="863c3-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="863c3-113">在 Lync Server 2013 中配置推送通知</span><span class="sxs-lookup"><span data-stu-id="863c3-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="863c3-114">在 Lync Server 2013 中配置移动策略</span><span class="sxs-lookup"><span data-stu-id="863c3-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

