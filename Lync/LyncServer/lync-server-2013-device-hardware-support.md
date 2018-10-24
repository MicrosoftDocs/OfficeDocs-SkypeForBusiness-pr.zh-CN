---
title: Lync Server 2013 设备硬件支持
TOCTitle: 设备硬件支持
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412908(v=OCS.15)
ms:contentKeyID: 49314043
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的设备硬件支持

 

_**上一次修改主题：** 2016-12-08_

特定的硬件配置到位后，才能部署 IP 电话和模拟设备。

运行 Lync Phone Edition 的 IP 电话支持 Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) 和 Power over Ethernet (PoE)。要使用 LLDP-MED，交换机必须支持 IEEE802.1AB 和 ANSI/TIA-1057。要使用 PoE，交换机必须支持 PoE802.3AF 或 802.3at。

要启用 LLDP-MED，管理员必须使用交换机控制台窗口启用 LLDP，并使用正确的语音 VLAN ID 设置 LLDP-MED 网络策略。

此外，如果部署包括模拟设备，则必须将模拟网关配置为使用 Lync Server，且网关必须为下列网关之一：

  - 模拟电话适配器 (ATA)

  - PSTN 模拟网关

  - 包括 PSTN 模拟网关的 Survivable Branch Appliance

  - 包括与 ATA 通信的 PSTN 网关的 Survivable Branch Appliance

要了解如何配置模拟网关，请参阅 Lync Server 2010 TechNet 库中的“规划部署模拟设备”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)。（模拟设备在 Lync Server 2013 中的工作方式与它们在 Lync Server 2010 中的相同。）

> [!IMPORTANT]
> 如果交换机支持，可以配置增强型 9-1-1 (E9-1-1) 的交换机。

