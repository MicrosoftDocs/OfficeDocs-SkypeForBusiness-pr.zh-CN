---
title: 添加边缘服务器选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 选择要为边缘池启用的每个功能。默认情况下，边缘池支持组织中使用虚拟专用网络 (VPN) 从防火墙外登录的远程用户。此外，还具有以下边缘池功能选项：
ms.openlocfilehash: 280aa7ec9c6adc68ef7f1316d5eb3024d140bdce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886274"
---
# <a name="add-edge-server-options"></a>添加边缘服务器选项

选择要为边缘池启用的每个功能。默认情况下，边缘池支持组织中使用虚拟专用网络 (VPN) 从防火墙外登录的远程用户。此外，还具有以下边缘池功能选项：

- 为所有边缘服务（包括访问边缘服务、Web 会议边缘服务和 A/V 边缘服务）使用单个完全限定的域名 (FQDN) 和 IP 地址。如果不选择使用一个 FQDN 和 IP 地址的选项，则需要在部署过程中分别为这三个边缘服务指定单独的 FQDN 和 IP 地址。有关边缘服务的详细信息，请参阅规划文档中的[Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx)。

    > [!NOTE]
    > 如果选择此选项，则必须为每个边缘服务指定不同的端口号（推荐的默认端口设置为：访问边缘服务为 444，Web 会议边缘服务为 8057，A/V 边缘服务为 443）。选择此选项可帮助防止潜在的连接问题，并简化配置，因为可以输入一个同时用于三个服务的 FQDN。

- 支持联盟。如果要支持内部用户与组织外受信任域中的用户（包括支持的公共即时消息 (IM) 提供商的任何用户）之间的通信，则选择此选项。如果选择此选项，则需要配置对要支持的特定联盟域和公共 IM 连接服务提供商的支持。有关配置对联盟和其他类型外部用户访问的支持的详细信息，请参阅边缘服务器部署文档中的[Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx)。

    > [!NOTE]
    > 只能为联盟对外发布组织中的一个前端池或 Standard 边缘服务器。联盟用户（包括公共 IM 用户）的所有访问都将通过相同的边缘池或单个边缘服务器。例如，如果部署中有一个边缘池或单个边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单个边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单个边缘服务器。这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。

- 启用 XMPP 联盟。如果要支持内部用户和信任的 XMPP 合作伙伴之间的通信，则选择此选项。

可以在部署初始拓扑时或在部署后添加对外部用户访问的支持。有关向现有拓扑中添加边缘服务器的详细信息，请参阅边缘服务器部署文档中的[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)。


