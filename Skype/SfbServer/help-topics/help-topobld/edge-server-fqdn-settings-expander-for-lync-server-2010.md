---
title: Lync Server 2010 中的边缘服务器 FQDN 设置扩展
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 要定义在外部设置下面的属性，请进行以下配置：
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 中的边缘服务器 FQDN 设置扩展
 
要定义在**外部设置**下面的属性，请进行以下配置：
  
选择**启用单独的 FQDN 和 IP 地址的 web 会议和 A / V**复选框如果您希望定义不同的池的 FQDN 和 IP 地址的 web 会议、 音频/视频。
  
> [!NOTE]
> 如果您选择不选择独立的 FQDN 和 IP 地址的复选框，必须为每个边缘服务器提供的三种服务提供不同的端口。 只是配置的完全合格的域名名称是与访问边缘服务相关联的 FQDN。 
  
选择**A / V 边缘服务是启用 NAT**复选框如果您希望将 A / V 边缘服务使用网络地址转换 (NAT) 的 IP 地址和配置。
  
对于已启用的边缘服务，键入**池的 FQDN**和**端口**下的端口。
  
- 定义**访问边缘服务**池的 FQDN，并唯一地标识该服务的端口。
    
- 定义**Web 会议边缘服务**池的 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未被选中) 唯一地标识该服务的端口。
    
- 定义**A / V 边缘服务**池的 FQDN (如果启用单独的 FQDN 和 IP 地址的 web 会议和 A / V 未被选中) 唯一地标识该服务的端口。
    
 **确定** 接受更改并通过对话框提交更改。
  
 **取消** 放弃更改并关闭对话框。
  
 **帮助** 显示此帮助屏幕。
  

