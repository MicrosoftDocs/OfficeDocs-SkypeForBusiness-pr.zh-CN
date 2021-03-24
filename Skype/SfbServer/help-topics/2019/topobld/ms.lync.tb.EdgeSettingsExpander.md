---
title: 边缘设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：
ms.openlocfilehash: c887ffaa16818e377035109632871b7bc7ed25d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108798"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="06599-103">边缘设置扩展器</span><span class="sxs-lookup"><span data-stu-id="06599-103">Edge Settings Expander</span></span>

<span data-ttu-id="06599-104">要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="06599-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="06599-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="06599-105">General settings</span></span>

- <span data-ttu-id="06599-106">下一个跃点选择设置</span><span class="sxs-lookup"><span data-stu-id="06599-106">Next hop selection settings</span></span>

- <span data-ttu-id="06599-107">边缘服务器配置</span><span class="sxs-lookup"><span data-stu-id="06599-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="06599-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="06599-108">General settings</span></span>

<span data-ttu-id="06599-p101">边缘服务器池的内部池完全限定域名 (FQDN)。编辑池的 FQDN 以更改此设置。</span><span class="sxs-lookup"><span data-stu-id="06599-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="06599-111">如果要设置与 Skype for Business Server 2015 服务器的联盟，请选中 (端口 **5061**) 为此边缘池启用联盟复选框。</span><span class="sxs-lookup"><span data-stu-id="06599-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="06599-112">为“内部配置复制端口(HTTPS)”指定端口号。</span><span class="sxs-lookup"><span data-stu-id="06599-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="06599-113">下一个跃点选择设置</span><span class="sxs-lookup"><span data-stu-id="06599-113">Next hop selection settings</span></span>

<span data-ttu-id="06599-114">若要设置或修改边缘服务器用于与内部基础结构通信的"下一个跃点池"，请从下拉列表框中选择控制器、控制器池、前端服务器或前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="06599-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="06599-115">只有已在拓扑生成器中配置的控制器或前端会进行选择。</span><span class="sxs-lookup"><span data-stu-id="06599-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="06599-116">边缘服务器配置</span><span class="sxs-lookup"><span data-stu-id="06599-116">Edge Server configuration</span></span>

<span data-ttu-id="06599-117">要编辑或指定边缘服务器的“外部设置”的设置，首先必须确定 SIP 访问、Web 会议和音频/视频服务是否要使用单独的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="06599-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="06599-p103">如果它们都要使用单独的 IP 地址，请选中“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。每个服务必须具有为其创建的对应 DNS 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="06599-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="06599-p104">对于每个面向外部的服务，指定 FQDN 和关联端口。例如，“SIP 访问”将使用 sip.contoso.com 和关联端口 5061。</span><span class="sxs-lookup"><span data-stu-id="06599-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06599-122">如果为每个面向外部的服务选择单独的 FQDN，则每个服务必须具有与其关联的唯一端口值。</span><span class="sxs-lookup"><span data-stu-id="06599-122">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="06599-123">默认情况下，SIP 在端口 5061/TLS 上，Web 会议边缘服务在端口 444/TLS 上，A/V 会议服务器在端口 443/TLS 上。</span><span class="sxs-lookup"><span data-stu-id="06599-123">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="06599-124">如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="06599-124">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="06599-p106">如果确定组织要为面向外部的服务使用单个 FQDN 和 IP 地址，请清除“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。然后，可以编辑“SIP 访问”池 FQDN 和端口值（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="06599-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06599-127">如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="06599-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="06599-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06599-128">See also</span></span>

<span data-ttu-id="06599-129">有关定义和配置边缘服务设置的详细信息，请参阅[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="06599-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>