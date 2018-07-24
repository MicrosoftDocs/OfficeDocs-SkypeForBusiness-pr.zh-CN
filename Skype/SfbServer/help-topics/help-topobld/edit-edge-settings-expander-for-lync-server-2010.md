---
title: 编辑 Lync Server 2010 的边缘设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: e09f20840627af19f1f9f2fa33dc5ab5f6b342f3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975926"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>编辑 Lync Server 2010 的边缘设置扩展器
 
通过配置以下属性编辑边缘服务器或边缘池的设置： 
  
 **常规**
  
- **内部池 FQDN**： 内部池完全限定的域名称是域名系统 (DNS) 主机 （A 或对于 IPv6 为 AAAA） 记录中定义的边缘服务器或边缘池的标识。
    
- 如果您想要启用边缘服务器或边缘池用于与其他会话初始协议合作伙伴的联盟，请选择**启用联盟，为此边缘池 （端口 5061）** 。
    
    > [!IMPORTANT]
    > 仅可以定义一个边缘服务器或边缘池主动用于联合身份验证。 关联的屏幕截图中所示的配置指示已为联盟配置了另一台边缘服务器或边缘池。 联合身份验证的外部 DNS SRV 记录 (_sipfederationtls._tcp。\<外部域名\>) 将指向边缘服务器或边缘池用于联合身份验证。 
  
- **内部配置复制端口 (HTTPS)**，默认情况下，在 TCP 端口 4443，是端口的本地 (即，本地到边缘服务器) 的中央管理存储副本都通过复制。 在**RTCLOCAL**数据库中每台计算机上的 SQL Server 中央管理存储的本地副本。 复制是单向，启动从中央管理服务器 （或包含中央管理服务器角色的前端服务器或前端池） 到边缘服务器，内部接口端口。
    
 **下一个跃点选择**
  
- 列表中选择**下一个跃点池**。 控制器池，假定此角色的前端服务器或前端池，您可以定义控制器。 下一个跃点池是服务器或将接受从边缘服务器的入站的 SIP 消息的服务器池或边缘池内部接口和发送出站 SIP 到边缘内部接口。
    
    > [!NOTE]
    > Director 是一个可选角色，如果您决定不部署控制器，前端服务器 （单个计算机或池） 将假定控制器角色。 
  
 **外部设置**
  
本节中的属性，可以编辑的边缘服务器或边缘池的外部设置的属性。 可编辑以下属性：
  
- 选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，如果您想要分配不同的 IP 地址和完全限定名称到每个边缘服务器服务。
    
    > [!NOTE]
    > 如果您选择不选中的复选框，则必须为每个边缘服务使用单独的端口。 每个边缘服务将共享为访问边缘服务，定义的 FQDN，因此将使用相同的 IP 地址。 每个边缘服务必须唯一地标识通过不同的 IP 地址和同一个端口，或同一个 IP 地址和唯一的端口值。 
  
- 选择**A / V 边缘服务启用 NAT**如果您想要配置 A / V 边缘服务使用专用的地址或其他将隐藏网络地址转换 (NAT) 设备的地址。
    
- 若要编辑**访问边缘服务**，您定义**池 FQDN**为访问边缘服务在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值
    
- 若要编辑**Web 会议边缘服务**，您定义一个用于 Web 会议边缘服务的**池 FQDN**在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值
    
- 编辑**A / V 边缘服务**，您定义**池 FQDN**的 a / V 边缘服务在 DNS 中定义的主机 （A 和如果使用 IPv6 为 AAAA） 记录和一个端口值
    
    > [!IMPORTANT]
    > 如果选择了**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，只是访问边缘服务池 FQDN 以供编辑。 三种边缘服务的每个分配不同的端口。
  
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  

