---
title: 编辑适合于 Lync Server 2010 的 Edge 设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 可通过配置以下属性来编辑 Edge 服务器或边缘池的设置：
ms.openlocfilehash: f483f87ad6c7ba6fa8cfc89e0b5d11899a68119a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820004"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>编辑适合于 Lync Server 2010 的 Edge 设置扩展器
 
可通过配置以下属性来编辑 Edge 服务器或边缘池的设置： 
  
 **常规**
  
- **内部池 FQDN**：内部池完全限定的域名是指在域名系统（DNS）主机（A 或 AAAA IPv6）记录中定义的边缘服务器或边缘池的标识。
    
- 如果要为与其他会话初始协议合作伙伴的联盟启用边缘服务器或边缘池，请选择 "**为此边缘池启用联盟（端口5061）** "。
    
    > [!IMPORTANT]
    > 你只能为联盟定义一个边缘服务器或边缘池。 关联的屏幕截图中显示的配置表示已为联盟配置了其他边缘服务器或边缘池。 联盟（_sipfederationtls _tcp 的外部 DNS SRV 记录。\<外部域名\>）将指向边缘服务器或联盟的边缘池。 
  
- 默认情况下，**内部配置复制端口（HTTPS）** 在 TCP 端口4443上，是复制中央管理存储的本地（即边缘服务器的本地）副本的端口。 中央管理存储的本地副本位于每台计算机上 SQL Server 中的**RTCLOCAL**数据库中。 复制是从中央管理服务器（或将中央管理服务器角色保留中央管理服务器角色的前端服务器或前端池）启动到边缘服务器的单向复制，并且是一个内部接口端口。
    
  **下一跃点选择**
  
- 选择以列出**下一个跃点池**。 你可以定义 Director、Director 池、前端服务器或前端池以承担此角色。 下一个跃点池是服务器或服务器池，将接受来自 Edge 服务器或边缘池内部接口的入站 SIP 消息，并将出站 SIP 发送到 Edge 内部接口。
    
    > [!NOTE]
    > Director 是可选角色，如果您决定不部署控制器，前端服务器（单个计算机或池）将承担 Director 角色。 
  
  **外部设置**
  
此部分属性允许你编辑边缘服务器或边缘池的外部设置的属性。 可编辑以下属性：
  
- 如果要向每个 Edge 服务器服务分配不同的 IP 地址和完全限定的域名，请选中 "**为 web 会议和 A/V 启用单独的 FQDN 和 IP 地址**" 复选框。
    
    > [!NOTE]
    > 如果您选择不选中此复选框，则必须为每个 Edge 服务使用单独的端口。 每个 Edge 服务将共享为访问边缘服务定义的 FQDN，因此将使用相同的 IP 地址。 每个 Edge 服务必须由不同的 IP 地址和相同的端口以及相同的 IP 地址和唯一的端口值进行唯一标识。 
  
- 如果要将 A/V 边缘服务配置为使用专用地址或将在网络地址转换（NAT）设备后面隐藏的其他地址，请选择 " **a/v 边缘服务**"。
    
- 若要编辑**Access edge 服务**，请为 access edge 服务定义**池 FQDN** ，如 DNS 中的主机（A 和 AAAA 使用了 IPv6）记录和一个端口值
    
- 若要编辑**Web 会议 edge 服务**，请为 Web 会议 edge 服务定义**池 FQDN** ，如 DNS 中的主机（a 和 AAAA 使用 IPv6）中定义的记录和端口值
    
- 若要编辑**a/v 边缘服务**，请为在 DNS 中定义的 a/v 边缘服务定义**池 FQDN** ，如 DNS 中的主机（A 和 AAAA 使用 IPv6）记录和一个端口值
    
    > [!IMPORTANT]
    > 如果已选中 "对**web 会议启用单独的 FQDN 和 IP 地址" 和 "A/V** " 复选框，则只有访问边缘服务池 FQDN 可供编辑。 为三个边缘服务中的每一个分配不同的端口。
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

