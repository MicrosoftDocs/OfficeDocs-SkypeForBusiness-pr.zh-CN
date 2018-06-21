---
title: 边缘计算机设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要编辑边缘服务器池中的服务器的属性，请执行以下操作：
ms.openlocfilehash: 3570675fd82512aa25d760c2380f05a2de80cec6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990194"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="8854a-103">边缘计算机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="8854a-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="8854a-104">若要编辑边缘服务器池中的服务器的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8854a-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="8854a-105">通过编辑的完全限定的域名 (FQDN)，可以更改的**内部名称或 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="8854a-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="8854a-106">域名系统 (DNS) 主机 (A) 记录，并分配给服务器的内部边缘的网络接口的证书的使用者名称必须匹配的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8854a-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="8854a-107">**内部 IP 地址**的值定义分配定义为相对于外围网络设计内部网络的网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="8854a-108">对话框中的下一步三个部分定义此边缘服务器的外部配置的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="8854a-109">若要更改的 IP 地址的能力受设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**在边缘服务器的属性设置在池级别。</span><span class="sxs-lookup"><span data-stu-id="8854a-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="8854a-110">SIP 访问</span><span class="sxs-lookup"><span data-stu-id="8854a-110">SIP Access</span></span>

<span data-ttu-id="8854a-111">编辑分配给会话初始协议 (SIP) 访问的网络接口的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="8854a-112">此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8854a-113">如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**池上设置页上启用，则仅 SIP 访问的 IP 地址将可供编辑。</span><span class="sxs-lookup"><span data-stu-id="8854a-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="8854a-114">Web 会议</span><span class="sxs-lookup"><span data-stu-id="8854a-114">Web Conferencing</span></span>

<span data-ttu-id="8854a-115">编辑分配给 web 会议的网络接口的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="8854a-116">此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="8854a-117">音频/视频</span><span class="sxs-lookup"><span data-stu-id="8854a-117">Audio/Video</span></span>

<span data-ttu-id="8854a-118">编辑分配给音频/视频的网络接口的外部 IP 地址 (A / V)。</span><span class="sxs-lookup"><span data-stu-id="8854a-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="8854a-119">此 IP 地址可以是公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="8854a-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="8854a-120">**启用公共 IP 地址使用 NAT**的设置是公共地址的外部接口用于任一 A / V 通常网络接口或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="8854a-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="8854a-121">如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**已启用，此公用 IP 地址用于所有三个外部接口。</span><span class="sxs-lookup"><span data-stu-id="8854a-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

