---
title: PSTN 网关设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：
ms.openlocfilehash: b083fa22d84cdd6adf8a9636a522c5c34a732ee3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684455"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="7274f-103">PSTN 网关设置扩展器</span><span class="sxs-lookup"><span data-stu-id="7274f-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="7274f-104">若要编辑或修改公用电话交换网 (PSTN) 网关的设置，请修改以下字段：</span><span class="sxs-lookup"><span data-stu-id="7274f-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="7274f-105">网关 FQDN 或 IP 地址是必需条目，按照域名系统 (DNS) 主机 (A) 记录、静态 HOSTS 文件条目或 PSTN 网关的 IP 地址的定义，定义 PSTN 网关的“**完全限定域名 (FQDN)**”。</span><span class="sxs-lookup"><span data-stu-id="7274f-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="7274f-p101">SIP 传输协议可以是传输控制协议 (TCP)，也可以是传输层安全性 (TLS)。TLS 为默认选项。有关网关所支持的选项，请参考网关供应商文档。默认为 TLS，且如果网关支持 TLS，则应将其视为更安全的选择。</span><span class="sxs-lookup"><span data-stu-id="7274f-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="7274f-110">选择是否为网关启用 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="7274f-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="7274f-111">**备用媒体 IP 地址**是中介服务器的定义，其中部署的 PSTN 网关的媒体流量与默认配置的 ip 地址（通常专用于 SIP 流量）具有不同的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="7274f-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="7274f-112">如果定义此参数，则 PSTN 网关为媒体提供不同的网络接口或路径支持。</span><span class="sxs-lookup"><span data-stu-id="7274f-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="7274f-113">如果此地址留空，则 PSTN 网关不支持媒体的备用路径。</span><span class="sxs-lookup"><span data-stu-id="7274f-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

