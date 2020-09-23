---
title: 编辑 Lync Server 2010 的边缘设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 可以通过配置以下属性来编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216113"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>编辑 Lync Server 2010 的边缘设置扩展器
 
可以通过配置以下属性来编辑边缘服务器或边缘池的设置： 
  
 **常规**
  
- **内部池 FQDN**：内部池完全限定域名是在域名系统中定义的边缘服务器或边缘池的标识 (DNS) 主机 (A 或 AAAA for IPv6) 记录。
    
- 选择 " **为此边缘池启用联盟" (端口 5061) ** 如果要为其他会话初始协议合作伙伴启用与联盟的边缘服务器或边缘池。
    
    > [!IMPORTANT]
    > 您只能为联合定义一个边缘服务器或边缘池。 相关联的屏幕截图中显示的配置指示已为联盟配置了另一台边缘服务器或边缘池。 联合身份验证 (_sipfederationtls _tcp 的外部 DNS SRV 记录。 \<external domain name\>) 将指向边缘服务器或边缘池以进行联盟。 
  
- 默认情况下， **内部配置复制端口 (HTTPS) **，默认情况下，TCP 端口4443是本地 (（即，复制中央管理存储) 副本的本地服务器的端口）。 中央管理存储的本地副本位于每台计算机上的 SQL Server 中的 **RTCLOCAL** 数据库中。 复制是从中央管理服务器启动的单向的 (，或者是前端服务器或前端池，它将中央管理服务器角色) 到边缘服务器，并且是一个内部接口端口。
    
  **下一个跃点选择**
  
- 为“下一个跃点池”**** 列表进行选择。 您可以定义控制器、控制器池、前端服务器或前端池以承担此角色。 下一个跃点池是服务器或服务器池，它将接受来自边缘服务器或边缘池内部接口的入站 SIP 消息，并将出站 SIP 发送到边缘内部接口。
    
    > [!NOTE]
    > Director 是一个可选角色，如果您决定不部署控制器，则 (单个计算机或池) 的前端服务器将承担控制器角色。 
  
  **外部设置**
  
通过此属性部分，可以编辑边缘服务器或边缘池的外部设置的属性。 可编辑以下属性：
  
- 如果要将不同的 IP 地址和完全限定的域名分配给每个边缘服务器服务，请选中 " **为 web 会议和 A/V 启用单独的 FQDN 和 IP 地址** " 复选框。
    
    > [!NOTE]
    > 如果选择不选中该复选框，则必须为每个边缘服务使用单独的端口。 每个边缘服务将共享为访问边缘服务定义的 FQDN，因此将使用相同的 IP 地址。 每个边缘服务都必须通过一个不同的 IP 地址和相同的端口，或相同的 IP 地址和唯一的端口值进行唯一标识。 
  
- 如果要将 A/V 边缘服务配置为使用专用地址或其他将隐藏在网络地址转换 (NAT) 设备后面的其他地址，则选择 **a/v 边缘服务将启用 NAT** 。
    
- 若要编辑 **访问边缘服务**，请为访问边缘服务定义按主机 (A 的 **池 FQDN** ，以及如果) 记录和端口值使用了 IPV6，则为 AAAA。
    
- 若要编辑 **Web 会议边缘服务**，请为 Web 会议边缘服务定义 **池 FQDN** ，如 DNS 中所定义的主机 (a）和 AAAA （如果使用 IPv6）) 记录和端口值
    
- 若要编辑 **a/v 边缘服务**，请为主机 (a 的 DNS 中定义的 a/v 边缘服务定义 **池 FQDN** ，如果) 记录和端口值使用了 IPV6，则为 AAAA。
    
    > [!IMPORTANT]
    > 如果已选中 "为 **web 会议和 A/V 启用单独的 FQDN 和 IP 地址** " 复选框，则只有访问边缘服务池 FQDN 可供编辑。 为三个边缘服务各自分配不同的端口。
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

