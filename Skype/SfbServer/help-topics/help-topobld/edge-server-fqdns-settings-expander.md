---
title: 边缘服务器 FQDN 设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: 若要编辑或指定边缘服务器的外部设置，首先必须确定是否对会话初始协议 (SIP) 访问、Web 会议边缘服务和音频/视频边缘服务使用单独的 IP 地址。
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095557"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="1321f-103">边缘服务器 FQDN 设置扩展器</span><span class="sxs-lookup"><span data-stu-id="1321f-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="1321f-104">若要编辑或指定边缘服务器的外部设置，首先必须确定是否对会话初始协议 (SIP) 访问、Web 会议边缘服务和音频/视频边缘服务使用单独的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1321f-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="1321f-p101">如果它们都要使用单独的 IP 地址，请选中 **“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”** 复选框。每个服务必须具有为其创建的对应域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="1321f-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="1321f-p102">对于每个面向外部的服务，指定完全限定的域名 (FQDN) 和关联端口。例如，对于“SIP 访问”，可以使用 sip.contoso.com 和关联端口 5061。</span><span class="sxs-lookup"><span data-stu-id="1321f-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1321f-p103">如果为每个面向外部的服务选择单独的 FQDN，则每个服务必须具有与其关联的唯一端口值。默认情况下，SIP 使用端口 5061/TLS，Web 会议边缘服务使用端口 444/TLS，A/V 会议边缘服务使用端口 443/TLS。如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="1321f-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="1321f-p104">如果确定组织要为面向外部的服务使用单个 FQDN 和 IP 地址，请清除“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。然后，可以编辑“SIP 访问”池 FQDN 和端口值（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="1321f-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1321f-114">如果对这些设置进行任何更改，包括使用单独的 FQDN 和 IP 地址或端口，则必须更新将依赖最初配置的值的其他所有服务。</span><span class="sxs-lookup"><span data-stu-id="1321f-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="1321f-115">有关定义和配置边缘服务设置的详细信息，请参阅 [定义边缘拓扑](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="1321f-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>