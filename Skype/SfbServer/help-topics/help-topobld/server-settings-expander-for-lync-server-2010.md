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
- NOCSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要编辑此计算机的属性，请执行以下操作：
ms.openlocfilehash: 0f8a1a31c593c792ff4872d0e104c6aadabcd819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819294"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="6f45f-103">适合于 Lync Server 2010 的服务器设置扩展器</span><span class="sxs-lookup"><span data-stu-id="6f45f-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="6f45f-104">若要编辑此计算机的属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6f45f-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="6f45f-105">编辑此计算机的**完全限定的域名（FQDN）** 。</span><span class="sxs-lookup"><span data-stu-id="6f45f-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="6f45f-106">此条目必须匹配在域名系统（DNS）中定义的计算机名称，以及与此计算机关联的证书的 "使用者备用名称（SAN）" 或 "使用者名称（SN）"。</span><span class="sxs-lookup"><span data-stu-id="6f45f-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="6f45f-107">选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6f45f-107">You select one of the following:</span></span>
    
    <span data-ttu-id="6f45f-108">**使用所有配置的 ip 地址**：选择此项可使用计算机上配置的所有 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="6f45f-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6f45f-109">如果计算机有多个 IP 地址，则必须注意与此计算机关联的服务将对所有服务使用所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6f45f-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="6f45f-110">如果侦听服务器或服务需要通信特定的 IP 地址和端口，则该服务可能无法最佳选择要在哪个 IP 地址上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="6f45f-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="6f45f-111">**将服务使用限制为选定的 IP 地址**：如果你想要为此计算机侦听的用于从其他计算机和部署中的其他计算机和池通信的**主 ip 地址**定义特定 ip 地址，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6f45f-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="6f45f-112">为计算机和服务侦听通信的特定 IP 地址定义**PSTN IP 地址**，并将通信发送到已定义的 PSTN 网关或 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="6f45f-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

