---
title: Lync Server 2010 的边缘服务器 FQDN 设置扩展器
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要定义“外部设置”下的属性，请配置以下内容：
ms.openlocfilehash: d8c800051dcbc6aa2c1a533940c3d3d558ef86ba8db115e557846dc04a08c795
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307153"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的边缘服务器 FQDN 设置扩展器
 
若要定义“外部设置”下的属性，请配置以下内容：
  
如果想要为 Web 会议和 A/V 定义不同的池 FQDN 和 IP 地址，则选中“为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址”复选框。
  
> [!NOTE]
> 如果选择不选中单独的 FQDN 和 IP 地址的复选框，则必须为边缘服务器提供的三个服务分别提供不同的端口。 唯一要配置的完全限定域名是与访问边缘服务关联的 FQDN。 
  
如果希望 A/V 边缘服务使用网络地址转换和 NAT (IP 地址和配置，请选中 **"A/V** 边缘服务已启用 NAT) 复选框。
  
对于已启用的边缘服务，在"端口"下键入 **池 FQDN** 和 **端口**
  
- 定义访问 **边缘服务** 池 FQDN 和唯一标识该服务的端口。
    
- 定义 **Web** 会议边缘服务池 FQDN (如果未选择"为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址") 并且未选择唯一标识该服务的端口。
    
- 定义 **A/V** 边缘服务池 FQDN (如果未选择"为 Web 会议和 A/V 启用单独的 FQDN 和 IP 地址") 并且未选择唯一标识该服务的端口。
    
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  

