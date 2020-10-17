---
title: Lync Server 2013： IP 地址类型概述
description: Lync Server 2013： IP 地址类型概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559218"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013 的 IP 地址类型概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-29_

在 Lync Server 2013 中配置 IP 地址时有三个选项。 您可以将 Lync Server 2013 配置为仅支持 IP 版本 4 (IPv4) 、仅 IP 版本 6 (IPv6) ，或者 () 称为 *双堆栈* 的组合。 对于每种类型的配置，都需要考虑一些问题：

  - **仅 IPv4**    由于世界耗尽了 IPv4 地址，因此已创建 IPv6。 最终，IPv6 将会在世界范围内得到完全支持，但现在有很多您的企业可能需要与之通信的公司和设备尚不支持 IPv6，并且在一段时间内可能也不会支持。 仅 IPv4 配置将有助于确保你的 Lync Server 实现能够与大多数现有设备通信。

  - **仅限 IPv6**    相反，完整的 IPv6 实现现在将排除与许多现有设备的通信。

  - **双栈**    双栈是启用 IPv4 和 IPv6 地址的网络。 Lync Server 2013 支持此配置，因为在大多数情况下，从完整 IPv4 到完整 IPv6 的转换需要几年时间。

以下各节概述了各种 Lync Server 功能在这三种配置中的兼容性。

<div>


> [!NOTE]  
> 仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。



</div>

<div>

## <a name="client-registration"></a>客户端注册


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端终结点网络</th>
<th>服务器网络</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>对等客户端

对等通信包括音频、音频/视频、应用程序共享和文件传输。两个客户端均注册成功后，将支持以下组合。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端终结点 1</th>
<th>客户端终结点 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>会议

会议包括音频/视频、应用程序共享和数据协作（白板和文件共享）。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端终结点网络</th>
<th>服务器网络</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>中介服务器/PSTN

如果流量通过 IPv6 接口，Lync Server 2013 不支持公用交换电话网络 (PSTN) 呼叫的媒体旁路。 如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>主要接口*</th>
<th>PSTN 接口（位于中介服务器上）</th>
<th>PSTN 网关设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>双协议栈</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* 主接口是与 Lync Server 组件进行通信的接口。

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>远程用户对等通信

与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>远程用户网络</th>
<th>边缘服务器（外部边缘）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>双协议栈</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>双协议栈</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>双协议栈</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>前端池和边缘池配置

下表显示了前端服务器池和内部边缘服务器池之间的支持列表。

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>前端池和边缘池（内部边缘）矩阵

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>边缘池：IPv4</strong></p></td>
<td><p><strong>边缘池：双协议栈</strong></p></td>
<td><p><strong>边缘池：IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>前端池：IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>前端池：双协议栈</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>前端池：IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是*</p></td>
</tr>
</tbody>
</table>


\* 仅在实验室环境中使用此组合。

下表是内部和外部边缘接口支持的组合矩阵。

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>边缘池（内部边缘）和边缘池（外部边缘）矩阵

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>边缘池（外部边缘）：IPv4</strong></p></td>
<td><p><strong>边缘池（外部边缘）：双协议栈</strong></p></td>
<td><p><strong>边缘池（外部边缘）：IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>边缘池（内部边缘）：IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>边缘池（内部边缘）：双协议栈</strong></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>边缘池（内部边缘）：IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是*</p></td>
</tr>
</tbody>
</table>


\* 仅在实验室环境中使用此组合。

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 的高级企业语音支持

包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实现。

<div>


> [!NOTE]  
> 在双堆栈部署中，即使 Lync 客户端使用 IPv6 连接到 Lync Server，Lync 也将尽力映射合适的 IPv4 地址以支持 E9-1-1。



</div>

不支持使用 IPv6 地址的位置信息服务。

Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>适用于 IPv6 的其他 Lync Server 2013 功能支持

除了前面提到的功能和组件，Lync Server 2013 还支持 IPv6 以实现以下功能：

  - **持久聊天**
    
    您可以使用拓扑生成器为持久聊天配置 IPv6。 有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。

  - **用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**
    
    监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

