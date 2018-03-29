---
title: 边缘机设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要编辑的属性中的边缘服务器池的服务器，执行以下操作：
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="02259-103">边缘机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="02259-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="02259-104">若要编辑的属性中的边缘服务器池的服务器，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02259-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="02259-105">通过编辑的完全合格的域名称 (FQDN)，可以更改**内部名称或 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="02259-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="02259-106">域名系统 (DNS) 主机 (A) 记录，并分配给服务器的内部边缘网络接口的证书的接受方名称必须匹配 FQDN。</span><span class="sxs-lookup"><span data-stu-id="02259-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="02259-107">**内部 IP 地址**的值定义为分配定义为内部网络，相对于外围网络设计的网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02259-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="02259-108">对话框中的三个部分定义的外部边缘服务器配置的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02259-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="02259-109">更改 IP 地址的能力受设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**属性设置在边缘服务器上池级别。</span><span class="sxs-lookup"><span data-stu-id="02259-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="02259-110">SIP 访问</span><span class="sxs-lookup"><span data-stu-id="02259-110">SIP Access</span></span>

<span data-ttu-id="02259-111">编辑分配给网络接口为会话启动协议 (SIP) 访问的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="02259-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="02259-112">此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02259-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02259-113">如果该设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**池上设置启用页，仅为 SIP 访问的 IP 地址可供编辑。</span><span class="sxs-lookup"><span data-stu-id="02259-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="02259-114">Web 会议</span><span class="sxs-lookup"><span data-stu-id="02259-114">Web Conferencing</span></span>

<span data-ttu-id="02259-115">编辑外部 IP 地址分配给网络接口的网络会议。</span><span class="sxs-lookup"><span data-stu-id="02259-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="02259-116">此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02259-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="02259-117">音频/视频</span><span class="sxs-lookup"><span data-stu-id="02259-117">Audio/Video</span></span>

<span data-ttu-id="02259-118">编辑外部 IP 地址分配给网络接口的音频/视频 (A / V)。</span><span class="sxs-lookup"><span data-stu-id="02259-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="02259-119">此 IP 地址可以是一个公共 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="02259-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="02259-120">**使用的公用 IP 地址启用 NAT**的设置是通过外部接口用于建立的公用地址 / V 一般网络接口或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="02259-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="02259-121">如果设置**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**已启用，此公用 IP 地址用于所有三个外部接口。</span><span class="sxs-lookup"><span data-stu-id="02259-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

