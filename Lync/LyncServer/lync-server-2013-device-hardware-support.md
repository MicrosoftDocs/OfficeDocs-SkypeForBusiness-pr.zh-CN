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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013 中的设备硬件支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-14_

特定的硬件配置到位后，才能部署 IP 电话和模拟设备。

运行 Lync Phone Edition 的 IP 电话支持链接层发现协议-媒体终结点发现（LLDP-MED-V）和以太网供电（PoE）。要使用 LLDP-MED，交换机必须支持 IEEE802.1AB 和 ANSI/TIA-1057。 要使用 PoE，交换机必须支持 PoE802.3AF 或 802.3at。

要启用 LLDP-MED，管理员必须使用交换机控制台窗口启用 LLDP，并使用正确的语音 VLAN ID 设置 LLDP-MED 网络策略。

此外，如果您的部署包括模拟设备，则必须将模拟网关配置为使用 Lync Server，并且网关必须是以下各项之一：

  - 模拟电话适配器 (ATA)

  - PSTN 模拟网关

  - 包括 PSTN 模拟网关的 Survivable Branch Appliance

  - 包括与 ATA 通信的 PSTN 网关的 Survivable Branch Appliance

若要了解如何配置模拟网关，请参阅 Lync Server 2010 TechNet 库[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)中的 "规划以部署模拟设备"。 （模拟设备在 Lync server 2013 中的工作方式与在 Lync Server 2010 中的工作方式相同。）

<div>


> [!IMPORTANT]  
> 如果交换机支持，可以配置增强型 9-1-1 (E9-1-1) 的交换机。



</div>

</div>

<span> </span>

</div>

</div>

</div>

