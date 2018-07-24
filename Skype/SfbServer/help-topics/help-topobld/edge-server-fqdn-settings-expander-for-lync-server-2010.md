---
title: Lync Server 2010 的边缘服务器 FQDN 设置扩展器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要定义的属性外部设置下，配置以下设置：
ms.openlocfilehash: 27bc29afd26ac280eaeb7469af530862c94b03a6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999728"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘服务器 FQDN 设置扩展器
 
若要定义的属性**外部设置**下，配置以下设置：
  
选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框，如果您想要定义不同池 FQDN 和 IP 地址的 web 会议和音频/视频。
  
> [!NOTE]
> 如果您选择不选中单独的 FQDN 和 IP 地址的复选框，您必须为每个边缘服务器所提供的三个服务提供不同的端口。 是配置的唯一完全限定的域名称是与访问边缘服务相关联的 FQDN。 
  
选择**A / V 边缘服务启用 NAT**复选框，如果您希望 A / V 边缘服务使用网络地址转换 (NAT) IP 地址和配置。
  
对于已启用的边缘服务，键入一个**池 FQDN**和端口**端口**下
  
- 定义**访问边缘服务**的池 FQDN 和唯一标识服务的端口。
    
- 定义**Web 会议边缘服务**的池 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未选中) 和唯一标识服务的端口。
    
- 定义**A / V 边缘服务**池 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未选中) 和唯一标识服务的端口。
    
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  

