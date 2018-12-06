---
title: Lync Server 2013：外围网络 VoIP 组件
TOCTitle: 外围网络 VoIP 组件
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398559(v=OCS.15)
ms:contentKeyID: 49313251
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的外围网络 VoIP 组件

 

_**上一次修改主题：** 2012-09-21_

使用统一通信客户端进行个别呼叫或电话会议的外部呼叫者依靠 边缘服务器与同事进行语音通信。

在 边缘服务器上，访问边缘服务为来自组织防火墙之外的 Lync 用户的呼叫提供 SIP 信号。A/V 边缘服务使媒体可以遍历 NAT 和防火墙。从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。

A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。

