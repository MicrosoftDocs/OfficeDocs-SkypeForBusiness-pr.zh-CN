---
title: Lync Server 2013：为音频会议提供商配置联盟
description: Lync Server 2013：为音频会议提供商配置联盟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553318"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="02a27-103">在 Lync Server 2013 中为音频会议提供商配置联盟</span><span class="sxs-lookup"><span data-stu-id="02a27-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02a27-104">_**上次修改的主题：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="02a27-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="02a27-105">如果要在混合 (部署中使用音频会议提供商 (ACP) 与 Lync Online) 的 Lync Server 本地，则需要在本地 Lync 部署和 ACP 合作伙伴之间配置联盟，作为允许的合作伙伴服务器。</span><span class="sxs-lookup"><span data-stu-id="02a27-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="02a27-106">您可以通过添加 ACP 合作伙伴域和边缘服务器来配置联合 (这也可能称为 "访问代理) 到本地部署的联盟域列表"。</span><span class="sxs-lookup"><span data-stu-id="02a27-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="02a27-107">然后，您的 ACP 合作伙伴需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。</span><span class="sxs-lookup"><span data-stu-id="02a27-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="02a27-108">请与您的 ACP 提供商联系，以获取其他 detailsYour ACP 合作伙伴，然后需要将本地边缘服务器池的 FQDN 添加到其允许的联盟域列表中。</span><span class="sxs-lookup"><span data-stu-id="02a27-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="02a27-109">**将 ACP 域和边缘服务器添加为允许的联盟域**</span><span class="sxs-lookup"><span data-stu-id="02a27-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="02a27-110">若要将 ACP 域添加为允许的伙伴服务器 (允许的联盟域) ，请按照 [Configure support for External domain In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="02a27-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="02a27-111">对于边缘服务器，添加 ACP 合作伙伴的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="02a27-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="02a27-112">您可能需要与您的 ACP 合作伙伴联系，以获取其边缘服务器的 FQDN，而您的 ACP 也可能将其称为访问代理。</span><span class="sxs-lookup"><span data-stu-id="02a27-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="02a27-113">**向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="02a27-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="02a27-114">ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加为允许的联盟域，从而配置联合以将您的本地域作为允许的合作伙伴服务器添加。</span><span class="sxs-lookup"><span data-stu-id="02a27-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

