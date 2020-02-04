---
title: Edge 机器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要在边缘服务器池中编辑服务器的属性，请执行下列操作：
ms.openlocfilehash: aeb9c48968b7b5223ac33fc3419d630229724a09
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697477"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="02083-103">Edge 机器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="02083-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="02083-104">若要在边缘服务器池中编辑服务器的属性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="02083-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="02083-105">通过编辑完全限定的域名（FQDN），可以更改**内部名称或 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="02083-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="02083-106">FQDN 必须与域名系统（DNS）主机（A）记录和分配给服务器内部 Edge 网络接口的证书的使用者名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="02083-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="02083-107">"**内部 IP 地址**" 的值定义了分配网络接口的 IP 地址，该地址是定义为内部网络的网络接口（相对于外围网络设计）。</span><span class="sxs-lookup"><span data-stu-id="02083-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="02083-108">对话框的接下来三个部分定义了此边缘服务器的外部配置的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02083-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="02083-109">更改 IP 地址的功能受此设置的影响在边缘服务器池级别的属性设置上**为 web 会议和 A/V 启用单独的 FQDN 和 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="02083-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="02083-110">SIP 访问</span><span class="sxs-lookup"><span data-stu-id="02083-110">SIP Access</span></span>

<span data-ttu-id="02083-111">编辑分配给用于会话初始协议（SIP）访问的网络接口的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02083-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="02083-112">此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02083-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02083-113">如果在启用了 "池设置" 页面上的 "**为 web 会议和 A/V 单独的 FQDN 和 IP 地址**" 设置，则只有 SIP 访问的 IP 地址才可供编辑。</span><span class="sxs-lookup"><span data-stu-id="02083-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="02083-114">Web 会议</span><span class="sxs-lookup"><span data-stu-id="02083-114">Web Conferencing</span></span>

<span data-ttu-id="02083-115">编辑分配给 web 会议网络接口的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02083-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="02083-116">此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02083-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="02083-117">音频/视频</span><span class="sxs-lookup"><span data-stu-id="02083-117">Audio/Video</span></span>

<span data-ttu-id="02083-118">编辑分配给音频/视频的网络接口的外部 IP 地址（A/V）。</span><span class="sxs-lookup"><span data-stu-id="02083-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="02083-119">此 IP 地址可以是公共 IP 地址，也可以是专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02083-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="02083-120">**使用支持 NAT 的公共 IP 地址**的设置是由 A/V 网络接口或边缘服务器使用的外部接口的公共地址。</span><span class="sxs-lookup"><span data-stu-id="02083-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="02083-121">如果设置为**web 会议和 A/V 启用了单独的 FQDN 和 IP 地址**，则此公共 IP 地址将用于所有三个外部接口。</span><span class="sxs-lookup"><span data-stu-id="02083-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

