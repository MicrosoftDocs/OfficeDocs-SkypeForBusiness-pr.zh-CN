---
title: Lync Server 2013：IP 地址类型概述
TOCTitle: Lync Server 的 IP 地址类型概述
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205363(v=OCS.15)
ms:contentKeyID: 49314671
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 IP 地址类型概述

 

_**上一次修改主题：** 2015-03-09_

在 Lync Server 2013 中配置 IP 地址时有三个选项。您可将 Lync Server 2013 配置为仅支持 IP 版本 4 (IPv4)、仅支持 IP 版本 6 (IPv6) 或支持二者的组合（称为*双协议栈*）。对于每种类型的配置，都需要考虑一些问题：

  - **仅 IPv4**   之所以创建 IPv6 是因为世界上的 IPv4 地址快要用完了。最终，IPv6 将会在世界范围内得到完全支持，但现在有很多您的企业可能需要与之通信的公司和设备尚不支持 IPv6，并且在一段时间内可能也不会支持。仅 IPv4 配置将有助于确保 Lync Server 实现可与大部分现有设备进行通信。

  - **仅 IPv6**   相反，现在完全实现 IPv6 将会导致无法与许多现有设备通信。

  - **双协议栈**   双协议栈是同时支持 IPv4 和 IPv6 地址的网络。 Lync Server 2013 中支持此配置，因为在大多数情况下，从完全 IPv4 到完全 IPv6 的切换需要若干年。

以下各节概述了各种 Lync Server 功能在三种配置之间的兼容性。

> [!NOTE]  
> 仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。



## 客户端注册


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


## 对等客户端

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


## 会议

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


## 中介服务器/PSTN

如果通信通过 IPv6 接口，则 Lync Server 2013 不支持公用电话交换网 (PSTN) 呼叫的媒体旁路。如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。


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


\* 主要接口是与 Lync Server 组件进行通信的接口。

## 远程用户对等通信

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


## 前端池和边缘池配置

下表显示的是 前端服务器池和内部 边缘服务器池之间的支持矩阵。

### 前端池和边缘池（内部边缘）矩阵

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
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
<td><p>支持*</p></td>
</tr>
</tbody>
</table>


\* 仅在实验室环境中使用此组合。

下表是内部和外部边缘接口支持的组合矩阵。

### 边缘池（内部边缘）和边缘池（外部边缘）矩阵

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
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
<td><p>支持*</p></td>
</tr>
</tbody>
</table>


\* 仅在实验室环境中使用此组合。

## IPv6 的高级企业语音支持

包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实现。

> [!NOTE]  
> 在双协议栈部署中，即使 Lync 客户端使用 IPv6 连接到 Lync Server， Lync 也尽力映射相应的 IPv4 地址以支持 E9-1-1。



不支持使用 IPv6 地址的 位置信息服务。

Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。

## IPv6 的其他 Lync Server 2013 功能支持

除了之前提到的功能和组件， Lync Server 2013 还对以下功能支持 IPv6：

  - **持久聊天**
    
    您可使用 拓扑生成器为 持久聊天配置 IPv6。有关配置 持久聊天的详细信息，请参阅“部署持久聊天服务器”文档。

  - **用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**
    
    监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。

