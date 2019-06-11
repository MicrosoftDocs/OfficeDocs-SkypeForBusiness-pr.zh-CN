---
title: Lync Server 2013 设备硬件支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="29217-102">Lync Server 2013 中的设备硬件支持</span><span class="sxs-lookup"><span data-stu-id="29217-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29217-103">_**主题上次修改时间:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="29217-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="29217-104">在部署 IP 电话和模拟设备之前, 必须准备好特定的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="29217-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="29217-105">运行 Lync Phone Edition 的 IP 电话支持链接层发现协议-媒体终结点发现 ("LLDP-中)" 和 "以太网供电" (PoE)。</span><span class="sxs-lookup"><span data-stu-id="29217-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="29217-106">若要充分利用 LLDP-MED-V, 交换机必须支持 IEEE 802.1 AB 和 ANSI/TIA-1057。</span><span class="sxs-lookup"><span data-stu-id="29217-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="29217-107">为了利用 PoE, 交换机必须支持 PoE 802.3 AF 或 802.3 at。</span><span class="sxs-lookup"><span data-stu-id="29217-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="29217-108">若要启用 LLDP-MED-V, 管理员必须使用切换控制台窗口启用 LLDP, 并使用正确的语音 VLAN ID 设置 LLDP 网络策略。</span><span class="sxs-lookup"><span data-stu-id="29217-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="29217-109">此外, 如果你的部署包括模拟设备, 则必须将模拟网关配置为使用 Lync Server, 并且网关必须是以下各项之一:</span><span class="sxs-lookup"><span data-stu-id="29217-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="29217-110">模拟电话适配器 (ATA)</span><span class="sxs-lookup"><span data-stu-id="29217-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="29217-111">PSTN 模拟网关</span><span class="sxs-lookup"><span data-stu-id="29217-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="29217-112">包含 PSTN 模拟网关的 Survivable 分支装置</span><span class="sxs-lookup"><span data-stu-id="29217-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="29217-113">包括与 ATA 通信的 PSTN 网关的 Survivable 分支装置</span><span class="sxs-lookup"><span data-stu-id="29217-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="29217-114">若要了解如何配置模拟网关, 请参阅 Lync Server 2010 TechNet 库[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)中的 "规划以部署模拟设备"。</span><span class="sxs-lookup"><span data-stu-id="29217-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="29217-115">(模拟设备在 Lync Server 2013 中的工作方式与在 Lync Server 2010 中的工作方式相同。)</span><span class="sxs-lookup"><span data-stu-id="29217-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="29217-116">如果切换器支持此功能, 则可以将开关配置为增强 9-1-1 (E9-1)。</span><span class="sxs-lookup"><span data-stu-id="29217-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

