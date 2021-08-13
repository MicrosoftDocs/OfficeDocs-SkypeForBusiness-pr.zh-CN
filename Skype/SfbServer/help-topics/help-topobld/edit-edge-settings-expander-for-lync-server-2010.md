---
title: 编辑 Lync Server 2010 的边缘设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 通过配置以下属性编辑边缘服务器或边缘池的设置：
ms.openlocfilehash: 5b4f9e2f6b4c5b74b0c1eadb8d48bc5a4ade0375e48dfdf1ecf399032db5693e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335172"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>编辑适合于 Lync Server 2010 的边缘设置扩展器
 
通过配置以下属性编辑边缘服务器或边缘池的设置： 
  
 **常规**
  
- 内部池 **FQDN：** 内部池完全限定域名是边缘服务器或边缘池的标识，如域名系统 (DNS) 主机 (A 或 AAAA for IPv6) 记录所定义。
    
- 如果要为边缘服务器或边缘池启用与其他会话初始协议伙伴的联盟 (端口 **5061**) ，请选择"为此边缘池启用联盟"。
    
    > [!IMPORTANT]
    > 只能为联盟主动定义一个边缘服务器或边缘池。 关联的屏幕截图中显示的配置指示已针对联盟配置了其他边缘服务器或边缘池。 联合身份验证的外部 DNS SRV 记录 (_sipfederationtls._tcp。 \<external domain name\>) 将指向联盟的边缘服务器或边缘池。 
  
- 默认情况下 **，TCP** 端口 4443 中的内部配置复制端口 (HTTPS) 是本地 (（即中央管理存储的边缘服务器) 副本的本地）的端口。 中央管理存储的本地副本位于每台计算机的 SQL Server **RTCLOCAL** 数据库中。 复制是单向的，从中央管理服务器 (或将中央管理服务器角色) 的前端服务器或前端池启动到边缘服务器，是内部接口端口。
    
  **下一个跃点选择**
  
- 为“下一个跃点池”列表进行选择。 定义控制器、控制器池、前端服务器或前端池以承担此角色。 下一个跃点池是接受来自边缘服务器或边缘池内部接口的入站 SIP 消息并将出站 SIP 发送到边缘内部接口的服务器或服务器池。
    
    > [!NOTE]
    > 控制器是可选角色，如果您决定不部署控制器，则单台计算机或 (前端服务器将) 控制器角色。 
  
  **外部设置**
  
通过这些属性的这一部分，您可以编辑边缘服务器或边缘池的外部设置的属性。 可编辑以下属性：
  
- 如果要为每个边缘服务器服务分配不同的 IP 地址和完全限定的域名，请选中"为 Web 会议和 A/V 启用单独的 **FQDN** 和 IP 地址"复选框。
    
    > [!NOTE]
    > 如果选择不选中该复选框，则必须为每个边缘服务使用单独的端口。 每个边缘服务将共享为访问边缘服务定义的 FQDN，因此将使用相同的 IP 地址。 每个边缘服务都必须通过一个不同的 IP 地址和相同的端口，或相同的 IP 地址和唯一的端口值进行唯一标识。 
  
- 如果要 **将 A/ (V** 边缘服务配置为使用将在网络地址转换设备或 NAT) 设备隐藏的专用地址或其他地址，请选择"A/V 边缘服务已启用 NAT"。
    
- 若要编辑访问边缘服务，请为访问边缘服务定义池 **FQDN（** 如 DNS 中由主机 (A 定义）和 AAAA（如果使用 IPv6) 记录和端口值）
    
- 若要编辑 **Web** 会议边缘服务，请为 WEB 会议边缘服务定义池 **FQDN，** 如主机 (A 在 DNS 中定义，如果使用 IPv6，则定义 AAAA（如果使用) 记录和端口值）
    
- 若要编辑 **A/V** 边缘服务，请为 A/V 边缘服务定义池 **FQDN，** 如主机 (A 在 DNS 中定义，如果使用 IPv6，则定义 AAAA（如果使用) 记录和端口值）
    
    > [!IMPORTANT]
    > 如果选中了"为 Web 会议和 A/V 启用单独的 **FQDN** 和 IP 地址"复选框，则只有访问边缘服务池 FQDN 可用于编辑。 为三个边缘服务各自分配不同的端口。
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

