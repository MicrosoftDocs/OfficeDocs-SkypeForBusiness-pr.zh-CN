---
title: Lync Server 2013：支持呼叫寄存的客户端
TOCTitle: 支持呼叫寄存的客户端
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412958(v=OCS.15)
ms:contentKeyID: 49314159
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中支持呼叫寄存的客户端

 

_**上一次修改主题：** 2012-09-13_

本节介绍可用于寄存呼叫的客户端和可用于取回寄存呼叫的客户端。

## 支持寄存呼叫的客户端

可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。

> [!NOTE]  
> 只能寄存音频呼叫。不能寄存即时消息和会议。



以下客户端可使用 呼叫寄存寄存呼叫：

  - Lync 2013

  - Lync 2010

  - Lync 2010 Attendant

  - Lync Phone Edition

> [!NOTE]  
> 移动电话不能使用 呼叫寄存寄存呼叫。



## 支持取回呼叫的客户端

将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。

联盟用户无法取回寄存的呼叫。

以下客户端可取回寄存在 呼叫寄存上的呼叫：

  - Lync 2013

  - Lync 2010

  - Lync 2010 Attendant

  - Lync Phone Edition

  - IP 公用区域电话

  - 连接到 Lync Server 2013 基础结构的非 IP 电话，包括公用区域电话和专用交换机 (PBX) 电话

