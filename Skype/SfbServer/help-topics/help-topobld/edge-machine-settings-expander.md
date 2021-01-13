---
title: 边缘计算机设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 要编辑边缘服务器池中的服务器的属性，请执行以下操作：
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807122"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="2eb42-103">边缘计算机设置扩展器</span><span class="sxs-lookup"><span data-stu-id="2eb42-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="2eb42-104">要编辑边缘服务器池中的服务器的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2eb42-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="2eb42-p101">通过编辑完全限定域名 (FQDN)，可更改“内部名称或 FQDN”。FQDN 必须与域名系统 (DNS) 主机 (A) 记录以及分配给服务器的内部边缘网络接口的证书使用者名称相匹配。“内部 IP 地址”的值定义分配给定义为内部网络（与外围网络设计相对）的网络接口的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="2eb42-p102">对话框的以下三部分定义此边缘服务器的外部配置的 IP 地址。更改 IP 地址的功能受边缘服务器池级别“属性”设置上的“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置的影响。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="2eb42-110">SIP 访问</span><span class="sxs-lookup"><span data-stu-id="2eb42-110">SIP Access</span></span>

<span data-ttu-id="2eb42-p103">编辑分配给会话初始协议 (SIP) 访问的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2eb42-113">如果已启用池设置页上的“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置，则只能编辑 SIP 访问的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2eb42-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="2eb42-114">Web 会议</span><span class="sxs-lookup"><span data-stu-id="2eb42-114">Web Conferencing</span></span>

<span data-ttu-id="2eb42-p104">编辑分配给 Web 会议的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="2eb42-117">音频/视频</span><span class="sxs-lookup"><span data-stu-id="2eb42-117">Audio/Video</span></span>

<span data-ttu-id="2eb42-p105">编辑分配给音频/视频 (A/V) 的网络接口的外部 IP 地址。此 IP 地址可以是公用 IP 地址或专用 IP 地址范围中的地址。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="2eb42-p106">一般情况下，“已使用的启用了 NAT 的公用 IP 地址”的设置是供 A/V 网络接口或边缘服务器的外部接口使用的公用地址。如果启用“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”设置，则此公用 IP 地址将用于所有三个外部接口。</span><span class="sxs-lookup"><span data-stu-id="2eb42-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

