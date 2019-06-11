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

# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013 中的设备硬件支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-12-14_

在部署 IP 电话和模拟设备之前, 必须准备好特定的硬件配置。

运行 Lync Phone Edition 的 IP 电话支持链接层发现协议-媒体终结点发现 ("LLDP-中)" 和 "以太网供电" (PoE)。若要充分利用 LLDP-MED-V, 交换机必须支持 IEEE 802.1 AB 和 ANSI/TIA-1057。 为了利用 PoE, 交换机必须支持 PoE 802.3 AF 或 802.3 at。

若要启用 LLDP-MED-V, 管理员必须使用切换控制台窗口启用 LLDP, 并使用正确的语音 VLAN ID 设置 LLDP 网络策略。

此外, 如果你的部署包括模拟设备, 则必须将模拟网关配置为使用 Lync Server, 并且网关必须是以下各项之一:

  - 模拟电话适配器 (ATA)

  - PSTN 模拟网关

  - 包含 PSTN 模拟网关的 Survivable 分支装置

  - 包括与 ATA 通信的 PSTN 网关的 Survivable 分支装置

若要了解如何配置模拟网关, 请参阅 Lync Server 2010 TechNet 库[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)中的 "规划以部署模拟设备"。 (模拟设备在 Lync Server 2013 中的工作方式与在 Lync Server 2010 中的工作方式相同。)

<div>


> [!IMPORTANT]  
> 如果切换器支持此功能, 则可以将开关配置为增强 9-1-1 (E9-1)。



</div>

</div>

<span> </span>

</div>

</div>

</div>

