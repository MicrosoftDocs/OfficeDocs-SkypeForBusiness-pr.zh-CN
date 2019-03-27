---
title: 适合于 Lync Server 2010 的服务器设置扩展器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑该计算机的属性，请执行以下操作：
ms.openlocfilehash: 4b05c52d92d3702c76afd6c7b682c1c9ffda7ab9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879719"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9a729-103">适合于 Lync Server 2010 的服务器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="9a729-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="9a729-104">若要编辑该计算机的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9a729-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="9a729-105">编辑**完全限定域名 (FQDN)** 为此计算机。</span><span class="sxs-lookup"><span data-stu-id="9a729-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="9a729-106">此条目必须与它被定义在域名系统 (DNS) 和使用者替代名称 (SAN) 或使用者名称 (SN) 与该计算机关联的证书匹配的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="9a729-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="9a729-107">您选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="9a729-107">You select one of the following:</span></span>
    
    <span data-ttu-id="9a729-108">**使用所有已配置的 IP 地址**： 选择此选项可在计算机上使用所有已配置的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9a729-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9a729-109">如果计算机有多个 IP 地址，必须注意与该计算机关联的服务，将使用的所有服务的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9a729-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="9a729-110">如果侦听服务器或服务预期的特定的 IP 地址和端口的通信，服务可能不进行侦听的 IP 地址的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="9a729-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="9a729-111">**将服务使用率限制为所选的 IP 地址**： 选择此选项，如果您想要定义特定 IP 地址从其他计算机和池部署中的通信将侦听此计算机的**主 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="9a729-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="9a729-112">为特定的 IP 地址的计算机和服务将侦听的通信和发送到定义 PSTN 网关或 IP PBX 的通信，定义**PSTN IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="9a729-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

