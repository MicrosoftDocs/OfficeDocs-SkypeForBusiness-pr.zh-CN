---
title: 边缘设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：
ms.openlocfilehash: 23162ee4100c077d072d6cc1d72946059611ce7f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889159"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="eb1f7-103">边缘设置扩展器</span><span class="sxs-lookup"><span data-stu-id="eb1f7-103">Edge Settings Expander</span></span>

<span data-ttu-id="eb1f7-104">要编辑包含单个或多个服务器的现有边缘池的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="eb1f7-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="eb1f7-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-105">General settings</span></span>

- <span data-ttu-id="eb1f7-106">下一个跃点选择设置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-106">Next hop selection settings</span></span>

- <span data-ttu-id="eb1f7-107">边缘服务器配置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="eb1f7-108">常规设置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-108">General settings</span></span>

<span data-ttu-id="eb1f7-p101">边缘服务器池的内部池完全限定域名 (FQDN)。编辑池的 FQDN 以更改此设置。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="eb1f7-111">如果您将设置与 Lync Server 2013 的联盟 Microsoft Lync Server 2010 或 Microsoft Office Communications Server 2007 R2 的受信任的合作伙伴，请选择**为此边缘池 (端口 5061) 启用联盟**复选框。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="eb1f7-112">选中“**为此边缘池启用 XMPP 联盟**”可启用 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="eb1f7-113">为“**内部配置复制端口 (HTTPS)**”指定端口号。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="eb1f7-114">下一个跃点选择设置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-114">Next hop selection settings</span></span>

<span data-ttu-id="eb1f7-115">要设置或修改边缘服务器将用于与内部基础结构通信的“**下一个跃点池**”，请从下拉列表框中选择控制器、控制器池、前端服务器或前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="eb1f7-116">只有控制器或前端已配置拓扑生成器中将显示选定内容。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="eb1f7-117">边缘服务器配置</span><span class="sxs-lookup"><span data-stu-id="eb1f7-117">Edge Server configuration</span></span>

<span data-ttu-id="eb1f7-118">要编辑或指定边缘服务器的“**外部设置**”的设置，首先必须确定 SIP 访问、Web 会议和音频/视频服务是否要使用单独的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="eb1f7-p103">如果它们都要使用单独的 IP 地址，请选中“**为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址**”复选框。每个服务必须具有为其创建的对应 DNS 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="eb1f7-p104">对于每个面向外部的服务，指定 FQDN 和关联端口。例如，“**SIP 访问**”将使用 sip.contoso.com 和关联端口 5061。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb1f7-p105">如果为每个面向外部的服务选择单独的 FQDN，则每个服务必须具有与其关联的唯一端口值。默认情况下，SIP 使用端口 5061/TLS，Web 会议边缘服务使用端口 444/TLS，A/V 会议服务器使用端口 443/TLS。如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="eb1f7-p106">如果确定组织要为面向外部的服务使用单个 FQDN 和 IP 地址，请清除“**为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址**”复选框。然后，可以编辑“**SIP 访问**”池 FQDN 和端口值（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb1f7-128">如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb1f7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb1f7-129">See also</span></span>

<span data-ttu-id="eb1f7-130">有关定义和配置边缘服务设置的详细信息，请参阅[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eb1f7-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


