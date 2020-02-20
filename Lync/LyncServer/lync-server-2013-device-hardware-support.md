---
title: Lync Server 2013 设备硬件支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="864a5-102">Lync Server 2013 中的设备硬件支持</span><span class="sxs-lookup"><span data-stu-id="864a5-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="864a5-103">_**上次修改的主题：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="864a5-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="864a5-104">特定的硬件配置到位后，才能部署 IP 电话和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="864a5-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="864a5-105">运行 Lync Phone Edition 的 IP 电话支持链接层发现协议-媒体终结点发现（LLDP-MED-V）和以太网供电（PoE）。</span><span class="sxs-lookup"><span data-stu-id="864a5-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="864a5-106">要使用 LLDP-MED，交换机必须支持 IEEE802.1AB 和 ANSI/TIA-1057。</span><span class="sxs-lookup"><span data-stu-id="864a5-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="864a5-107">要使用 PoE，交换机必须支持 PoE802.3AF 或 802.3at。</span><span class="sxs-lookup"><span data-stu-id="864a5-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="864a5-108">要启用 LLDP-MED，管理员必须使用交换机控制台窗口启用 LLDP，并使用正确的语音 VLAN ID 设置 LLDP-MED 网络策略。</span><span class="sxs-lookup"><span data-stu-id="864a5-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="864a5-109">此外，如果您的部署包括模拟设备，则必须将模拟网关配置为使用 Lync Server，并且网关必须是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="864a5-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="864a5-110">模拟电话适配器 (ATA)</span><span class="sxs-lookup"><span data-stu-id="864a5-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="864a5-111">PSTN 模拟网关</span><span class="sxs-lookup"><span data-stu-id="864a5-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="864a5-112">包括 PSTN 模拟网关的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="864a5-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="864a5-113">包括与 ATA 通信的 PSTN 网关的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="864a5-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="864a5-114">若要了解如何配置模拟网关，请参阅 Lync Server 2010 TechNet 库[https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537)中的 "规划以部署模拟设备"。</span><span class="sxs-lookup"><span data-stu-id="864a5-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="864a5-115">（模拟设备在 Lync server 2013 中的工作方式与在 Lync Server 2010 中的工作方式相同。）</span><span class="sxs-lookup"><span data-stu-id="864a5-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="864a5-116">如果交换机支持，可以配置增强型 9-1-1 (E9-1-1) 的交换机。</span><span class="sxs-lookup"><span data-stu-id="864a5-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

