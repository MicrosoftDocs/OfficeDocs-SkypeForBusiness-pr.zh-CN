---
title: Lync Server 2013：使用第三方 PSTN 网关或 PBX 时的呼叫允许控制
TOCTitle: 使用第三方 PSTN 网关或 PBX 时的呼叫允许控制
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398762(v=OCS.15)
ms:contentKeyID: 49313647
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用第三方 PSTN 网关或 PBX 时 Lync Server 2013 中的呼叫允许控制

 

_**上一次修改主题：** 2012-10-20_

本主题举例说明如何在中介服务器的网关接口与第三方公用电话交换网 (PSTN) 网关或专用交换机 (PBX) 之间的链接上部署呼叫允许控制 (CAC)。

## 示例 1：中介服务器与 PSTN 网关之间的 CAC

可以在从中介服务器的网关接口连接到第三方 PBX 或 PSTN 网关的 WAN 链路上部署 CAC。

**示例 1：中介服务器与 PSTN 网关之间的 CAC**

![示例 1：中介服务器与 PSTN 网关之间的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "示例 1：中介服务器与 PSTN 网关之间的 CAC")

在此示例中，将在中介服务器与 PSTN 网关之间应用 CAC。如果网络站点 1 上的 Lync 客户端用户通过网络站点 2 中的 PSTN 网关发出 PSTN 呼叫，则媒体将流经 WAN 链路。因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

  - Lync 客户端应用程序与中介服务器之间

  - 中介服务器与 PSTN 网关之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端应用程序发送的传出 PSTN 呼叫。

> [!NOTE]  
> 请确保 PSTN 网关所属的 IP 子网已配置并与网络站点 2 相关联。<br />
请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。<br />
有关详细信息，请参阅 <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点相关联</a>。



## 示例 2：中介服务器与具有媒体端点的第三方 PBX 之间的 CAC

此配置与示例 1 类似。在这两个示例中，中介服务器知道哪个设备会在 WAN 链路的另一端终止媒体，而且 PSTN 网关或具有媒体端点 (MTP) 的 PBX 的 IP 地址在中介服务器上配置为下一个跃点。

**示例 2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**

![示例 2：中介服务器与具有 MTP 的 PBX 之间的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "示例 2：中介服务器与具有 MTP 的 PBX 之间的 CAC")

在此示例中，将在中介服务器与 PBX/MTP 之间应用 CAC。如果网络站点 1 上的 Lync 客户端用户通过网络站点 2 中的 PBX/MTP 发出 PSTN 呼叫，则媒体将流经 WAN 链路。因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

  - Lync 客户端应用程序与中介服务器之间

  - 中介服务器与 PBX/MTP 之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端发送的传出 PSTN 呼叫。

> [!NOTE]  
> 请确保 MTP 所属的 IP 子网已配置并与网络站点 2 相关联。<br />
请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。<br />
有关详细信息，请参阅 <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点相关联</a>。



## 示例 3：中介服务器与没有媒体端点的第三方 PBX 之间的 CAC

示例 3 与前两个示例略有不同。如果第三方 PBX 上没有 MTP，则对于向第三方 PBX 发出的传出会话请求，中介服务器不知道媒体将在 PXB 边界中终止的位置。在此示例中，媒体直接在中介服务器与第三方终结点设备之间流动。

**示例 3：中介服务器与没有 MTP 的第三方 PBX 之间的 CAC**

![示例 3：中介服务器与不具有 MTP 的 PBX 之间的 CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "示例 3：中介服务器与不具有 MTP 的 PBX 之间的 CAC")

在此示例中，如果网络站点 1 上的 Lync 客户端用户通过 PBX 向用户发出呼叫，中介服务器将能够仅在代理线路（Lync 客户端应用程序与中介服务器之间）上执行 CAC 检查。由于中介服务器不了解请求会话时的终结点设备，因此，在呼叫建立之前无法在 WAN 链路（中介服务器与第三方终结点之间）上执行 CAC 检查。但是，在建立会话后，中介服务器有助于查明中继上使用的带宽。

对于来自第三方终结点的呼叫，在发出会话请求时会提供有关终结点设备的信息，而且可以同时在中介服务器的两端执行 CAC 检查。

> [!NOTE]  
> 请确保终结点设备所属的 IP 子网已配置并与网络站点 2 相关联。<br />
请确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点 1 相关联。<br />
有关详细信息，请参阅 <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点相关联</a>。


