---
title: 编辑 Lync Server 2010 中的边缘设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 您可以通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>编辑 Lync Server 2010 中的边缘设置扩展器
 
您可以通过配置以下属性编辑边缘服务器或边缘池的设置： 
  
 **常规**
  
- **内部池的 FQDN**： 内部池完全限定的域名是域名系统 (DNS) 主机 （A 或 AAAA ipv6） 记录中定义的边缘服务器或边缘池的标识。
    
- 如果您想要启用的边缘服务器或其他会话启动协议合作伙伴与联盟的边缘池，请选择**启用此边缘池 （端口 5061） 联盟**。
    
    > [!IMPORTANT]
    > 您只能定义一个边缘服务器或边缘池积极为联盟。 相关的屏幕快照中所示的配置表示为联合已经配置了另一个边缘服务器或边池。 联盟的外部 DNS SRV 记录 (_sipfederationtls._tcp。\<外部域名\>) 将指向的边缘服务器或联盟的边缘池。 
  
- **内部配置复制端口 (HTTPS)**，默认情况下 TCP 端口 4443，是端口的本地 (即，边缘服务器的本地) 的中央管理存储副本复制到。 中央管理存储的本地副本是在**RTCLOCAL**中每台计算机上的 SQL Server 数据库中。 复制到边缘服务器启动从中央管理服务器 （或前端服务器或前端池中包含的中央管理服务器角色） 是单向的而且是内部接口端口。
    
 **下一跃点的选择**
  
- 列表中选择您的**下一个跃点池**。 导演池、 前端服务器或前端池可承担此角色，您可以定义导演。 下一个跃点池的服务器或服务器池将接受来自边缘服务器的入站的 SIP 消息或边缘池内部接口和发送出站 SIP 与边缘的内部接口。
    
    > [!NOTE]
    > 控制器是一个可选角色和前端服务器 （单机或池） 如果您决定不将部署控制器，将假定控制器角色。 
  
 **外部设置**
  
此节的属性允许您编辑的边缘服务器或池边缘的外部设置的属性。 可编辑以下属性：
  
- 选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**为每个边缘服务器服务名称的复选框，如果您想要分配不同的 IP 地址和完全限定的域名。
    
    > [!NOTE]
    > 如果选择未选中复选框，则必须为每个边缘服务使用不同的端口。 每个边缘服务将共享访问边缘服务中，为定义的 FQDN，并因此将使用相同的 IP 地址。 必须由一个不同的 IP 地址和同一个端口，或相同的 IP 地址和唯一的端口值唯一标识每个边缘服务。 
  
- 选择**A / V 边缘服务是启用 NAT**如果您想要配置 A / V 边缘服务要使用专用地址或其他地址将被隐藏在网络地址转换 (NAT) 设备后面。
    
- 若要编辑**访问边缘服务**，您定义访问边缘服务**池的 FQDN**在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值
    
- 若要编辑**Web 会议边缘服务**，定义 Web 会议边缘服务**池的 FQDN**在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值
    
- 编辑**A / V 边缘服务**，您定义一个**池的 FQDN**的 A / V 边缘服务在 DNS 中定义的主机 （A 和 AAAA 如果使用 IPv6） 记录和端口值
    
    > [!IMPORTANT]
    > 如果选择了**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，将提供用于编辑只访问边缘服务池的 FQDN。 每个三个的边缘服务分配不同的端口。
  
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  

