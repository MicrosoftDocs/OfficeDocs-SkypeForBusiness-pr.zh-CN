---
title: 适合于 Lync Server 2010 的服务器设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑该计算机的属性，请执行以下操作：
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215693"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8a559-103">适合于 Lync Server 2010 的服务器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="8a559-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="8a559-104">若要编辑该计算机的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8a559-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="8a559-p101">编辑该计算机的“完全限定的域名(FQDN)”\*\*\*\*。此条目必须与域名系统 (DNS) 以及与该计算机关联的证书的使用者替代名称 (SAN) 或使用者名称 (SN) 中定义的计算机名匹配。</span><span class="sxs-lookup"><span data-stu-id="8a559-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="8a559-107">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="8a559-107">You select one of the following:</span></span>
    
    <span data-ttu-id="8a559-108">**使用所有已配置的 IP 地址**：选择此选项可使用计算机上所有已配置的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a559-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a559-p102">如果计算机具有多个 IP 地址，则必须意识到与该计算机关联的服务将所有的 IP 地址用于所有服务。如果某个侦听服务器或服务期待特定 IP 地址和端口的通信，则该服务可能无法选择用于侦听的最佳 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a559-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="8a559-p103">**将服务用途限制为所选 IP 地址**：如果要为该计算机在其上侦听来自部署中其他计算机和池的通信的“主 IP 地址”\*\*\*\* 定义特定的 IP 地址，则选择此选项。为计算机和服务将在其上侦听通信并将通信发送至定义的 PSTN 网关或 IP-PBX 的特定 IP 地址定义“PSTN IP 地址”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8a559-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

